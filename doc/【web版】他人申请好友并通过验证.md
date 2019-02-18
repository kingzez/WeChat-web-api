- [添加申请好友](#添加申请好友)
- [通过验证](#通过验证)
- [angularjs注入实现通过好友验证](#angularjs注入实现通过好友验证)
## 添加申请好友
Request URL: https://wx.qq.com/cgi-bin/mmwebwx-bin/webwxstatusnotify?pass_ticket=vaKIL932WFhTd81gwNPgdMCa6eO50rVA4OwKbc7ihzJ%252BDI35hU47e901xWHlgyAB

```javascript
// request 
{
	"BaseRequest": {
		"Uin": 2272112421,
		"Sid": "Cgqjdrmqey2GcFmj",
		"Skey": "@crypt_a936502b_5b859f7523b6ca9a972dfda46a5b1cbe",
		"DeviceID": "e096843791780858"
	},
	"Code": 1,
	"FromUserName": "@4233fa05d05539732108de9e6badf0b90b3632264090fe778b65918865ce3960",
	"ToUserName": "fmessage",
	"ClientMsgId": 1514535065539
}

```

```javascript
// response
{
	"BaseResponse": {
		"Ret": 0,
		"ErrMsg": ""
	},
	"MsgID": "8034226646547498740"
}
```


## 通过验证

Request URL: https://wx.qq.com/cgi-bin/mmwebwx-bin/webwxverifyuser?r=1514535376115&pass_ticket=vaKIL932WFhTd81gwNPgdMCa6eO50rVA4OwKbc7ihzJ%252BDI35hU47e901xWHlgyAB

```javascript
// request 
{
	"BaseRequest": {
		"Uin": 2272112421,
		"Sid": "Cgqjdrmqey2GcFmj",
		"Skey": "@crypt_a936502b_5b859f7523b6ca9a972dfda46a5b1cbe",
		"DeviceID": "e259454658201818"
	},
	"Opcode": 3,
	"VerifyUserListSize": 1,
	"VerifyUserList": [{
		"Value": "@de2eaf6981fcc295508f155bb4945e4de9782693b8bd40a407def12685cab8c5",
		"VerifyUserTicket": "v2_15acedb658bb6e0f30facb02bc77e6a4706180d8fac6aadbed306ce42ae1b6b9d8b3077888516c20d4170b1f409a7b154deae4a7c085a0a689299844cdaaa107@stranger"
	}],
	"VerifyContent": "",
	"SceneListCount": 1,
	"SceneList": [33],
	"skey": "@crypt_a936502b_5b859f7523b6ca9a972dfda46a5b1cbe"
}

```

```javascript
// response
{
	"BaseResponse": {
		"Ret": 0,
		"ErrMsg": ""
	}

}
```

## angularjs注入实现通过好友验证
```javascript

let varifyInfo = {
    "Opcode": 3,
    "Scene": 33,
    "Ticket": "v2_15acedb658bb6e0f30facb02bc77e6a4d37b790878c3ed30f179d2e530378d481a53fe6d83d594994b9771ca02a53b57e0e021a2ef1df1e6e9609341a185b1ae@stranger",
    "UserName": "@de2eaf6981fcc295508f155bb4945e4de9782693b8bd40a407def12685cab8c5"
}


angular.element(document).injector().get('contactFactory').verifyUser(varifyInfo)
    .then(function(e) {
            e.BaseResponse && 0 == e.BaseResponse.Ret ? n.resolve(e) : (n.reject(e))
        },
        function(e) {

        })
```