**获取调用凭证**
------------------------------

获取全局唯一后台接口调用凭据（access_token）。调用绝大多数后台接口时都需使用
access_token，开发者需要进行妥善保存。


**请求地址**

::

   GET https://open.api.ctcfile.com/oauth/access-token

**请求参数**

============== ====== ====== ==== ========================
属性           类型   默认值 必填  说明
============== ====== ====== ==== ========================
client_id      string         是  用户唯一凭证，即ClientID
client_secret  string         是  用户唯一凭证密钥
============== ====== ====== ==== ========================

**返回值**

============= ====== ==========================================
属性          类型   说明
============= ====== ==========================================
token_type    string 凭证类型
access_token  string 接口调用凭据
expires_in    string 凭证有效时间，单位：秒，默认 7200 (2 小时)
refresh_token string 刷新凭证
============= ====== ==========================================

**返回数据示例**

正常返回

.. code:: json

   {
    "token_type": "",
    "access_token": "ACCESS_TOKEN",
    "expires_in": 3600,
    "refresh_token": "REFRESH_TOKEN"
   }

错误时返回

   :doc:`../overview/StatusCode`

**access_token的应用、存储与更新**

-  在请求的 ``Header`` 中添加 ``authorization:"Bearer {access_token}"``
   进行验证；
-  ``access_token`` 的存储至少要保留 512 个字符空间；
-  ``access_token`` 的有效期目前为 **1**
   个小时，需定时刷新，重复获取将导致上次获取的 ``access_token`` 失效；
-  ``access_token`` 的有效期通过返回的 ``expires_in``
   来传达，目前是3600秒之内的值;
-  ``access_token`` 的有效时间可能会在未来有调整。

**在线调试**


开发者可以使用 |网页调试工具| 调试该接口

.. |网页调试工具| raw:: html

   <a href="https://open.api.ctcfile.com/swagger/index.html#/%E6%8E%A5%E5%8F%A3%E8%B0%83%E7%94%A8%E5%87%AD%E8%AF%81/get_oauth_access_token" target="_blank">网页调试工具</a>