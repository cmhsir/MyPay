﻿# 收款二维码合并
## 原理
扫描二维码后跳转到此页面，然后根据 UA 判断具体平台。  
支付宝为:AlipayClient  
微信为:MicroMessenger/  
QQ为:QQ/  
**微信和QQ后边加"/"是加以区分，不加则QQ无法识别。**  
然后根据平台进行跳转，支付宝可以直接跳转到收款链接，而微信和QQ只能跳转到二维码页面，然后长按图片识别进行付款。  
同理可以添加其他平台的支付方式。  
移动和包为:hebao  
京东为: jdPay   
## 配置
### 1.更换支付宝收款链接  
保存支付宝收款二维码，使用二维码识别软件进行识别，得到链接。  
然后将 index.html 中的变量 alipayURL0 改为自己的支付宝收款链接。  
**alipayURL1 是扫码点单的收款链接，alipayURL2 是支付宝分享红包链接**  
此页面切换alipayURL0、1、2的原理是通过浏览器获取设备当前时间，然后取时间中的个位数数值。个位数值小于4是alipayURL0，大于4小于8是alipayURL1，大于8是alipayURL2。  
### 2.更换微信二维码
保存微信收款二维码，上传，并命名为 wechat.jpg  
**上传之前先删除原有的 wechat.jpg**
### 3.更换QQ二维码
保存QQ收款二维码，上传，并命名为 qq.png   
**上传之前先删除原有的 qq.jpg**  
### 4.设置为 Github Pages
选择 Settings --> GitHub Pages 设置为 Github Pages  
**如果没有通过 ICP 备案的域名建议不要使用自定义域名，会被微信拦截**  
设置成功后得到链接，使用链接生成二维码即可。
