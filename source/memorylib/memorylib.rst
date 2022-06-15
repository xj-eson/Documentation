**用户的语料库**
====================

1. 子用户
---------

**1.1. 创建子用户**

请求地址

   POST `https://openapi.ctcfile.com/api/User/CreateThirdPartyUser`_

请求参数

   ================ ===== ====== ===========================================
   参数              必选  类型   说明
   ================ ===== ====== ===========================================
   authorization    true  string Header 参数，“Bearer” + client access_token
   thirdPartyUserId true  string 第三方平台子用户 Id
   phone            false string 电话号码
   email            false string 邮箱
   name             false string 姓名（请传正式名称，用于聊天展示姓名）
   company          false string 公司
   ================ ===== ====== ===========================================

返回字段

   ========= ======== =======================================
   返回字段  字段类型 说明
   ========= ======== =======================================
   isSuccess bool     返回结果状态。true：成功；false：失败。
   msg       string   若创建用户失败，返回错误信息
   ========= ======== =======================================

..

   正常返回

   .. code:: json

      {
       "isSuccess": true,
       "msg": ""
      }

**1.2. 获取子用户Token**

.. _请求地址-1:

请求地址

   GET `https://openapi.ctcfile.com/api/User/GetIdentityToken`_

.. _请求参数-1:

请求参数

   ================ ==== ====== ===========================================
   参数             必选 类型   说明
   ================ ==== ====== ===========================================
   authorization    true string Header 参数，“Bearer” + client access_token
   thirdPartyUserId true string 第三方平台子用户 Id
   ================ ==== ====== ===========================================

.. _返回字段-1:

返回字段

   ============= ======== =========================================
   返回字段      字段类型 说明
   ============= ======== =========================================
   token_type    string   凭证类型
   access_token  string   接口调用凭据
   expires_in    int      凭证有效期，单位：秒，默认 864000 (10 天)
   refresh_token string   刷新 token 凭证
   errcode       int      0: 请求成功，其他为错误码
   errmsg        string   错误信息
   ============= ======== =========================================

..

   正常返回

   .. code:: json

      {
       "token_type": "",
       "access_token": "abcd666……",
       "expires_in": 864000,
       "refresh_token": "ab567……",
       "errcode": "",
       "errmsg": ""
      }

**1.3. 获取 第三方用户Id 对应的 用户Id**

.. _请求地址-2:

请求地址

   GET `https://openapi.ctcfile.com/api/User/GetUserInfo`_

.. _请求参数-2:

请求参数

   ================ ==== ====== ===========================================
   参数             必选 类型   说明
   ================ ==== ====== ===========================================
   authorization    true string Header 参数，“Bearer” + client access_token
   thirdPartyUserId true string 第三方平台子用户 Id
   ================ ==== ====== ===========================================

.. _返回字段-2:

返回字段

   ========= ======== =======================================
   返回字段  字段类型 说明
   ========= ======== =======================================
   isSuccess bool     返回结果状态。true：正常；false：错误。
   msg       string   若充值失败，则返回错误信息
   data      object   用户 Id，用于创建聊天
   ========= ======== =======================================

..
   【data 内容字段说明】
   ========= ======== =======================================
   返回字段  字段类型 说明
   ========= ======== =======================================
   openId    string   第三方用户 Id 对应的用户 id
   ========= ======== =======================================

   正常返回

   .. code:: json

      {
       "isSuccess": true,
       "msg": "",
       "data": {
           "openId": "0a26d350-8955-4363-ad15-f96ecc57678b"
        }
      }

2. 创建私有云库
---------------

**2.1. 获取 专业领域**

请求地址
        

   GET `https://api.ctcfile.com/api/Goods/GetAllLabelsAsyncl`_

返回值
      

   ======== ======== ==========================================
   返回字段 字段类型 说明
   ======== ======== ==========================================
   id       long     专业领域id
   depth    int      专业领域层级深度
   content  string   专业领域名称
   domains  array    子领域集合，字段相同
   ======== ======== ==========================================

返回数据示例
            

   正常返回

   .. code:: json

      [
        {
         "id": "272",
         "depth": 0,
         "content": "通用",
         "domains": null,
        },
        {
         "id": "273",
         "depth": 0,
         "content": "军事作战",
         "domains": null,
        }
      ]

**2.2. 创建私有云库**

.. _请求地址-1:

请求地址
        

   POST `https://api.ctcfile.com/api/MemoryLib/AddMemoryLibAsync`_

请求参数
        

   ======== ==== ==== ==========
   参数     必选 类型 说明
   ======== ==== ==== ==========
   domainId true long 专业领域Id
   ======== ==== ==== ==========

.. _返回值-1:

返回值
      

   ============ ======== ==========
   返回字段     字段类型 说明
   ============ ======== ==========
   isSuccess    bool     是否成功
   data         long     私有云库Id
   errorMessage string   错误信息
   ============ ======== ==========

.. _返回数据示例-1:

返回数据示例
            

   正常返回

   .. code:: json

      {
       "isSuccess": true,
       "data": 3787,
       "errorMessage": ""
      }

**2.3. 获取支持的语种**

.. _请求地址-2:

请求地址
        

   GET `https://api.ctcfile.com/api/App/GetLanguages`_

.. _返回值-2:

返回值
      

   ======== ======== ================
   返回字段 字段类型 说明
   ======== ======== ================
   id       long     语种Id
   value    string   语种的代码值
   name     string   语种的名称(中文)
   english  string   语种的名称(英文)
   native   string   语种的名称(母语)
   selected bool     是否已经选择过
   ======== ======== ================

.. _返回数据示例-2:

返回数据示例
            

   正常返回

   .. code:: json

      [
        {
         "id": 30,
         "value": "ru",
         "name": "俄语",
         "english": "Russian",
         "native": "русский",
         "selected": false,
        },
        {
         "id": 50,
         "value": "ko",
         "name": "韩语",
         "english": "Korean",
         "native": "한국어",
         "selected": false,
        }
      ]

**2.4. 添加语料**

.. _请求地址-3:

请求地址
        

   POST
   `https://api.ctcfile.com/api/MemoryLib/AddOrUpdateMemoryItemAsync`_

.. _请求参数-1:

请求参数
        

   =============== ==== ====== ============
   参数            必选 类型   说明
   =============== ==== ====== ============
   memoryLibId     true long   私有云库Id
   srcLanguageType true int    源语言
   srcContent      true string 源语言内容
   tgtLanguageType true int    目标语言
   tgtContent      true string 目标语言内容
   =============== ==== ====== ============

.. _返回值-3:

返回值
      

   ============ ======== ========
   返回字段     字段类型 说明
   ============ ======== ========
   isSuccess    bool     是否成功
   errorMessage string   错误信息
   ============ ======== ========

.. _返回数据示例-3:

返回数据示例
            

   正常返回

   .. code:: json

      {
       "isSuccess": true,
       "errorMessage": ""
      }

.. _`https://openapi.ctcfile.com/api/User/CreateThirdPartyUser`: 
.. _`https://openapi.ctcfile.com/api/User/GetIdentityToken`: 
.. _`https://openapi.ctcfile.com/api/User/GetUserInfo`: 
.. _`https://api.ctcfile.com/api/Goods/GetAllLabelsAsyncl`: 
.. _`https://api.ctcfile.com/api/MemoryLib/AddMemoryLibAsync`: 
.. _`https://api.ctcfile.com/api/App/GetLanguages`: 
.. _`https://api.ctcfile.com/api/MemoryLib/AddOrUpdateMemoryItemAsync`: 