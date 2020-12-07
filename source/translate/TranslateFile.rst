**文件翻译**
============

.. raw:: html

   <!-- ![文件翻译流程图](/img/1604991035269translate-file-process.jpg) -->

流程图
------

.. figure:: /_static/translate-file-process.jpg
   :alt: 文件翻译流程图

**1.文件翻译**
--------------

**请求地址**

::

   POST https://coresite.ctcfile.com/translation/file

**请求参数**

==== ====== ====== ==== ============
属性 类型   默认值 必填 说明
==== ====== ====== ==== ============
file binary        是   翻译文件(流)
data object        是   翻译参数
==== ====== ====== ==== ============

*data的结构*

=============== ====== ====== ==== ==========================
属性            类型   默认值 必填 说明
=============== ====== ====== ==== ==========================
fileName        string        是   文件名
srcLanguageType string        是   源语言语种(请查看 :doc:`../overview/LanguageType`)
tgtLanguageType string        是   目标语言语种( :doc:`../overview/LanguageType`)
editable        bool          是   文档是否可编辑 null:自动识别 true:可编辑 false:不可编辑
=============== ====== ====== ==== ==========================

**返回值**

====== ====== ======================
属性   类型   说明
====== ====== ======================
taskId string 任务ID（具体请看示例）
====== ====== ======================

**返回数据示例**

正常返回

.. code:: text


   "3fa85f64-5717-4562-b3fc-2c963f66afa6"

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具1| 调试该接口

.. |网页调试工具1| raw:: html
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/post_translation_file" target="_blank">网页调试工具</a>

-----------------------------------------------------------


**2.根据任务ID获取任务信息**
----------------------------------

**请求地址**

::

   GET https://coresite.ctcfile.com/translation/tasks/[taskId]

**请求参数**

====== ====== ====== ==== ======
属性   类型   默认值 必填 说明
====== ====== ====== ==== ======
taskId string        是   任务ID
====== ====== ====== ==== ======

**返回值**

============== ======== ==================
属性           类型     说明
============== ======== ==================
taskId         string   任务ID
translateInfo  object   基本信息
progress       object   翻译进度信息
============== ======== ==================

*translateInfo的结构*

=============== ====== ========================
属性            类型   说明
=============== ====== ========================
fileName        string 文件名称
secretLevel     int    机密级别，包括 0:未设置密级,10:非密,20:内部,30:秘密,40:机密
srcLanguageType string 源文本语种( :doc:`../overview/LanguageType`)
tgtLanguageType string 目标语种( :doc:`../overview/LanguageType`)
=============== ====== ========================

*progress的结构*

============== ======== ============================================
属性           类型     说明
============== ======== ============================================
taskId         string   任务ID
taskStatusType int      状态，包括0:进行中，1:完成，2:取消，3:错误
fileLibIds     array    文件id数组，需要根据此id获取翻译后的文件信息
percent        double   进度值
errorCode      int      :doc:`错误码 </../overview/StatusCode>`
createTime     datetime 开始时间
finishTime     datetime 完成时间
============== ======== ============================================

**返回数据示例**

正常返回

.. code:: json


   {
      "isCancelled": false,
      "taskId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
      "translateInfo": {
         "fileName": "string",
         "srcLanguageType": "zs",
         "tgtLanguageType": "zs",
         "editable": true
      },
      "progress": {
         "taskId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
         "taskStatusType": "Progressing",
         "percent": 0,
         "fileLibIds": [
            0
         ],
         "errorCode": -1,
         "createTime": "2020-12-07T02:11:18.512Z",
         "finishTime": "2020-12-07T02:11:18.512Z"
      }
   }

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具2.1| 调试该接口

.. |网页调试工具2.1| raw:: html
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/get_translation_tasks__taskId_" target="_blank">网页调试工具</a>

------------------------------------------------------

**3.获取所有任务翻译进度**
----------------------------

**请求地址**

::

   GET https://coresite.ctcfile.com/translation/tasks

**返回值**

``返回的结构为2接口的数组，如示例``

**返回数据示例**

正常返回

.. code:: json


   [
      {
         "isCancelled": false,
         "taskId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
         "translateInfo": {
            "fileName": "string",
            "srcLanguageType": "zs",
            "tgtLanguageType": "zs",
            "editable": true
         },
         "progress": {
            "taskId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
            "taskStatusType": "Progressing",
            "percent": 0,
            "fileLibIds": [
            0
            ],
            "errorCode": -1,
            "createTime": "2020-12-07T02:11:18.501Z",
            "finishTime": "2020-12-07T02:11:18.501Z"
         }
      }
   ]

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具2.2| 调试该接口

.. |网页调试工具2.2| raw:: html
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/get_translation_tasks" target="_blank">网页调试工具</a>

-------------------------------------------------------

**4.根据文件ID获取翻译后的文件**
--------------------------------

**请求地址**

::

   GET https://coresite.ctcfile.com/translation/tgtFile/[fileLibId]

**请求参数**

========= ==== ====== ==== ===========================
属性      类型 默认值 必填 说明
========= ==== ====== ==== ===========================
fileLibId int         是   接口2返回的fileLibIds字段值
========= ==== ====== ==== ===========================

**返回值**

====== ====== ======
属性   类型   说明
====== ====== ======
stream stream 文件流
====== ====== ======

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具3| 调试该接口

.. |网页调试工具3| raw:: html
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/get_translation_tgtFile__fileLibId_" target="_blank">网页调试工具</a>

-----------------------------------------------------------

**6.取消任务**
--------------

**请求地址**

::

   DELETE https://coresite.ctcfile.com/translation/cancel/[taskId]

**请求参数**

====== ====== ====== ==== ======
属性   类型   默认值 必填 说明
====== ====== ====== ==== ======
taskId string        是   任务ID
====== ====== ====== ==== ======

**返回数据示例**

正常返回

.. code:: json

   true

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具5| 调试该接口

.. |网页调试工具5| raw:: html
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/put_translation_cancel__taskId_" target="_blank">网页调试工具</a>