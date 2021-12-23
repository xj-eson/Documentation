**获取文件页数**
==================================

**请求地址**

::

   POST https://api2.ctcfile.com/files/pages

**请求参数**

==== ====== ====== ==== ============
属性 类型   默认值 必填 说明
==== ====== ====== ==== ============
file binary        是   转换文件(流)
==== ====== ====== ==== ============

**返回值**

====== ======
类型   说明
====== ======
int    文件页数
====== ======


错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具| 调试该接口

.. |网页调试工具| raw:: html

   <a href="https://api2.ctcfile.com/swagger/index.html#/%E6%96%87%E4%BB%B6%E6%8E%A5%E5%8F%A3/post_files_pages" target="_blank">网页调试工具</a>