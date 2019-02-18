# 文件消息

## 发送文件消息(excel、word、ppt、pdf)

> 文件获取URL  https://file.wx.qq.com/cgi-bin/mmwebwx-bin/webwxgetmedia
```
{
    sender: '@4f5ae0aa195467d343de2a2b71af73273c12f5211903479ff98342ae12a71668',
    mediaid: '@crypt_fb7d56f6_4c73b0358f351266a84ddd132a02bbccd8c0e923df6785d9f607a8b4c303ce082ffc0f4696e5e9727c430fed0da1d041ae658f399103b6a092f9b9009c5cb537d60fea1c29d6952cdd5a0adc83193e02',
    encryfilename: '%E7%8E%8B%E6%B3%BD%E7%9F%A5%2D%E5%91%A8%E6%8A%A5%2D20171229%2Exlsx',
    fromuser: '2272112421',
    pass_ticket: 'cpCS65By3qQ8VqBU7mnceHX2RrAqYu0e3Da5FR43PIgnVBBwr0Fem%252FXxFvqwlbvL,
    webwx_data_ticket: gSemLovTab2t7nqZ2fp57wMK'
}
```
> eg:  
>https://file.wx.qq.com/cgi-bin/mmwebwx-bin/webwxgetmedia?sender=@4f5ae0aa195467d343de2a2b71af73273c12f5211903479ff98342ae12a71668&mediaid=@crypt_fb7d56f6_4c73b0358f351266a84ddd132a02bbccd8c0e923df6785d9f607a8b4c303ce082ffc0f4696e5e9727c430fed0da1d041ae658f399103b6a092f9b9009c5cb537d60fea1c29d6952cdd5a0adc83193e02&encryfilename=%E7%8E%8B%E6%B3%BD%E7%9F%A5%2D%E5%91%A8%E6%8A%A5%2D20171229%2Exlsx&fromuser=2272112421&pass_ticket=cpCS65By3qQ8VqBU7mnceHX2RrAqYu0e3Da5FR43PIgnVBBwr0Fem%252FXxFvqwlbvL&webwx_data_ticket=gSemLovTab2t7nqZ2fp57wMK


### 1.上传过程

> Request URL: https://file.wx.qq.com/cgi-bin/mmwebwx-bin/webwxuploadmedia?f=json

#### request
```
------WebKitFormBoundarypmCFUdKkyDK6RCyY
Content-Disposition: form-data; name="id"

WU_FILE_2
------WebKitFormBoundarypmCFUdKkyDK6RCyY
Content-Disposition: form-data; name="name"

王泽知-日报-20171121.xlsx
------WebKitFormBoundarypmCFUdKkyDK6RCyY
Content-Disposition: form-data; name="type"

application/vnd.openxmlformats-officedocument.spreadsheetml.sheet
------WebKitFormBoundarypmCFUdKkyDK6RCyY
Content-Disposition: form-data; name="lastModifiedDate"

Wed Nov 22 2017 10:08:52 GMT+0800 (CST)
------WebKitFormBoundarypmCFUdKkyDK6RCyY
Content-Disposition: form-data; name="size"

17064
------WebKitFormBoundarypmCFUdKkyDK6RCyY
Content-Disposition: form-data; name="mediatype"

doc
------WebKitFormBoundarypmCFUdKkyDK6RCyY
Content-Disposition: form-data; name="uploadmediarequest"

{"UploadType":2,"BaseRequest":{"Uin":2272112421,"Sid":"1tii3ZdwRgZ63VMI","Skey":"@crypt_a936502b_ed4416744728af1905aa9338dc7acfb3","DeviceID":"e785325894917424"},"ClientMediaId":1517483154962,"TotalLen":17064,"StartPos":0,"DataLen":17064,"MediaType":4,"FromUserName":"@4f5ae0aa195467d343de2a2b71af73273c12f5211903479ff98342ae12a71668","ToUserName":"@600dad68de623655d2cf0bfd8a49b49bfd677092f00f276bd0ff531d0def7c7d","FileMd5":"6ff3c58431564d0e049525a1ea72605b"}
------WebKitFormBoundarypmCFUdKkyDK6RCyY
Content-Disposition: form-data; name="webwx_data_ticket"

gSemLovTab2t7nqZ2fp57wMK
------WebKitFormBoundarypmCFUdKkyDK6RCyY
Content-Disposition: form-data; name="pass_ticket"

cpCS65By3qQ8VqBU7mnceHX2RrAqYu0e3Da5FR43PIgnVBBwr0Fem/XxFvqwlbvL
------WebKitFormBoundarypmCFUdKkyDK6RCyY
Content-Disposition: form-data; name="filename"; filename="王泽知-日报-20171121.xlsx"
Content-Type: application/vnd.openxmlformats-officedocument.spreadsheetml.sheet


------WebKitFormBoundarypmCFUdKkyDK6RCyY--

```


