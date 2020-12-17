**获取文件链接**
=====================

**请求地址**

::

   GET https://open-api.ctcfile.com/File/GetOpenLink

**请求参数**

==== ==== ====== ==== ======================================
属性 类型 默认值 必填 说明
==== ==== ====== ==== ======================================
Id   int         是   文件ID
==== ==== ====== ==== ======================================

**返回值**

======= ====== ==========
属性    类型   说明
======= ====== ==========
srcView object 源文件信息
tgtView object 译文件信息
======= ====== ==========

*srcView的结构*

============ ====== ===============================
属性         类型   说明
============ ====== ===============================
name         string 文件名称
docTitle     string 文档标题
path         string 文档路径
type         string 文档类型
content      string 内容(当文档为txt时，该字段有值)
downloadLink string 下载链接
downloadName string 下载文件名
canDownload  bool   是否可下载
============ ====== ===============================

*tgtView的结构*

同srcView结构

**返回数据示例**

正常返回

.. code:: json

   {
     "srcView": {
       "name": "源文件名.pdf",
       "docTitle": "原文",
       "path": "/GetFile/LrXy6wQ0v9d1yOdu1cmKYOjsNBEhGAKfu_OXUjXPyX3GgxvYbUhajp4QTbWwXDNJyGZZ9nlQyHjW1LwHmd1CnbFopo2_9B0Tq_DPvA9yhWP0ZP5LU99YsHHotTC18hntQiPJ_hEcRdN-69oQ0pwhe3yJdmTLP29XtLJmZudSFLbDLRC4uM3xSqIzrAgxtnS",
       "type": "application/pdf",
       "content": null,
       "downloadLink": "/GetFile/LrXy6wQ0v9d1yOdu1cmKYOjsNBEhGAKfu_OXUjXPyX3GgxvYbUhajp4QTbWwXDNJyGZZ9nlQyHjW1LwHmd1CnbFopo2_9B0Tq_DPvA9yhWP0ZP5LU99YsHHotTC18hntQiPJ_hEcRdN-69oQ0pwhe3yJdmTLP29XtLJmZudSFLbDLRC4uM3xSqIzrAgxtnS",
       "downloadName": "源文件名.pdf",
       "canDownload": true
     },
     "tgtView": {
       "name": "译文件名(zs_en).pdf",
       "docTitle": "译文",
       "path": "/GetFile/s-S9EZQSLgQht-8wDYd3xKriLr40HgHazupne2pntVJLElRvUtz4emItO7UQbjbuBA4lVTWQed3O9TsJVri9-wgKFvwKe6f-dail8vji5NRyibBWwdGW9ZdV8JXZnXKxdFsb9zdJ7AAD4thksjBjwiFFSK_-mi34SbI3SbLV5zCSvVwTuwVUsNocNFJgycu5qulAJT9eqzFFgXbxTe63sNNw",
       "type": "application/pdf",
       "content": null,
       "downloadLink": "/GetFile/s-S9EZQSLgQht-8wDYd3xKriLr40HgHazupne2pntVJLElRvUtz4emItO7UQbjbuBA4lVTWQed3O9TsJVri9-wgKFvwKe6f-dail8vji5NRyibBWwdGW9ZdV8JXZnXKxdFsb9zdJ7AAD4thksjBjwiFFSK_-mi34SbI3SbLV5zCSvVwTuwVUsNocNFJgycu5qulAJT9eqzFFgXbxTe63sNNw",
       "downloadName": "译文件名(zs_en).docx",
       "canDownload": true
     }
   }

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具| 调试该接口

.. |网页调试工具| raw:: html

  <a href="https://open-api.ctcfile.com/swagger/index.html#/%E6%96%87%E4%BB%B6%E6%8E%A5%E5%8F%A3/get_File_GetOpenLink" target="_blank">网页调试工具</a>