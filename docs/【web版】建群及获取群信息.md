# 建群
>POST: https://wx.qq.com/cgi-bin/mmwebwx-bin/webwxcreatechatroom?r=1511952419440
#### request
```javascript
 {
	"MemberCount": 2,
	"MemberList": [{
		"UserName": "@d90971cfd323a2e2c13d345a9e1ca5c5608fefdae670c1ce470b2d10a86fd847"
	}, {
		"UserName": "@53f3c05380da953d19116b903fcb9d9db287b138622f3ad902e6e88928cb3721"
	}],
	"Topic": "",
	"BaseRequest": {
		"Uin": 488765359,
		"Sid": "UMbxr71Njdylap27",
		"Skey": "@crypt_7382455a_ea46cb6e96eb89aa5e5caaccb64c27fd",
		"DeviceID": "e494907203492397"
	}
}
```

#### response

```javascript
{
	"BaseResponse": {
		"Ret": 0,
		"ErrMsg": "Everything is OK"
	},
	"Topic": "",
	"PYInitial": "",
	"QuanPin": "",
	"MemberCount": 2,
	"MemberList": [{
		"Uin": 0,
		"UserName": "@d90971cfd323a2e2c13d345a9e1ca5c5608fefdae670c1ce470b2d10a86fd847",
		"NickName": "Rain1ove",
		"AttrStatus": 0,
		"PYInitial": "",
		"PYQuanPin": "",
		"RemarkPYInitial": "",
		"RemarkPYQuanPin": "",
		"MemberStatus": 0,
		"DisplayName": "",
		"KeyWord": ""
	}, {
		"Uin": 0,
		"UserName": "@53f3c05380da953d19116b903fcb9d9db287b138622f3ad902e6e88928cb3721",
		"NickName": "迴焘願點",
		"AttrStatus": 0,
		"PYInitial": "",
		"PYQuanPin": "",
		"RemarkPYInitial": "",
		"RemarkPYQuanPin": "",
		"MemberStatus": 0,
		"DisplayName": "",
		"KeyWord": ""
	}],
	"ChatRoomName": "@@60bee4413ae9c655abe22fc69d5a0d110a6a71e3aa23566ac109707f1354da4e",
	"BlackList": ""
}
```
# 建群后获取群信息

>POST: https://wx2.qq.com/cgi-bin/mmwebwx-bin/webwxbatchgetcontact?type=ex&r=1511952420539

#### request 
```javascript
{
	"BaseRequest": {
		"Uin": 488765359,
		"Sid": "UMbxr71Njdylap27",
		"Skey": "@crypt_7382455a_ea46cb6e96eb89aa5e5caaccb64c27fd",
		"DeviceID": "e873795171117613"
	},
	"Count": 1,
	"List": [{
                // UserName 为刚刚创建的群名称 ChatRoomName
		"UserName": "@@60bee4413ae9c655abe22fc69d5a0d110a6a71e3aa23566ac109707f1354da4e",   
		"ChatRoomId": ""
	}]
}
```

#### response
```javascript
{
	"BaseResponse": {
		"Ret": 0,
		"ErrMsg": ""
	},
	"Count": 1,
	"ContactList": [{
		"Uin": 0,
		"UserName": "@@60bee4413ae9c655abe22fc69d5a0d110a6a71e3aa23566ac109707f1354da4e",
		"NickName": "",
		"HeadImgUrl": "/cgi-bin/mmwebwx-bin/webwxgetheadimg?seq=658243804&username=@@60bee4413ae9c655abe22fc69d5a0d110a6a71e3aa23566ac109707f1354da4e&skey=",
		"ContactFlag": 2,
		"MemberCount": 3,
		"MemberList": [{
			"Uin": 0,
			"UserName": "@34ec15a61cf54e046611216d557409a82234b496a7d6ed59cec95cc99c9f9d39",
			"NickName": "<span class=\"emoji emoji1f601\"></span> <span class=\"emoji emoji1f602\"></span> <span class=\"emoji emoji1f603\"></span> <span class=\"emoji emoji1f604\"></span> <span class=\"emoji emoji1f47f\"></span> <span class=\"emoji emoji1f60f\"></span>",
			"AttrStatus": 102437,
			"PYInitial": "",
			"PYQuanPin": "",
			"RemarkPYInitial": "",
			"RemarkPYQuanPin": "",
			"MemberStatus": 0,
			"DisplayName": "",
			"KeyWord": ""
		}, {
			"Uin": 0,
			"UserName": "@53f3c05380da953d19116b903fcb9d9db287b138622f3ad902e6e88928cb3721",
			"NickName": "迴焘願點",
			"AttrStatus": 102501,
			"PYInitial": "",
			"PYQuanPin": "",
			"RemarkPYInitial": "",
			"RemarkPYQuanPin": "",
			"MemberStatus": 0,
			"DisplayName": "",
			"KeyWord": ""
		}, {
			"Uin": 0,
			"UserName": "@d90971cfd323a2e2c13d345a9e1ca5c5608fefdae670c1ce470b2d10a86fd847",
			"NickName": "Rain1ove",
			"AttrStatus": 234169,
			"PYInitial": "",
			"PYQuanPin": "",
			"RemarkPYInitial": "",
			"RemarkPYQuanPin": "",
			"MemberStatus": 0,
			"DisplayName": "",
			"KeyWord": ""
		}],
		"RemarkName": "",
		"HideInputBarFlag": 0,
		"Sex": 0,
		"Signature": "",
		"VerifyFlag": 0,
		"OwnerUin": 0,
		"PYInitial": "",
		"PYQuanPin": "",
		"RemarkPYInitial": "",
		"RemarkPYQuanPin": "",
		"StarFriend": 0,
		"AppAccountFlag": 0,
		"Statues": 1,
		"AttrStatus": 0,
		"Province": "",
		"City": "",
		"Alias": "",
		"SnsFlag": 0,
		"UniFriend": 0,
		"DisplayName": "",
		"ChatRoomId": 0,
		"KeyWord": "",
		"EncryChatRoomId": "@75d4e4644c3e2782bd916967c6de6418",
		"IsOwner": 1
	}]
}
```

# AngularJS 服务注入建群
```javascript
// 用户名 UserName 对象数组
let selectUsers = [
  { UserName: "@ceafc2d2a463161a9bfb97b26e39a73ca2406848894ee426df5ef05196c566a1" },
  { UserName: "@e5b7a249be58890c7411f5c5a5e97e12e5e2d52a4eec2dc0fc75aee3c09a568d" }
]

// angular service 创建群
angular.element(document).injector().get('chatroomFactory').create(selectUsers)
  .then(function (e) {
    e.BaseResponse && 0 == e.BaseResponse.Ret || e.BaseResponse.Ret == -2013 ? console.log("success") : console.log("failed")
  }, function (e) {

  })
```