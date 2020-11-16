**获取译文下载地址**
=====================

**请求地址**

::

   GET https://coresite.ctcfile.com/File/GetTgtDownUrls

**请求参数**

==== ==== ====== ==== ======================================
属性 类型 默认值 必填 说明
==== ==== ====== ==== ======================================
Id   int         是   文件ID，翻译接口返回的fileLibIds字段值
==== ==== ====== ==== ======================================

**返回值**

==== ====== ============
属性 类型   说明
==== ====== ============
docx string docx下载地址
pdf  string pdf下载地址
==== ====== ============

**返回数据示例**

正常返回

.. code:: json

   {
     "docx": "/GetFile/y03Gt1UqdFApuTx_qOBm6d0gh8HBntQiKN73Zp_6F4c-w6Uiy_1Rtt7I7I54RWrLjahlcfiRn759E1R-hg--SslHNPAxsgrohd2lU5cv1RFDP0rw1bTZADjaKA74LOqDz3dvd7zewmiJ_yLBp8KWDoiS2_ZH5fW7ke7Cbo3nexMvO0igJQ17C2enZ1QhuJiG2JHXCGak1JOI-_EH9Ad1ZCY7Hhp8qtYWgqnrNnqjGwL9sFEbhf70ZiJSB0_r3WXu6uhBSyUrQoej4aZRVCM42Q",
     "pdf": "/GetFile/s-S9EZQSLgQht-8wDYd3xKriLr40HgHazupne2pntVJLElRvUtz4emItO7UQbjbuBA4lVTWQed3O9TsJVri9-wgKFvwKe6f-dail8vji5NRyibBWwdGW9ZdV8JXZnXKxwj1YlhP_k9crEMwpIi6gW_jYMCfXW5QGiFv6ALSW13Y7tJwbhBoqfM63-Xv6AbYdDMzdaDyVR6nBb0Flwfm03jg1EcPo_nxvVKeFRzWe6JDYvCh8tziFDR7xCc7grYxVAEhHk4UUvoLaxGQXiKtHCQ"
   }

错误时返回

   :doc:`../overview/StatusCode`

**在线调试**

开发者可以使用 |网页调试工具| 调试该接口

.. |网页调试工具| raw:: html
 
   <a href="https://coresite.ctcfile.com/swagger/index.html#/%E6%96%87%E4%BB%B6%E6%8E%A5%E5%8F%A3/get_File_GetTgtDownUrls" target="_blank">网页调试工具</a>