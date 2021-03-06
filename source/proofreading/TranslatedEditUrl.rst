**获取智能校对地址**
========================

**请求地址**

::

   GET https://api2.ctcfile.com/translations/proofread/{file_lib_id}/url

**请求参数**

=========== ==== ====== ==== ==============================
属性        类型 默认值 必填 说明
=========== ==== ====== ==== ==============================
file_lib_id int         是   文件ID
=========== ==== ====== ==== ==============================

**返回值**

====== ===============
类型   说明
====== ===============
string 智能校对URL地址
====== ===============

**返回数据示例**

正常返回

::


   https://www.xxx.com/new-post-editing-second?type=ctc&lang=zh&fileId=1&token=xxxxx

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具| 调试该接口

.. |网页调试工具| raw:: html
 
   <a href="https://api2.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/get_translations_proofread__file_lib_id__url" target="_blank">网页调试工具</a>