### response

```
{
    "BaseResponse": {
        "Ret": 0,
        "ErrMsg": ""
    },
    "MediaId": "@crypt_e1a815ba_fbac33539ad19e956699f348b29b6900906a539d5bf7329ec29efddb7a3a6400c0b40f8c0e4c3cbe005949b7f47e2ee7046cb9c875e5d7c8ea38853f9a7b6db874e9628b1d47ae9649436378b5d2b9a8",
    "StartPos": 17064,
    "CDNThumbImgHeight": 0,
    "CDNThumbImgWidth": 0,
    "EncryFileName": "%E7%8E%8B%E6%B3%BD%E7%9F%A5%2D%E6%97%A5%E6%8A%A5%2D20171121%2Exlsx"
}
```

### 2.发送过程

> Request URL: https://wx.qq.com/cgi-bin/mmwebwx-bin/webwxsendappmsg?fun=async&f=json&pass_ticket=cpCS65By3qQ8VqBU7mnceHX2RrAqYu0e3Da5FR43PIgnVBBwr0Fem%252FXxFvqwlbvL

```
params = {
    fun:async,
    f:json,
    pass_ticket: cpCS65By3qQ8VqBU7mnceHX2RrAqYu0e3Da5FR43PIgnVBBwr0Fem%252FXxFvqwlbvL
}
```

#### request
```
{
    "BaseRequest": {
        "Uin": 2272112421,
        "Sid": "1tii3ZdwRgZ63VMI",
        "Skey": "@crypt_a936502b_ed4416744728af1905aa9338dc7acfb3",
        "DeviceID": "e578494563899759"
    },
    "Msg": {
        "Type": 6,
        "Content": "<appmsg appid='wxeb7ec651dd0aefa9' sdkver=''><title>王泽知-日报-20171121.xlsx</title><des></des><action></action><type>6</type><content></content><url></url><lowurl></lowurl><appattach><totallen>17064</totallen><attachid>@crypt_e1a815ba_fbac33539ad19e956699f348b29b6900906a539d5bf7329ec29efddb7a3a6400c0b40f8c0e4c3cbe005949b7f47e2ee7046cb9c875e5d7c8ea38853f9a7b6db874e9628b1d47ae9649436378b5d2b9a8</attachid><fileext>xlsx</fileext></appattach><extinfo></extinfo></appmsg>",
        "FromUserName": "@4f5ae0aa195467d343de2a2b71af73273c12f5211903479ff98342ae12a71668",
        "ToUserName": "@600dad68de623655d2cf0bfd8a49b49bfd677092f00f276bd0ff531d0def7c7d",
        "LocalID": "15174831548770216",
        "ClientMsgId": "15174831548770216"
    },
    "Scene": 0
}


```


### response

```
{
    "BaseResponse": {
        "Ret": 0,
        "ErrMsg": ""
    },
    "MsgID": "2512298580467649662",
    "LocalID": "15174831548770216"
}
```