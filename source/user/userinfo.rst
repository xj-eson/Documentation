**用户信息**
==============

**请求地址**

::

   GET https://coresite.ctcfile.com/users

**返回值**

============================= ====== ====================================
属性                          类型   说明
============================= ====== ====================================
id                            int    用户ID
user_name                     string 用户显示名称
normalized_user_name          string 登录用户名
email                         string 用户邮箱
phone                         string 用户电话
organization_name             string 组织机构名称
organization_remain_words     string 组织机构剩余字数
organization_date_due         string 组织机构到期日期
============================= ====== ====================================

**返回数据示例**

正常返回

.. code:: json

   {
      "id": 1,
      "user_name": "yx",
      "normalized_user_name": "yx",
      "email": "",
      "phone": "",
      "organization_name": "yx",
      "organization_remain_words": 4022178,
      "organization_date_due": "2021-09-20T15:59:59.999+00:00"
   }

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具| 调试该接口

.. |网页调试工具| raw:: html
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E7%94%A8%E6%88%B7%E6%9C%8D%E5%8A%A1/get_users" target="_blank">网页调试工具</a>