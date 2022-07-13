**返回码说明**
==============

====== ======================= =======================================
状态码 状态码英文名称           说明                                  
====== ======================= =======================================
200    OK                      请求成功。                            
401    Unauthorized            请求要求用户的身份认证                
400    Bad Request             查看 :ref:`error-core`
500    Internal Server Error   服务器内部错误,请稍后重试
====== ======================= =======================================


.. _error-core: 

错误码
------

.. code:: json

    {
        "err_code": "40016",
        "message": "Invalid args."
    }


======= ======================================================== =======================================
错误码  英文描述                                                 中文描述                    
======= ======================================================== =======================================
0       System error.                                            系统繁忙,此时请开发者稍候再试
40001   The account has been logged in elsewhere.                账户已在别处登录
40002   Get access_token error.                                  获取令牌失败
40003   Not enough words.                                        额度不足
40004   Number of word has expired.                              额度已过期
40005   Language selection Error.                                语言选择错误
40006   File has no words.                                       文件里没有字
40007   Pdf has Encrypted.                                       pdf文件已加密
40008   File too large.                                          文件太大
40009   Do not have this translation permissions.                没有该类型文档翻译权限
40010   Translation timeout.                                     翻译超时
40011   Not enaugh pages.                                        页数不够
40012   Document handling error.                                 文档处理出错
40013   The task has been canceled.                              任务已经取消
40014   The operation has been canceled.                         操作已经取消
40015   Some arguments is empty.                                 部分参数为空
40016   Invalid args.                                            参数错误
40017   File data does not exist.                                文件数据不存在
40018   File item does not exist.                                文件项不存在
40019   Task not exist.                                          任务不存在或已完成
40020   Not support OCR.                                         不支持OCR      
40021   User doesn't exist.                                      用户不存在    
40022   Specified argument was out of the range of valid values. 指定的参数不在有效值范围内     
40024   File not found.                                          文件不存在
40025   File convert fail.                                       文件转换失败       
40026   The source language is the same as the target language.  源语言与目标语言相同      
40035   User space out of range.                                 私有云空间已不足
40043   Assign words expired.                                    分配额度已过期
40044   Assign words not enough.                                 分配额度不足
40045   User not exist.                                          用户不存在
40046   User locked.                                             用户被锁定
40047   User channel error                                       用户平台错误
40050   no language translate right                              用户没有该语种翻译权限
======= ======================================================== =======================================
