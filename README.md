# angularDemo
Angular练习
### 一些基本的angular指令
* `ng-app` angular最基本的指令 相当于开启了angular编译 可以在任何一个html上添加使用 但一个html最好只有一个ng-app 添加过多也只会识别第一个。<br> 
```html
<body ng-app="app">
  ... ...
<script src="../angular.min.js"></script>   
<script>
    var app = angular.module('app',[]);   //一切从它开始
</script> 
</body>
```
* `ng-controller` 是angular js里控制器 在控制器中编写代码函数。。。 用$scope对象去访问
```html
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
```html
<div ng-app="myApp" ng-controller="myCtrl">
    姓：<input type="text" ng-model="firstName"><br>
    名：<input type="text" ng-model="lastName"><br>
    全名：{{firstName + ' ' + lastName}}<br>
</div>

<script>
    var app = angular.module('myApp',[]); //demo中ng-app为‘myApp’元素是angular应用程序
    app.controller('myCtrl',function($scope){ //myApp应用程序是由什么数据内容控制的
        $scope.firstName = "Sun";
        $scope.lastName = "shine";
    });
```
* `ng-click` angular中的点击指令 当绑定元素被点击 则执行操作
* `ng-repeat` angular中遍历元素的指令 循环指定次数的元素 循环对象必须是数组或对象
* `ng-bind` 绑定 HTML 元素到应用程序数据
* `ng-init` 指令执行给定的表达式。ng-init 指令添加一些不必要的逻辑到 scope 中，建议你可以在控制器中 ng-controller 指令执行它 
* `ng-clock`
* `ng-selected` 
* `ng-change` 当一个元素的状态发生改变时 会触发这个指令操作
* `ng-copy` 复制
* `ng-cut`  剪切
* `ng-paste` 粘贴
