**字数翻译趋势**
=================

**请求地址**

::

   GET https://openapi.ctcfile.com/v1/statistics/translate-trends

**请求参数**

========== ======== ====== ==== =========================
属性       类型     默认值 必填 说明
========== ======== ====== ==== =========================
start_date datetime        是   开始时间
end_date   datetime        是   结束时间
date_type  int      2      否   时间类型 包括1:日,2:周,3:月
========== ======== ====== ==== =========================

**返回值**

================ ====== ====================================
属性             类型   说明
================ ====== ====================================
consumeWordCount int    消费字数
date             string 时间
================ ====== ====================================


**返回数据示例**

正常返回

.. code:: json

   [
       {
            consumeWordCount:100,
            date:"01"
       },
       {
            consumeWordCount:110,
            date:"02"
       },
       {
            consumeWordCount:150,
            date:"03"
       },
       {
            consumeWordCount:200,
            date:"04"
       },
       {
            consumeWordCount:500,
            date:"05"
       },
       {
            consumeWordCount:800,
            date:"06"
       },
       {
            consumeWordCount:1000,
            date:"00"
       }
   ]


错误时返回

   :doc:`../overview/StatusCode`

**参数说明**

================== ============================= ============================== ========
date_type          start_date                    end_date                       date     
================== ============================= ============================== ========
1(日)              2020-10-01 00:00:00           2020-10-01 23:59:59            当天每个整点,如:["00:00","01:00"..."23:00"]
2(周)              2020-10-01 00:00:00           2020-10-07 23:59:59            "01":星期一,"02":星期二,"03":星期三,"04":星期四,"05":星期五,"06":星期六,"00":星期日
3(月)              2020-10-01 00:00:00           2020-10-31 23:59:59            当月的每天,如:["01","02","03"..."30"]
================== ============================= ============================== ========


-  ``start_date`` 和 ``end_date`` 参数值请根据 ``date_type`` 自行生成
