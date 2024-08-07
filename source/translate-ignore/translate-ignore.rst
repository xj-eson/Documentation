获取翻译过滤列表
====================

**请求地址**

::

   GET https://openapi.ctcfile.com/v1/user-text-translate-ignore-items/items


**返回值**

   =========== ========== ==============
   返回字段     字段类型     说明
   =========== ========== ==============
   items       array       翻译过滤列表
   updateTime  datetime    上次更新时间
   =========== ========== ==============

**返回数据示例**

.. code:: json


   {
      "items": [
         "忽略项1",
         "忽略项2"
      ],
      "updateTime": "2024-08-07T09:35:00"
   }


设置过滤项
===========

**请求地址**

::    

   POST https://openapi.ctcfile.com/v1/user-text-translate-ignore-items/set

**请求参数**

================= ====== ==============
属性              类型    说明
================= ====== ==============
items             array  忽略项
================= ====== ==============


**参数示例**

.. code:: json


   {
      "items": [
         "忽略项1",
         "忽略项2"
      ]
   }