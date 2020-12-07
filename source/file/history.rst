**翻译历史文件**
=================

**请求地址**

::

   GET https://coresite.ctcfile.com/file

**请求参数**

========= ====== ====== ==== =====================================================================================
属性      类型   默认值 必填 说明
========= ====== ====== ==== =====================================================================================
name      string        否   文件名
fileTypes array         否   文件类型，包括 0:pdf,10:txt,20:docx,30:xlsx,40:pptx,50:odt,60:image,70:html,80:folder
pageIndex int    0      否   当前页数，默认从 0 开始
pageSize  int           是   每页显示多少条
========= ====== ====== ==== =====================================================================================

**返回值**

=========== ====== ====================================
属性        类型   说明
=========== ====== ====================================
result      array  数据
toltalCount int    总数量
=========== ====== ====================================

*result的结构*

======================== ========= ====================================
属性                     类型      说明
======================== ========= ====================================
id                       int       id
name                     string    文件名称
secretLevel              string    文件机密级别，包括 0:未设置密级,10:非密,20:内部,30:秘密,40:Confidential
fileType                 string    文件类型
downFileTypes            array     提供下载的文件类型
createTime               datetime  创建时间
srcLanguageType          string    源语种( :doc:`../overview/LanguageType`)
tgtLanguageType          string    目标语种( :doc:`../overview/LanguageType`)
tgtFileSize              int       翻译后文件大小
consumeWordsTotalCount   int       消费字数
isCollect                int       0:未收藏,1:收藏
======================== ========= ====================================


**返回数据示例**

正常返回

.. code:: json


   {
    "result": [
        {
        "id": 1,
        "name": "002-英译中PDF.pdf",
        "fileType": "pdf",
        "secretLevel": "notSet",
        "downFileTypes": [
            "docx",
            "pdf"
        ],
        "createTime": "2020-12-07T02:54:20.090822+00:00",
        "srcLanguageType": "en",
        "tgtLanguageType": "zs",
        "tgtFileSize": 163125,
        "createTimeDesc": "2020-12-07 02:54:20",
        "consumeWordsTotalCount": 3210,
        "isCollect": 0
        }
    ],
    "toltalCount": 8
    }

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具| 调试该接口

.. |网页调试工具| raw:: html
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/post_translation_texts" target="_blank">网页调试工具</a>