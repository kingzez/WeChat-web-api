在 console 中执行即可得到所有的服务

```javascript
var inj;
function allServices(mod, r) {
  if (!r) {
    r = {};
    inj = angular.element(document).injector().get;
  }
  angular.forEach(angular.module(mod).requires, function(m) {allServices(m,r)});
  angular.forEach(angular.module(mod)._invokeQueue, function(a) {
    try { r[a[2][0]] = inj(a[2][0]); } catch (e) {}
  });
  return r;
};

allMyServices = allServices('webwxApp');
```
![image](https://user-images.githubusercontent.com/10891613/34860146-81ea9982-f796-11e7-8048-333ce013e73b.png)
