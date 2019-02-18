# 撤回消息
实现方法如下：
```javascript
msg = {
    MsgId: "3629065551085521194",
    ToUserName: "@a039625545ddfdfcc518cbabdc36ca2c1095ad25176d3ed99b5d2d990,ea45db7"
    ClientMsgId: "15156657121880707",
}

angular.element(document).injector().get('chatFactory').revokemsg(msg)
```
## Request 
### url
> https://wx.qq.com/cgi-bin/mmwebwx-bin/webwxrevokemsg?pass_ticket=Ta%252FhqPx81V1AfuFP%252BYyalcWAal%252BWtAGfP%252BWSUtQX5ZUG6RT6%252F9qdYY0etcNHvRhK

### request body
```javascript
{
    "BaseRequest": {
        "Uin": 2272112421,
        "Sid": "VSSKufNTHY7KfLAW",
        "Skey": "@crypt_a936502b_52fe6633081dcc297c7582561af9e9d2",
        "DeviceID": "e846911657230984"
    },
    "SvrMsgId": "1310710330281436239",
    "ToUserName": "@a039625545ddfdfcc518cbabdc36ca2c1095ad25176d3ed99b5d2d990ea45db7",
    "ClientMsgId": "15156659951750509"
}
```

## response
```javascript
{
    "BaseResponse": {
        "Ret": 0,
        "ErrMsg": ""
    },
    "Introduction": "ä½ å¯ä»¥æ’¤å›ž2åˆ†é’Ÿå†…å‘é€çš„æ¶ˆæ¯ï¼ˆéƒ¨åˆ†æ—§ç‰ˆæœ¬å¾®ä¿¡ä¸æ”¯æŒè¿™ä¸ªåŠŸèƒ½ï¼‰ã€‚",//中英文系统均为乱码
    "SysWording": "å·²æ’¤å›ž" //中英文系统均为乱码
}
```
```javascript
// 超过两分钟 无法撤回： 
// 时间可以根据 ClientMsgId  LocalID  15156675898840832 (去掉后四位得到发消息时的时间戳)=> 1515667589884  根据时间戳 计算
{
    "BaseResponse": {
        "Ret": -1,
        "ErrMsg": ""
    },
    "Introduction": "",
    "SysWording": ""
}
```