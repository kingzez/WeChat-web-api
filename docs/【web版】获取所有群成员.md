# 获取所有群成员/除自已以外的所有群成员

## 获取所有群成员
```javascript 
groupName = "@@92a661bf9fa74f10bd5a6ab7e25393ae8f290f09c7dd8de1251228efc7d72394"
// 可选参数 withoutMe

angular.element(document).injector().get('contactFactory')
  .getChatRoomMembersContact(groupName)
```


## 获取出自己以外的所有群成员
```javascript 

angular.element(document).injector().get('contactFactory')
  .getChatRoomMembersContact(groupName, "withoutMe")
```
## 执行结果
<img width="1262" alt="qq20180123-172939 2x" src="https://user-images.githubusercontent.com/10891613/35268110-385a631c-0063-11e8-958b-63f76be4a196.png">