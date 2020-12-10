**用户的领域类型**
====================

**请求地址**

::

   GET https://coresite.ctcfile.com/users/domain-types

**返回值**

=========================== ====== ====================================
属性                        类型   说明
=========================== ====== ====================================
id                          int    ID
name                        string 领域名称
=========================== ====== ====================================

**返回数据示例**

正常返回

.. code:: json

    [
        {
            "id": 6,
            "name": "通用版"
        }
    ]

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具| 调试该接口

.. |网页调试工具| raw:: html
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E7%94%A8%E6%88%B7%E6%9C%8D%E5%8A%A1/get_users_domain_types" target="_blank">网页调试工具</a>