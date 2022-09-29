**文本翻译**
==============

**请求地址**

::

   POST https://openapi.ctcfile.com/v1/translations/texts

**请求参数**

================= ====== ====== ==== ====================================
属性              类型   默认值 必填 说明
================= ====== ====== ==== ====================================
texts             array         是   翻译的内容(最大字符数为2000)
src_language_type string        是   原文本语种( :doc:`../overview/LanguageType`)
tgt_language_type string        是   目标语种( :doc:`../overview/LanguageType`)
other             string        否   其它信息.传递什么信息,返回同样的信息
================= ====== ====== ==== ====================================

**返回值**

================= ====== ====================================
属性              类型   说明
================= ====== ====================================
texts             array  翻译的内容
src_language_type string 原文本语种( :doc:`../overview/LanguageType`)
tgt_language_type string 目标语种( :doc:`../overview/LanguageType`)
other             string 其它信息.传递什么信息,返回同样的信息
================= ====== ====================================

**返回数据示例**

正常返回

.. code:: json


   {
     "src_language_type": "zs",
     "tgt_language_type": "en",
     "texts": [
       "hello"
     ],
     "other": ""
   }

错误时返回

   :doc:`../overview/StatusCode`
