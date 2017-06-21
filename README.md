# angularDemo
Angular练习
### 一些基本的angular指令
* `ng-app` angular最基本的指令 相当于开启了angular编译 可以在任何一个html上添加使用 但一个html最好只有一个ng-app 添加过多也只会识别第一个。<br> 
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Angular事件指令</title>
</head>
<body ng-app="app">
  ... ...
<script src="../angular.min.js"></script>   
<script>

    var app = angular.module('app',[]);   //一切从它开始

</script> 
</body>
</html>
```
* `ng-controller` 是angular js里控制器 在控制器中编写代码函数。。。 用$scope对象去访问
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Angular事件指令</title>
</head>
<body ng-app="app">
    <div ng-controller="myController">
        ... ...
    </div>
    <script src="../angular.min.js"></script>
    <script>
        var app =  angular.module('app',[]);
        app.controller('myController',function($scope){

        });
    </script>
</body>
</html>
```
说到$scope就会想到angular里的$rootscope 他们两者之间的区别是 $rootScope针对全局的作用域生效 $scope只针对当前的controller作用域生效 类似于javascript的原型链，搜索时会优先找自己的scope 不然则一级级向上搜索直到找到根作用域$rootscope。
* `$rootscope`
```html
        var app = angular.module('app',[]);
        app.run(['$rootScope',function($rootScope){
            $rootScope.name = 'daisy';
        }]);
```
* `ng-model` 是将标签设置的输入值与scope中的数据进行绑定
