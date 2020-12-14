**翻译历史文件**
=================

**请求地址**

::

   GET https://open.api.ctcfile.com/files

**请求参数**

========== ====== ====== ==== =====================================================================================
属性       类型   默认值 必填 说明
========== ====== ====== ==== =====================================================================================
name       string        否   文件名
file_types array         否   文件类型，包括 0:pdf,10:txt,20:docx,30:xlsx,40:pptx,50:odt,60:image,70:html,80:folder
pageIndex  int    0      否   当前页数，默认从 0 开始
pageSize   int           是   每页显示多少条
========== ====== ====== ==== =====================================================================================

**返回值**

============ ====== ====================================
属性         类型   说明
============ ====== ====================================
result       array  数据
toltal_count int    总数量
============ ====== ====================================

*result的结构*

============================ ========= ====================================
属性                         类型      说明
============================ ========= ====================================
id                           int       id
name                         string    文件名称
secret_level                 string    文件机密级别，包括 0:未设置密级,10:非密,20:内部,30:秘密,40:Confidential
file_type                    string    文件类型
down_file_types              array     提供下载的文件类型
create_time                  datetime  创建时间
src_language_type            string    源语种( :doc:`../overview/LanguageType`)
tgt_language_type            string    目标语种( :doc:`../overview/LanguageType`)
tgt_file_size                int       翻译后文件大小
consume_words_total_count    int       消费字数
is_collect                   int       0:未收藏,1:收藏
============================ ========= ====================================


**返回数据示例**

正常返回

.. code:: json


   {
      "result": [
         {
            "id": 0,
            "name": "file.pdf",
            "file_type": "Pdf",
            "secret_level": "notSet",
            "down_file_types": [
               "docx",
               "pdf"
            ],
            "create_time": "2020-12-10T06:23:38.921Z",
            "src_language_type": "en",
            "tgt_language_type": "zs",
            "tgt_file_size": 163125,
            "consume_words_total_count": 3210,
            "is_collect": 0
         }
      ],
      "toltalCount": 1
   }

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具| 调试该接口

.. |网页调试工具| raw:: html
 
   <a href="https://open.api.ctcfile.com/swagger/index.html#/%E6%96%87%E4%BB%B6%E6%8E%A5%E5%8F%A3/get_files" target="_blank">网页调试工具</a>