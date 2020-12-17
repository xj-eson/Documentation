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

   POST https://open-api.ctcfile.com/translationss/file

**请求参数**

==== ====== ====== ==== ============
属性 类型   默认值 必填 说明
==== ====== ====== ==== ============
file binary        是   翻译文件(流)
data object        是   翻译参数
==== ====== ====== ==== ============

*data的结构*

================= ====== ====== ==== ==========================
属性              类型   默认值 必填 说明
================= ====== ====== ==== ==========================
src_language_type string        是   源语言语种(请查看 :doc:`../overview/LanguageType`)
tgt_language_type string        是   目标语言语种( :doc:`../overview/LanguageType`)
editable          int           是   文档可编辑 0:自动识别,1:可编辑,2:不可编辑
================= ====== ====== ==== ==========================

**返回值**

====== ======================
类型   说明
====== ======================
string 任务ID
====== ======================

**返回数据示例**

正常返回

.. code:: text


   "3fa85f64-5717-4562-b3fc-2c963f66afa6"

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具1| 调试该接口

.. |网页调试工具1| raw:: html
 
   <a href="https://open-api.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/post_translations_file" target="_blank">网页调试工具</a>

-----------------------------------------------------------


**2.根据任务ID获取任务信息**
----------------------------------

**请求地址**

::

   GET https://open-api.ctcfile.com/translations/tasks/{task_id}

**请求参数**

======= ====== ====== ==== ======
属性    类型   默认值 必填 说明
======= ====== ====== ==== ======
task_id string        是   任务ID
======= ====== ====== ==== ======

**返回值**

=============== ======== ==================
属性            类型     说明
=============== ======== ==================
task_id         string   任务ID
translate_info  object   基本信息
progress        object   翻译进度信息
=============== ======== ==================

*translate_info的结构*

================= ====== ========================
属性              类型   说明
================= ====== ========================
file_name         string 文件名称
src_language_type string 源文本语种( :doc:`../overview/LanguageType`)
tgt_language_type string 目标语种( :doc:`../overview/LanguageType`)
editable          int    文档可编辑 0:自动识别,1:可编辑,2:不可编辑
================= ====== ========================

*progress的结构*

================ ======== ============================================
属性             类型     说明
================ ======== ============================================
task_id          string   任务ID
task_status_type int      状态，包括0:进行中，1:完成，2:取消，3:错误
percent          double   进度值
file_lib_ids     array    文件id数组，需要根据此id获取翻译后的文件信息
error_code       string   :doc:`错误码 </../overview/StatusCode>`
error_msg        string   错误信息
create_time      datetime 开始时间
finish_time      datetime 完成时间
================ ======== ============================================

**返回数据示例**

正常返回

.. code:: json


   {
      "is_cancelled": false,
      "task_id": "66aa7ab0-b9ba-46fd-9a6e-e07dc14a6a11",
      "translate_info": {
         "file_name": "file.pdf",
         "src_language_type": "en",
         "type_language_type": "zs",
         "editable": 0
      },
      "progress": {
         "task_id": "66aa7ab0-b9ba-46fd-9a6e-e07dc14a6a11",
         "task_status_type": 1,
         "percent": 100,
         "file_lib_ids": [
            1
         ],
         "error_code": -1,
         "error_msg": null,
         "create_time": "2020-12-10T14:36:24.2084142+08:00",
         "finish_time": "2020-12-10T14:36:35.6994498+08:00"
      }
   }

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具2.1| 调试该接口

.. |网页调试工具2.1| raw:: html
 
   <a href="https://open-api.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/get_translations_tasks__task_id_" target="_blank">网页调试工具</a>

------------------------------------------------------

**3.获取所有任务翻译进度**
----------------------------

**请求地址**

::

   GET https://open-api.ctcfile.com/translations/tasks

**返回值**

``返回的结构为2接口的数组，如示例``

**返回数据示例**

正常返回

.. code:: json


   [
      {
         "is_cancelled": false,
         "task_id": "66aa7ab0-b9ba-46fd-9a6e-e07dc14a6a11",
         "translate_info": {
            "file_name": "file.pdf",
            "src_language_type": "en",
            "type_language_type": "zs",
            "editable": 0
         },
         "progress": {
            "task_id": "66aa7ab0-b9ba-46fd-9a6e-e07dc14a6a11",
            "task_status_type": 1,
            "percent": 100,
            "file_lib_ids": [
               1
            ],
            "error_code": -1,
            "error_msg": null,
            "create_time": "2020-12-10T14:36:24.2084142+08:00",
            "finish_time": "2020-12-10T14:36:35.6994498+08:00"
         }
      }
   ]

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具2.2| 调试该接口

.. |网页调试工具2.2| raw:: html
 
   <a href="https://open-api.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/get_translations_tasks" target="_blank">网页调试工具</a>

-------------------------------------------------------

**4.根据文件ID获取翻译后的文件**
--------------------------------

**请求地址**

::

   GET https://open-api.ctcfile.com/translations/tgt/{file_lib_id}

**请求参数**

=========== ==== ====== ==== ===========================
属性        类型 默认值 必填 说明
=========== ==== ====== ==== ===========================
file_lib_id int         是   文件ID
=========== ==== ====== ==== ===========================

**返回值**

====== ======
类型   说明
====== ======
stream 文件流
====== ======

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具3| 调试该接口

.. |网页调试工具3| raw:: html
 
   <a href="https://open-api.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/get_translations_tgt__file_lib_id_" target="_blank">网页调试工具</a>

-----------------------------------------------------------

**5.取消任务**
--------------

**请求地址**

::

   PATCH https://open-api.ctcfile.com/translations/tasks/{task_id}/cancel

**请求参数**

======= ====== ====== ==== ======
属性    类型   默认值 必填 说明
======= ====== ====== ==== ======
task_id string        是   任务ID
======= ====== ====== ==== ======

**返回数据示例**

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具5| 调试该接口

.. |网页调试工具5| raw:: html
 
   <a href="https://open-api.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/patch_translations_tasks__task_id__cancel" target="_blank">网页调试工具</a>