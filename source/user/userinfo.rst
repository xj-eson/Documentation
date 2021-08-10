**用户信息**
==============

**请求地址**

::

   GET https://transapi.dl.wiki:30120/users

**返回值**

============================= ======== ====================================
属性                          类型     说明
============================= ======== ====================================
id                            int      用户ID
username                      string   用户显示名称
normalized_username           string   登录用户名
email                         string   用户邮箱
phone                         string   用户电话
organization_name             string   组织机构名称
organization_remain_words     int      组织机构剩余字数
organization_date_due         datetime 组织机构到期日期
package_info                  object   套餐信息
============================= ======== ====================================

*package_info的结构*

============================= ======== ==============================================================================================================
属性                          类型     说明
============================= ======== ==============================================================================================================
package_total_words           int      套餐总字数
package_remain_words          int      套餐剩余字数
package_pricing               int      套餐支付方式，包括0:通用，10:字数计价，30:时间计价，40:字数月套餐，50:字数年计价，60:字数月套餐，70:字数年计价
package_date_due              datetime 套餐到期时间
============================= ======== ==============================================================================================================


**返回数据示例**

正常返回

.. code:: json

   {
      "id": 1,
      "username": "yx",
      "normalized_username": "yx",
      "email": "",
      "phone": "",
      "organization_name": "yx",
      "organization_remain_words": 4022178,
      "organization_date_due": "2021-09-20T15:59:59.999+00:00",
      "package_info": {
         "package_date_due": "2021-09-20T15:59:59.999+00:00",
         "package_total_words": 995821,
         "package_remain_words": 995640,
         "package_pricing": 0
      }
   }

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具| 调试该接口

.. |网页调试工具| raw:: html
 
   <a href="https://transapi.dl.wiki:30120/swagger/index.html#/%E7%94%A8%E6%88%B7%E6%9C%8D%E5%8A%A1/get_users" target="_blank">网页调试工具</a>