# 消息体
> https://wx.qq.com/cgi-bin/mmwebwx-bin/webwxsync 中获得消息体

```javascript
msgBody = {
    "MsgId": "586941367312769777",
    "FromUserName": "@@27f08593f0a227c3a4bcecab6a8d5633fd742e3c93cacad328cd487ef645d9e7",
    "ToUserName": "@f4b126f41d10818c524ae41d151db11b018da381461e82c4388458eb9ae0e000",
    "MsgType": 1,
    "Content": "@1caa5d72524bfe1383abbc976612d7fbc9f0428e8c45c0ece8c75dd662bf47f6:<br/>你好你好",
    "Status": 3,
    "ImgStatus": 1,
    "CreateTime": 1515736755,
    "VoiceLength": 0,
    "PlayLength": 0,
    "FileName": "",
    "FileSize": "",
    "MediaId": "",
    "Url": "",
    "AppMsgType": 0,
    "StatusNotifyCode": 0,
    "StatusNotifyUserName": "",
    "RecommendInfo": {
        "UserName": "",
        "NickName": "",
        "QQNum": 0,
        "Province": "",
        "City": "",
        "Content": "",
        "Signature": "",
        "Alias": "",
        "Scene": 0,
        "VerifyFlag": 0,
        "AttrStatus": 0,
        "Sex": 0,
        "Ticket": "",
        "OpCode": 0
    },
    "ForwardFlag": 0,
    "AppInfo": {
        "AppID": "",
        "Type": 0
    },
    "HasProductId": 0,
    "Ticket": "",
    "ImgHeight": 0,
    "ImgWidth": 0,
    "SubMsgType": 0,
    "NewMsgId": 586941367312769777,
    "OriContent": "",
    "EncryFileName": ""
}
```

# 获取发消息人 HeadImgUrl
```javascript
params = {
    UserName: "@15fe1773f0239e24e26d92796e98b778fa2e10eca84aee9defee6cafceffc23f", // 发消息人 群消息username 从content中取 私聊 直接为 FromUserName
    Skey: angular.element(document).injector().get('accountFactory').getSkey(),
    MsgId: "6256157022282073076"
}

result = angular.element(document).injector().get('utilFactory').getContactHeadImgUrl(params)

result = "/cgi-bin/mmwebwx-bin/webwxgeticon?seq=0&username=@7a4028651b1e25faff1c63a2e658f67de5efc7530224981667d52d3b2ac5a105&skey=@crypt_a936502b_98624b0e5e37e187f08ec50b028cb3e1&msgid=5257969042830986755"

```


# 获取发消息人 NickName  
## getNicknameByUsername(username)
## 获取到实际的值为 ：remarkname || nickname
> 已实现到 [【guest script】](https://github.com/yi/wkf-prober-electron/blob/master/src/utils/guest_scripts.coffee#L356)

```javascript

// 注：群消息体组成 发消息人的username:<br\/>content  
//"@1caa5d72524bfe1383abbc976612d7fbc9f0428e8c45c0ece8c75dd662bf47f6:<br/>你好你好"
// 私聊 sender  =  FromUserName
var senduser; //发消息人
var content; //消息内容

content = msgBody.Content.replace(/^(@[a-zA-Z0-9]+|[a-zA-Z0-9_-]+):<br\/>/, function(e, t) {
    return senduser = t,
    ""
})
// senduser = "@1caa5d72524bfe1383abbc976612d7fbc9f0428e8c45c0ece8c75dd662bf47f6"
// content = "你好你好"

angular.element(document).injector().get('contactFactory').getContact(senduser, msgBody.FromUserName).getDisplayName(msgBody.FromUserName)


//eg:
result = angular.element(document).injector().get('contactFactory')
    .getContact("@1caa5d72524bfe1383abbc976612d7fbc9f0428e8c45c0ece8c75dd662bf47f6")
    .getDisplayName()
    
result = "Vincent W"
```