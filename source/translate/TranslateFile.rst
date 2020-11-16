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

   POST https://coresite.ctcfile.com/Translate/TranslateFile

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
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/post_Translate_TranslateFile" target="_blank">网页调试工具</a>

-----------------------------------------------------------


**2.根据任务ID获取任务翻译进度**
----------------------------------

**请求地址**

::

   GET https://coresite.ctcfile.com/Translate/GetProgress

**请求参数**

====== ====== ====== ==== ======
属性   类型   默认值 必填 说明
====== ====== ====== ==== ======
taskId string        是   任务ID
====== ====== ====== ==== ======

**返回值**

============== ======== ============================================
属性           类型     说明
============== ======== ============================================
taskId         string   任务ID
taskStatusType int      状态，包括0:进行中，1:完成，2:取消，3:错误
fileLibIds     array    文件id数组，需要根据此id获取翻译后的文件信息
percent        double   进度值
errMsg         string   错误信息
createTime     datetime 开始时间
finishTime     datetime 完成时间
============== ======== ============================================

**返回数据示例**

正常返回

.. code:: json


   {
     "taskId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
     "taskStatusType": "0",
     "percent": 50.00,
     "fileLibIds": [
       0
     ],
     "errMsg": "string",
     "createTime": "2020-09-16T05:20:05.004Z",
     "finishTime": "2020-09-16T05:20:05.004Z"
   }

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具2.1| 调试该接口

.. |网页调试工具2.1| raw:: html
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/get_Translate_GetProgress__taskId_" target="_blank">网页调试工具</a>

------------------------------------------------------

**3.获取所有任务翻译进度**
----------------------------

**请求地址**

::

   GET https://coresite.ctcfile.com/Translate/GetProgress

**返回值**

``返回的结构为2接口的数组，如示例``

**返回数据示例**

正常返回

.. code:: json


   [
     {
       "taskId": "3fa85f64-5717-4562-b3fc-2c963f66afa6",
       "taskStatusType": "0",
       "percent": 50.00,
       "fileLibIds": [
         0
       ],
       "errMsg": "",
       "createTime": "2020-11-16T15:20:05.004Z",
       "finishTime": "2020-11-16T15:20:05.004Z"
     },
     {
       "taskId": "f6640589-33a8-4ee3-a013-46f47ad0cd29",
       "taskStatusType": "1",
       "percent": 100.00,
       "fileLibIds": [
         100
       ],
       "errMsg": "",
       "createTime": "2020-11-16T15:30:05.004Z",
       "finishTime": "2020-11-16T15:30:05.004Z"
     }
   ]

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具2.2| 调试该接口

.. |网页调试工具2.2| raw:: html
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/get_Translate_GetProgress__taskId_" target="_blank">网页调试工具</a>

-------------------------------------------------------

**4.根据文件ID获取翻译后的文件**
--------------------------------

**请求地址**

::

   GET https://coresite.ctcfile.com/Translate/GetTgtFile

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
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/get_Translate_GetTgtFile__fileLibId_" target="_blank">网页调试工具</a>

--------------


**5.获取正在运行的任务详细信息**
--------------------------------

**请求地址**

::

   GET https://coresite.ctcfile.com/Translate/GetTasks

**返回值**

=========== ====== ============
属性        类型   说明
=========== ====== ============
isCancelled bool   任务是否取消
inputParam  object 基础信息
progress    object 翻译进度
=========== ====== ============

*inputParam的结构*

=============== ====== ========================
属性            类型   说明
=============== ====== ========================
fileName        string 文件名称
secretLevel     int    机密级别，包括 0:未设置密级,10:非密,20:内部,30:秘密,40:机密
srcLanguageType int    源文本语种( :doc:`../overview/LanguageType`)
tgtLanguageType int    目标语种( :doc:`../overview/LanguageType`)
=============== ====== ========================

*progress的结构*

``见2返回值结构``

**返回数据示例**

正常返回

.. code:: json


   [
     {
       "isCancelled": false,
       "inputParam": {
         "fileName": "test.pdf",
         "secretLevel": 0,
         "srcLanguageType": 0,
         "tgtLanguageType": 10
       },
       "progress": {
         "taskId": "0c5e5a60-25a1-49e2-a7f4-657875b6e87f",
         "taskStatusType": 3,
         "percent": 35.84,
         "fileLibIds": [],
         "errMsg": "您的剩余字数已不够",
         "createTime": "2020-11-10T14:09:21.1013329+08:00",
         "finishTime": null
       }
     },
     {
       "isCancelled": false,
       "inputParam": {
         "fileName": "test1.pdf",
         "secretLevel": 0,
         "srcLanguageType": 0,
         "tgtLanguageType": 10
       },
       "progress": {
         "taskId": "f6640589-33a8-4ee3-a013-46f47ad0cd29",
         "taskStatusType": 3,
         "percent": 5,
         "fileLibIds": [],
         "errMsg": "翻译失败,请重试",
         "createTime": "2020-11-10T14:19:09.8947673+08:00",
         "finishTime": null
       }
     },
     {
       "isCancelled": false,
       "inputParam": {
         "fileName": "test2.pdf",
         "secretLevel": 0,
         "srcLanguageType": 0,
         "tgtLanguageType": 10
       },
       "progress": {
         "taskId": "e6d05ab0-78cf-407d-be3e-95da1347586b",
         "taskStatusType": 3,
         "percent": 5,
         "fileLibIds": [],
         "errMsg": "翻译失败,请重试",
         "createTime": "2020-11-10T14:19:46.9171417+08:00",
         "finishTime": null
       }
     }
   ]

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具4| 调试该接口

.. |网页调试工具4| raw:: html
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/get_Translate_GetProgress__taskId_" target="_blank">网页调试工具</a>

-----------------------------------------------------------

**6.取消任务**
--------------

**请求地址**

::

   GET https://coresite.ctcfile.com/Translate/CancelTask/[taskId]

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
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/get_Translate_CancelTask__taskId_" target="_blank">网页调试工具</a>