# wechat-encodingAESKey

微信官方只提供了C++、php、Java、Python和C#版本的示例代码，看了官方算法和部分别人的轮子，

## 微信公众号消息加密解密，支持 node > 8.0

```shell
npm install wechat-encodingAESKey --save 
```


```javascript
 var WXCrypto = require('wechat-encodingAESKey');
 var wx = new WXCrypto(token, aesKey, appid);
 var encryptedXML = wx.encrypt(xml, timestamp, nonce); // 加密 输出是字符串
 var decryptedXML = wx.decrypt(signature, timestamp, nonce, 加密的字符串); //解密 输出是xml
```


## 解密后是xml格式，可以通过xml2json自行解析

```shell
npm install xml2json --save 
```

### js

```javascript
 xml2json
 var parseString = require('xml2js').parseString;
 var decryptedjson
 await parseString(decryptedXML, function (err, result) {
    decryptedjson = result
 });
 console.log( decryptedjson.xml.Content[0] )
```
 
 尤其Github上一篇代码，没找到出处，感谢所有轮主。
