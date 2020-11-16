**pdf转word**
=================

**请求地址**

::

   POST https://coresite.ctcfile.com/Convert/PdfConvertUseOcr

**请求参数**

==== ====== ====== ==== ============
属性 类型   默认值 必填 说明
==== ====== ====== ==== ============
file binary        是   转换文件(流)
data object        是   转换参数
==== ====== ====== ==== ============

*data的结构*

==== ====== ====== ==== =========================
属性 类型   默认值 必填 说明
==== ====== ====== ==== =========================
lang string        是   PDF文件语言( :doc:`../overview/LanguageType`)
==== ====== ====== ==== =========================

**返回值**

====== ====== ======
属性   类型   说明
====== ====== ======
stream stream 文件流
====== ====== ======

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具| 调试该接口

.. |网页调试工具| raw:: html
 
   <a href="https://coresite.ctcfile.com/%E8%BD%AC%E6%8D%A2%E6%9C%8D%E5%8A%A1%E6%8E%A5%E5%8F%A3/post_Convert_PdfConvertUseOcr" target="_blank">网页调试工具</a>