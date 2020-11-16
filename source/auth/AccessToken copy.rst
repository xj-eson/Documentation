**获取AccessToken**
------------------------------

获取全局唯一后台接口调用凭据（access_token）。调用绝大多数后台接口时都需使用
access_token，开发者需要进行妥善保存。


.. http:get:: /oauth/accesstoken?clientId=(clientId)&clientSecret=(clientSecret)

   **请求示例**

   .. sourcecode:: http

      GET /oauth/accesstoken?clientId=6zgY2DngtDjAq567k5sWfqJ6S01l&clientSecret=f6b24565-8566-32b6-120d-5a137a7110f8 HTTP/1.1
      Host: coresite.ctcfile.com
      Accept: application/json

   **响应示例**

   .. sourcecode:: http

      HTTP/1.1 200 OK
      Vary: Accept
      Content-Type: application/json

      {
         "token_type": "",
         "access_token": "eyJhbGciOiJSUzI1N43ImtpZCI6IjQ1RjYyMDIwNzhCNDQzMUZDNDI0NzdCNzk5QjZFQ0RCMUJCNzUzNkYiLCJ0eXAiOiJhdCtqd3QiLCJ4NX45SZllnSUhpMFF4X0VKSGUzbWJiczJ4dTNVMjgifQ.eyJuYmYiOjE2MDUyNDkxMDM54V4cCI6MTYwNTI1MjcwMywiaXNzIjoiaHR0cDovL2F1dGguc3ZjLnl4LmNvbSIsImF1ZCI6ImN0YyIsImNsaWVudF9pZCI6InpCM0tZMkRuZ3REakFxNTlLM2o5azVzV2ZxSjZTMDF65bmFtZSI6Im1pZ3VhbnhpYW9zaHVvIiwic3ViIjoiMjQzYjdjYjItNzk5OS00ODc2LTg4YTctOGIyMTEwZTg4MTBiIiwic3lzVXNlcklkIjoiMTU3MzUiLCJzY29wZSI6WyJjdGMiXX0.Sok8Q1mDOjpV22QMkpF31lbzKOjUBKP9sU7Nr90XeyBJVssgKa9-8f1XnSUO_Nk02g8PL5ylezDIEigpdRQKH_Jw4vzGDLch77PiQlztpId2Pajjse5bYI5lDAAn61AzDBYEYvmCz0buTg5ZAQtXKb3N6587bJidCCH64LXObGcTF-1P8LHZ19fmB97GefFbarXGU2QsNdMjIeOwl8_q83R16FmI3YFqxgpWIc3gXCi9PNZMVJy7iF4Tp8OgFiK68h32fkxT1KL_etUP4Wy4a-3KbWgYFa5ix_W3G_FLpkzvDIUuC7FgrAybBUdqtrLQiIEeWP5CRj3UzQxJA",
         "expires_in": 3600,
         "refresh_token": "",
         "errcode": "",
         "errmsg": ""
      }

   :query string clientId: 用户唯一凭证，即ClientID
   :query string clientSecret: 用户唯一凭证密钥
   
   :resjson string token_type: 凭证类型
   :resjson string access_token: 接口调用凭据
   :resjson int expires_in: 凭证有效时间，单位：秒，默认 3600秒 (1 小时)
   :resjson string errcode: 0: 请求成功，其他为错误码
   :resjson string errmsg: 错误信息

**access_token的应用、存储与更新**

-  在请求的 ``Header`` 中添加 ``authorization:"Bearer [access_token]"``
   进行验证；
-  ``access_token`` 的存储至少要保留 512 个字符空间；
-  ``access_token`` 的有效期目前为 **1**
   个小时，需定时刷新，重复获取将导致上次获取的 ``access_token`` 失效；
-  ``access_token`` 的有效期通过返回的 ``expires_in``
   来传达，目前是3600秒之内的值;
-  ``access_token`` 的有效时间可能会在未来有调整。
