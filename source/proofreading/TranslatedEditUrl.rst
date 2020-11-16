**获取智能校对地址**
========================

**请求地址**

::

   GET https://coresite.ctcfile.com/Translate/GetTranslatedEditUrl

**请求参数**

========= ==== ====== ==== ==============================
属性      类型 默认值 必填 说明
========= ==== ====== ==== ==============================
fileLibId int         是   翻译接口返回的fileLibIds字段值
========= ==== ====== ==== ==============================

**返回值**

==== ====== ===============
属性 类型   说明
==== ====== ===============
url  string 智能校对URL地址
==== ====== ===============

**返回数据示例**

正常返回

::


   https://www.xxx.com/new-post-editing-second?type=ctc&lang=zh&fileId=1154&token=xxxxx

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具| 调试该接口

.. |网页调试工具| raw:: html
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/get_Translate_GetTranslatedEditUrl__fileLibId_" target="_blank">网页调试工具</a>