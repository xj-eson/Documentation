**译文下载地址**
=================

**请求地址**

::

   GET https://transapi.dl.wiki/files/tgt-downurls

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
      "docx": "https://transapi.dl.wiki/files/BAgfRvGEHSm3CN0yRcCYj3stair",
      "pdf": "https://transapi.dl.wiki/files/BAgfRvGEHSm3CN0yRcCYj7MnrYFs"
   }

错误时返回

   :doc:`../overview/StatusCode`
