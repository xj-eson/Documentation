**充值记录**
=================

**请求地址**

::

   GET https://openapi.ctcfile.com/v1/statistics/recharges

**请求参数**

========== ======== ====== ==== =========================
属性       类型     默认值 必填 说明
========== ======== ====== ==== =========================
start_date datetime        是   开始时间
end_date   datetime        是   结束时间
min_count  int             否   最小操作字数
max_count  int             否   最大操作字数
pageIndex  int      0      否   当前页数，默认从 0 开始
pageSize   int             是   每页显示多少条
========== ======== ====== ==== =========================

**返回值**

============ ====== ====================================
属性         类型   说明
============ ====== ====================================
result       array  数据
toltal_count int    总数量
============ ====== ====================================

*result的结构*

============================ ========= ====================================
属性                         类型      说明
============================ ========= ====================================
file_lib_id                  int       文件Id
option_date                  datetime  操作时间
change_words_count           int       变更字数
remain_words                 int       剩余字数
date_due                     datetime  剩余时间
============================ ========= ====================================


**返回数据示例**

正常返回

.. code:: json


   {
        "result": [
            {
                "file_lib_id": 1,
                "option_date": "2020-12-16T16:32:21.057Z",
                "change_words_count": 50,
                "remain_words": 50,
                "date_due": "2020-12-18T06:05:21.057Z"
            },
            {
                "file_lib_id": 2,
                "option_date": "2020-12-16T16:15:21.057Z",
                "change_words_count": 50,
                "remain_words": 100,
                "date_due": "2020-12-18T06:05:21.057Z"
            }
        ],
        "toltalCount": 10
    }

错误时返回

   :doc:`../overview/StatusCode`
