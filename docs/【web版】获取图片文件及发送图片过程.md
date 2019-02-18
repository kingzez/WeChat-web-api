# 接收图片
> GET : https://wx.qq.com/cgi-bin/mmwebwx-bin/webwxgetmsgimg

> Param：
```javascript
//requset

MsgID="8997396119269472610"
skey="%40crypt_a936502b_74e29c164b1802c5bfd4b1f9a7db4b5e"
type="slave" 有该类型是缩略图，没有则是原图
```

```javascript
//response

图片流
```



# 发送图片
## 1 发送请求

GET: https://support.weixin.qq.com/cgi-bin/mmsupport-bin/reportforweb?rid=69373&rkey=9&rvalue=1

GET: https://support.weixin.qq.com/cgi-bin/mmsupport-bin/reportforweb?rid=63637&rkey=72&rvalue=146  

GET: https://support.weixin.qq.com/cgi-bin/mmsupport-bin/reportforweb?rid=63637&rkey=76&rvalue=1


## 2 缓存
GET: blob:https://wx.qq.com/21ff8b6b-758e-4c3f-8909-5df3d3c11d4c  缓存

## 3 转成base64


## 4 上传图片

OPTIONS: https://file.wx.qq.com/cgi-bin/mmwebwx-bin/webwxuploadmedia?f=json
```javascript
//request
图片
```

```javascript
//response

{
    "BaseResponse": {
        "Ret": 1,
        "ErrMsg": ""
    },
    "MediaId": "",
    "StartPos": 0,
    "CDNThumbImgHeight": 0,
    "CDNThumbImgWidth": 0
}

```

## 4 所有上传中response 都一样

POST: https://file.wx.qq.com/cgi-bin/mmwebwx-bin/webwxuploadmedia?f=json 
```javascript
//request
图片
```

```javascript
//response

{
    "BaseResponse": {
        "Ret": 0,
        "ErrMsg": ""
    },
    "MediaId": "",
    "StartPos": 0,
    "CDNThumbImgHeight": 0,
    "CDNThumbImgWidth": 0
}


```

## 4 上传成功后获取到 `MediaId`、 缩略图宽高`CDNThumbImgWidth`、 `CDNThumbImgHeight`


POST: https://file.wx.qq.com/cgi-bin/mmwebwx-bin/webwxuploadmedia?f=json

```javascript
//request
图片
```

```javascript
//response

{
    "BaseResponse": {
        "Ret": 0,
        "ErrMsg": ""
    },
    "MediaId": "@crypt_a60f99f7_93b86d77b96410f61682940c55fe8fe9cc17e0c5cfed14f7ccd285ef57f8f91b419b77a13f76456a949c30384030f7eb365ea859e5bb7037a64cdaa19e87b23a284300984f836fe580e8e85bb918c2123467f205833684dc06f2b7e6912e982a06979eb727c3a5f713d7c958b4d0cf63ba6cdd4c0cc88503b4e2ac7e3ce6a910bba12bb863b6c5240fbe80f4f5d9e4b05ac0bc09bf26d703ae654b9de5388b895b0802de513d32551aa45c5e778a9cff1a03bb3f5e2e183ba8a65bcf1cb521a103acdb7ec1caa56029238b0656bc6eac57e5bec39dc94d1d908c25b79a84238184dc739f55d3c776c8c16183de2daab52e9d82c5ea4f571f0eff8f3bd71ad505cc2f42704aaf74340ffb6b3d1de86603a38c421451ed982b511bedb330100da73463ff22f53c349ea65cc93d68700135b69ed666908e3c750737afa417db41e9",
    "StartPos": 977168,
    "CDNThumbImgHeight": 71,
    "CDNThumbImgWidth": 100
}

```

## 5 发送 

POST: https://wx.qq.com/cgi-bin/mmwebwx-bin/webwxsendmsgimg?fun=async&f=json&lang=zh_CN

```javascript
//request

{
    "BaseRequest": {
        "Uin": 2272112421,
        "Sid": "oMrabhVznekD3NaC",
        "Skey": "@crypt_a936502b_74e29c164b1802c5bfd4b1f9a7db4b5e",
        "DeviceID": "e426626750347587"
    },
    "Msg": {
        "Type": 3,  //图片类型
        "MediaId": "@crypt_a60f99f7_93b86d77b96410f61682940c55fe8fe9cc17e0c5cfed14f7ccd285ef57f8f91b419b77a13f76456a949c30384030f7eb365ea859e5bb7037a64cdaa19e87b23a284300984f836fe580e8e85bb918c2123467f205833684dc06f2b7e6912e982a06979eb727c3a5f713d7c958b4d0cf63ba6cdd4c0cc88503b4e2ac7e3ce6a910bba12bb863b6c5240fbe80f4f5d9e4b05ac0bc09bf26d703ae654b9de5388b895b0802de513d32551aa45c5e778a9cff1a03bb3f5e2e183ba8a65bcf1cb521a103acdb7ec1caa56029238b0656bc6eac57e5bec39dc94d1d908c25b79a84238184dc739f55d3c776c8c16183de2daab52e9d82c5ea4f571f0eff8f3bd71ad505cc2f42704aaf74340ffb6b3d1de86603a38c421451ed982b511bedb330100da73463ff22f53c349ea65cc93d68700135b69ed666908e3c750737afa417db41e9",
        "Content": "",
        "FromUserName": "@201052a7770bca9418a5a8aba13ffc879f2768df968c8ec3d188d9790695fc8a",
        "ToUserName": "@1f2879f180e21b8a2906d594822857050889711650c5ef303960482ab7078812",
        "LocalID": "15114939427950364",
        "ClientMsgId": "15114939427950364"
    },
    "Scene": 0
}
```

```javascript
//response

{
    "BaseResponse": {
        "Ret": 0,
        "ErrMsg": ""
    },
    "MsgID": "1036723910963469192",
    "LocalID": "15114939427950364"
}

```




## 上传参数 Params

```
{
    mediatype: "pic"
    pass_ticket: "undefined"
    uploadmediarequest: {
        UploadType: 1,
        BaseRequest: {
            Uin: 2272112421,
            Sid: "sbP3ymYOQZio10BD ",
            Skey: "@crypt_a936502b_e15410d6dbff4c856aa8d26e71ec8ac1",
            DeviceID: e236986525200640
        },
        ClientMediaId: 1511509303507,
        TotalLen: 39766,
        StartPos: 0,
        DataLen: 39766,
        MediaType: 4,
        FromUserName: "@55917ed2bbb04c07687466c1a5afd3e4adaf015eee65728814f49b5d7885705a ",
        ToUserName: "@47ec5786aa3c8ac093b1150ff2846a7feb382b4299373cb7dc0143f925d74ff1",
        FileMd5: "daf2d55da001844735acd560b28d8a1a"
    }
    webwx_data_ticket: "gScDxle6RuLZRNXBh+IEbkmF"
}
```