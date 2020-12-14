**用户语言**
==============

**请求地址**

::

   GET https://open.api.ctcfile.com/users/languages

**返回值**

=========================== ====== ====================================
属性                        类型   说明
=========================== ====== ====================================
id                          int    ID
name                        string 名称
value                       string 语言标识值
english                     string 英语名
native                      string 本地名
=========================== ====== ====================================

**返回数据示例**

正常返回

.. code:: json

    [
        {
            "id": 0,
            "name": "中文(简体)",
            "value": "zh-Hans",
            "english": "Chinese",
            "native": "中文"
        },
        {
            "id": 10,
            "name": "英语"
            "value": "en",
            "english": "English",
            "native": "English"
        },
        {
            "id": 20,
            "name": "中文(繁体)",
            "value": "zh-Hant",
            "english": "Chinese",
            "native": "中文"
        },
        {
            "id": 30,
            "name": "俄语",
            "value": "ru",
            "english": "Russian",
            "native": "русский"
        }
    ]

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具| 调试该接口

.. |网页调试工具| raw:: html
 
   <a href="https://open.api.ctcfile.com/swagger/index.html#/%E7%94%A8%E6%88%B7%E6%9C%8D%E5%8A%A1/get_users_languages" target="_blank">网页调试工具</a>