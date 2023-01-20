# Routing State with Controller
#### Given the Following State Config
```
.state('home', {
    url: '/',
    templateUrl: 'home.html'
});
```
__home.html__
```
<div ng-controller="HomeCtrl as home">
    <div> content </div>
    <div> content </div>
</div>
```
`<div ng-controller="HomeCtrl as home">` - inefficient because this tag is only here to declare controller

#### Declare Controller In State Configuration
```
.state('home', {
    url: '/',
    templateUrl: 'home.html',
    controller: 'HomeCtrl as home'
});
```
__home.html__
```
<div> content </div>
<div> content </div>
```
***
#### _Summary_
* We can declare a controller that is responsible for the state's template right in the state's declaration.
* Use
    * `controller: 'CtrlName as label'` or
    * `controller: ctrlName, controllerAs: 'label'`;
* In the template, use label.data as usual with controllerAs syntax. 
***