**用户信息**
==============

**请求地址**

::

   GET https://coresite.ctcfile.com/user

**返回值**

=========================== ====== ====================================
属性                        类型   说明
=========================== ====== ====================================
id                          int    用户ID
userName                    string 用户显示名称
normalizedUserName          string 登录用户名
normalizedEmail             string 用户邮箱
phoneNumber                 string 用户电话
organizationName            string 组织机构名称
organizationRemainWords     string 组织机构剩余字数
organizationDateDue         string 组织机构到期日期
=========================== ====== ====================================

**返回数据示例**

正常返回

.. code:: json

    {
    "id": 1,
    "userName": "yx",
    "normalizedUserName": "yx",
    "normalizedEmail": "",
    "phoneNumber": "",
    "organizationName": "yx",
    "organizationRemainWords": 4035024,
    "organizationDateDue": "2021-09-20T15:59:59.999+00:00"
    }

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具| 调试该接口

.. |网页调试工具| raw:: html
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E7%94%A8%E6%88%B7%E6%9C%8D%E5%8A%A1/get_user" target="_blank">网页调试工具</a>