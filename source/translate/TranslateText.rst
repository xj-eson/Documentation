**文本翻译**
==============

**请求地址**

::

   POST https://coresite.ctcfile.com/Translate/TranslateTexts

**请求参数**

===== ====== ====== ==== ====================================
属性  类型   默认值 必填 说明
===== ====== ====== ==== ====================================
texts array         是   翻译的内容
sl    string        是   源文本语种( :doc:`../overview/LanguageType`)
tl    string        是   目标语种( :doc:`../overview/LanguageType`)
other string        否   其它信息.传递什么信息,返回同样的信息
===== ====== ====== ==== ====================================

**返回值**

===== ====== ====================================
属性  类型   说明
===== ====== ====================================
texts array  翻译的内容
sl    string 源文本语种( :doc:`../overview/LanguageType`)
tl    string 目标语种( :doc:`../overview/LanguageType`)
other string 其它信息.传递什么信息,返回同样的信息
===== ====== ====================================

**返回数据示例**

正常返回

.. code:: json


   {
     "sl": "zs",
     "tl": "en",
     "texts": [
       "hello"
     ],
     "other": ""
   }

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具| 调试该接口

.. |网页调试工具| raw:: html
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E7%BF%BB%E8%AF%91%E6%8E%A5%E5%8F%A3/post_Translate_TranslateTexts" target="_blank">网页调试工具</a>