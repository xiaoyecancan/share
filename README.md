<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<meta name="author" content="jack">
<meta name="viewport" content="width=device-width,initial-scale=1,minimum-scale=1,maximum-scale=1,
 		user-scalable=no" />
<!-- 适应手机屏幕，防止屏幕缩放 -->

<!--样式-->
<link rel="stylesheet" type="text/css" href="http://www.jq22.com/jquery/bootstrap-3.3.4.css">
</head>

<body>
<title>固定表头和首列的表格</title>
<style type="text/css">
#left_div{
    width:100px;
    float: left;
}
#left_div1{
    width: 100%;
}
#left_div2{
	margin-top:-20px;
    width: 100%;
    height: 400px;
    overflow: hidden;
}
#left_table1 th{
	background: #E9F8FF;
	text-align:center;
}
#left_table2 th{
	text-align:center;
}

#right_div{
    float: left;
}
#right_div1{
    width: 100%;
    overflow: hidden;
}
#right_divx{
    width: 900px;
}
#right_div2{
	margin-top:-20px;
    width:100%;
    height:400px;
    overflow: auto;
}
#right_table1{
    width: 880px;
}
#right_table2{
	/**width和max-width一起写，手机浏览器打开也能固定长度**/
    width: 880px;
    max-width: 880px;
    white-space:nowrap;
}
#right_table1 th{
	background: #E9F8FF;
    text-align:center;
	width:10%;
}
#right_table2 td{
	width:10%;
    text-align:center;
}

</style>
<div class="container-fluid">
  <div id="left_div">
    <div id="left_div1">
      <table id="left_table1" class="table table-bordered">
        <tr>
          <th>我不会动</th>
        </tr>
      </table>
    </div>
    <div id="left_div2">
      <table id="left_table2" class="table table-bordered">
      </table>
    </div>
  </div>
  <div id="right_div">
    <div id="right_div1">
      <div id="right_divx">
        <table id="right_table1" class="table table-bordered">
          <tr>
            <th>我是表头</th>
            <th>我是表头</th>
            <th>我是表头</th>
            <th>我是表头</th>
            <th>我是表头</th>
            <th>我是表头</th>
            <th>我是表头</th>
            <th>我是表头</th>
            <th>我是表头</th>
            <th>我是表头</th>
          </tr>
        </table>
      </div>
    </div>
    <div id="right_div2">
      <table id="right_table2" class="table table-bordered">
      </table>
    </div>
  </div>
</div>

<!--脚本--> 
<script src="http://www.jq22.com/jquery/jquery-1.10.2.js"></script> 
<script src="./bootstrap.min.js" type="text/javascript"></script> 
<script type="text/javascript">

//固定和滚动
var right_div2 = document.getElementById("right_div2");
right_div2.onscroll = function(){
    var right_div2_top = this.scrollTop;
    var right_div2_left = this.scrollLeft;
    document.getElementById("left_div2").scrollTop = right_div2_top;
    document.getElementById("right_div1").scrollLeft = right_div2_left;
}
//设置右边div宽度
document.getElementById("right_div").style.width=""+document.documentElement.clientWidth-130+"px";	
setInterval(function() {
	document.getElementById("right_div").style.width=""+document.documentElement.clientWidth-130+"px";	
}, 0);

for(var i=0;i<24;i++){
	$("#left_table2").append("<tr><th>我是首列</th></tr>");
	$("#right_table2").append("<tr><td>"+i+"</td><td>"+i+"</td><td>"+i+"</td><td>"+i+"</td><td>"+i+"</td><td>"+i+"</td><td>"+i+"</td><td>"+i+"</td><td>"+i+"</td><td>"+i+"</td></tr>");
}

</script>
</body>
</html>
