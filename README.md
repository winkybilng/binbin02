# binbin02
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>IFE JavaScript Task 01</title>
  </head>
<body>

  <h3>污染城市列表</h3>
  <ul id="aqi-list">
<!--   
    <li>第一名：福州（样例），10</li>
      <li>第二名：福州（样例），10</li> -->
  </ul>

<script type="text/javascript">

var aqiData = [
  ["西安", 100],
  ["北京", 90],
  ["上海", 50],
  ["福州", 10],
  ["广州", 50],
  ["成都", 90],

];

(function () {

  /*
  在注释下方编写代码
  遍历读取aqiData中各个城市的数据
  将空气质量指数大于60的城市显示到aqi-list的列表中
  */
  function compare(value1,value2){
    if (value1<value2) {
      return -1;
    } else if(value1>value2){
      return 1;
    }
    else return 0;
  }
var aqiresult = aqiData.filter(function(item){
  return (item[1] > 60);
});
aqiresult.sort(compare);
for (var i = 0; i < aqiresult.length; i++) {
  var li = document.createElement("li");
  document.getElementById("aqi-list").appendChild(li);
  li.innerHTML = aqiresult[i][0]+"为第"+ i +"名，空气污染指数为" + aqiresult[i][1];
}
})();

</script>
</body>
</html>
