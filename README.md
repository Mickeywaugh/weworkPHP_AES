# weworkPHP_AES
wework AES Sign fork from  sbzhu / weworkapi_php 

  包括VerifyURL, DecryptMsg, EncryptMsg三个接口，分别用于开发者验证回调url，收到用户回复消息的解密以及开发者回复消息的加密过程  
  使用方法可以参考Sample.php文件。
- 加解密协议请参考企业微信官方文档。
- 经测试，PHP 5.3.3 ~ 7.2.0 版本均可使用

<?php
use weworkapi\WXBizMsgCrypt;

$api=new WXBizMsgCrypt();

$sVerifyMsgSig = input('msg_signature');
$sVerifyTimeStamp =input('timestamp'); 
$sVerifyNonce = input('nonce');
$sVerifyEchoStr = input('echostr');
		// 需要返回的明文
$sEchoStr = "";
$wxcpt = new WXBizMsgCrypt($token, $aes_key, $app_id);
$errCode = $wxcpt->VerifyURL($sVerifyMsgSig, $sVerifyTimeStamp, $sVerifyNonce, $sVerifyEchoStr, $sEchoStr);
.....
.....
样例见Sample.php
