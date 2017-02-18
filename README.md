<!DOCTYPE html>
<html>
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>
<body>
 
<form name = "vitals" ng-app="vitals" ng-controller="vitalsCtrl">
<input name = "bloodPressure" ng-model='bloodPressure' placeholder="Blood Pressure">
<input name = "pulse" ng-model='pulse' placeholder="Pulse">
<br>
<br>
<input name = "specialHealth" ng-model='specialHealth' placeholder = "Special medical history, if none leave blank">
<p>Medical history reviewed. 
<span ng-show="vitals.bloodPressure.$dirty"> BP {{bloodPressure}} </span>
<span ng-show="vitals.pulse.$dirty"> P {{pulse}}. </span>
<span ng-show="vitals.specialHealth.$dirty"> {{specialHealth}} </span>
</p>
</form>
 
<form name="surfaces" ng-contoller="SurfaceController">
   <label> Mesial:
        <input type="checkbox" ng-model= "M">
   </label>
   <label> Occlusal:
        <input type="checkbox" ng-model= "O">
   </label>
   <label> Distal:
        <input type="checkbox" ng-model= "D">
   </label>
   <label> Buccal:
        <input type="checkbox" ng-model= "B">
   </label>
   <label> Lingual:
        <input type="checkbox" ng-model= "L">
   </label>
 
<p>
<span ng-show="M">M</span><span ng-show="O">O</span><span ng-show="D">D</span><span ng-show="B">B</span><span ng-show="L">L</span>
</p>
 
</form>
  
   
 
<script>
var app = angular.module('vitals', []);
app.controller('vitalsCtrl', function($scope) {
    $scope.bloodPressure = "";
    $scope.pulse = "";
    $scope.specialHealth= "";
});
 
angular.module('SurfaceController', [])
    .controller('SurfaceController', ['$scope', function($scope) {
      $scope.checkboxModel =""
     };
    }]);
 
</script>
 
 
 
</body>
</html>
