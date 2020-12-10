**状态码说明**
==============

====== ======================= =======================================
状态码 状态码英文名称           说明                                  
====== ======================= =======================================
200    OK                      请求成功。                            
401    Unauthorized            请求要求用户的身份认证                
500    Internal Server Error   服务器内部错误,查看 :ref:`error-core`
====== ======================= =======================================


.. _error-core: 

错误码
------


======= ========================================== =======================================
错误码  英文描述                                   中文描述                    
======= ========================================== =======================================
0       system error                               系统繁忙,此时请开发者稍候再试
40001   the account has been logged in elsewhere   账户已在别处登录
40003   not enough words                           字数不够
40004   number of word has expired                 字数已经过期
40005   language selection Error                   语言选择错误
40006   file has no words                          文件里没有字
40007   pdf has Encrypted                          pdf文件已加密
40008   file too large                             文件太大
40009   do not have this translation permissions   没有该类型文档翻译权限
40010   translation timeout                        翻译超时
40011   not enaugh pages                           页数不够
40012   document handling error                    文档处理出错
40013   the task has been canceled                 任务已经取消
40014   the operation has been canceled            操作已经取消
40015   some arguments is empty                    部分参数为空
40016   invalid args                               参数错误
40017   file data does not exist                   文件数据不存在
40018   file item does not exist                   文件项不存在
40019   task not exist                             任务不存在或已完成
40020   not support ocr                            不支持ocr                   
======= ========================================== =======================================