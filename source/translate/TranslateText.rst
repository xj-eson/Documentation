**文本翻译**
==============

**请求地址**

::

   POST https://openapi.ctcfile.com/v1/translations/texts

**请求参数**

================= ====== ====== ==== ====================================
属性              类型   默认值 必填 说明
================= ====== ====== ==== ====================================
texts             array         是   需要翻译的内容
src_language_type string        否   源语种类型。如未指定，将自动检测( :doc:`../overview/LanguageType`)
tgt_language_type string        是   目标语种类型( :doc:`../overview/LanguageType`)
other             string        否   其它信息，传递的内容将原样返回
properties        dict          否   属性(详见下方示例)
================= ====== ====== ==== ====================================

*properties参数示例*

=================================== ============
属性名                               属性值
=================================== ============
options:text_translate_retain_emoji 1:保留Emoji
options:text_translate_retain_url   1:保留URL
=================================== ============


**参数示例**

.. code:: json


   {
     "src_language_type": "en",
     "tgt_language_type": "zs",
     "texts": [
       "hello"
     ],
     "other": "",
     "properties": {
       "options:text_translate_retain_emoji": "1",
       "options:text_translate_retain_url": "1"
     }
   }


**返回值**

================= ====== ====================================
属性              类型   说明
================= ====== ====================================
texts             array  翻译后的内容
src_language_type string 源语种类型( :doc:`../overview/LanguageType`)
tgt_language_type string 目标语种类型( :doc:`../overview/LanguageType`)
other             string 其它信息，传递的内容将原样返回
================= ====== ====================================

**返回数据示例**

正常返回

.. code:: json


   {
     "src_language_type": "zs",
     "tgt_language_type": "en",
     "texts": [
       "你好"
     ],
     "other": ""
   }

错误时返回

   :doc:`../overview/StatusCode`
