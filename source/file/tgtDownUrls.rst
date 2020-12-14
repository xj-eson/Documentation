**译文下载地址**
=================

**请求地址**

::

   GET https://open.api.ctcfile.com/files/tgt-downurls

**请求参数**

========= ====== ====== ==== ====================================
属性      类型   默认值 必填 说明
========= ====== ====== ==== ====================================
id        int           是   文件ID
========= ====== ====== ==== ====================================

**返回数据示例**

正常返回

.. code:: json


   {
      "docx": "https://open.api.ctcfile.com/files/BAgfRvGEHSm3CN0yRcCYj3stair",
      "pdf": "https://open.api.ctcfile.com/files/BAgfRvGEHSm3CN0yRcCYj7MnrYFs"
   }

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具| 调试该接口

.. |网页调试工具| raw:: html
 
   <a href="https://open.api.ctcfile.com/swagger/index.html#/%E6%96%87%E4%BB%B6%E6%8E%A5%E5%8F%A3/get_files_tgt_downurls" target="_blank">网页调试工具</a>