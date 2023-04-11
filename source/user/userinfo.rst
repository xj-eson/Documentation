**用户信息**
==============

**请求地址**

::

   GET https://openapi.ctcfile.com/v1/users

**返回值**

=============================== ======== ====================================
属性                            类型      说明
=============================== ======== ====================================
id                              int      用户ID
username                        string   用户显示名称
organization_name               string   组织机构名称
organization_remain_words       int      组织机构剩余字数
organization_remain_pages       int      组织机构剩余PDF页数
organization_remain_image_pages int      组织机构剩余剩余图片页数
organization_date_due           datetime 组织机构到期日期
package_info                    object   套餐信息
============================= ======== ====================================

*package_info的结构*

============================= ======== ==============================================================================================================
属性                          类型     说明
============================= ======== ==============================================================================================================
package_total_words           int      套餐总字数
package_remain_words          int      套餐剩余字数
package_date_due              datetime 套餐到期时间
============================= ======== ==============================================================================================================


**返回数据示例**

正常返回

.. code:: json

   {
      "id": 1,
      "username": "yx",
      "organization_name": "yx",
      "organization_remain_words": 4022178,
      "organization_remain_pages": 5000,
      "organization_remain_image_pages":5000,
      "organization_date_due": "2021-09-20T15:59:59.999+00:00",
      "package_info": {
         "package_date_due": "2021-09-20T15:59:59.999+00:00",
         "package_total_words": 995821,
         "package_remain_words": 995640
      }
   }

错误时返回

   :doc:`../overview/StatusCode`
