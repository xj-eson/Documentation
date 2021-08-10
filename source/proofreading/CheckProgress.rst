**获取校对进度**
===================

**请求地址**

::

   GET https://transapi.dl.wiki:30120/translations/proofread/{file_lib_id}

**请求参数**

=========== ==== ====== ==== ======================================
属性        类型 默认值 必填 说明
=========== ==== ====== ==== ======================================
file_lib_id int         是   文件ID
=========== ==== ====== ==== ======================================

**返回值**

======== ====== ======
属性     类型   说明
======== ====== ======
id       int    文件ID
progress double 进度值
======== ====== ======

**返回数据示例**

正常返回

.. code:: json

   {
     "id": 1,
     "progress": 66
   }

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具| 调试该接口

.. |网页调试工具| raw:: html
 
   <a href="https://transapi.dl.wiki:30120/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/get_translations_proofread__file_lib_id_" target="_blank">网页调试工具</a>