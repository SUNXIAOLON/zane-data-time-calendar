# zane-data-time-calendar
PC端时间日历插件

### 说明：
此插件不依赖任何第三方插件，因此可以在任何地方单独使用

### images 
![输入图片说明](https://github.com/wangweianger/zane-data-time-calendar/blob/master/demo/01.png "在这里输入图片标题")
![输入图片说明](https://github.com/wangweianger/zane-data-time-calendar/blob/master/demo/02.png "在这里输入图片标题")
![输入图片说明](https://github.com/wangweianger/zane-data-time-calendar/blob/master/demo/03.png "在这里输入图片标题")
![输入图片说明](https://github.com/wangweianger/zane-data-time-calendar/blob/master/demo/04.png "在这里输入图片标题")
![输入图片说明](https://github.com/wangweianger/zane-data-time-calendar/blob/master/demo/05.png "在这里输入图片标题")
![输入图片说明](https://github.com/wangweianger/zane-data-time-calendar/blob/master/demo/06.png "在这里输入图片标题")
![输入图片说明](https://github.com/wangweianger/zane-data-time-calendar/blob/master/demo/07.png "在这里输入图片标题")
![输入图片说明](https://github.com/wangweianger/zane-data-time-calendar/blob/master/demo/08.png "在这里输入图片标题")

### API文档及DEMO地址  ：http://www.seosiwei.com/zaneDate/index.html  

### npm地址：https://www.npmjs.com/package/zane-calendar 

### vue组件npm地址 支持vue1.0,vue2.0: https://www.npmjs.com/package/vue-date-calendar

### 使用方式  


### 浏览器端使用 
```js
<link href="./dist/zane-calendar.min.css">
<script src="./dist/zane-calendar.min.js"></script>

<!-- Input boxes for plug-ins requiring extra time. -->
<input type="" name="" id="zane-calendar">

Initialization.
zaneDate({
	elem:'#zane-calendar',
})
```


### Webpack 使用

```js

npm install zane-calendar --save-dev


const zaneDate = require('zane-calendar') 或
import zaneDate from 'zane-calendar'


<!-- Input boxes for plug-ins requiring extra time. -->
<input type="" name="" id="zane-calendar">


Initialization. 
zaneDate({
	elem:'#zane-calendar',
})

```

### 参数说明

参数配置(参数可灵活配置)
```js
{
	
	elem:'#zane-calendar',  控件的dom原生 注意：仅限制于id选择器
	type:'day',   			可选类型 day year month time doubleday doubleyear doublemonth doubletime
	lang:'cn',   			可选择语言类型 cn , en 
	width:250,  			插件宽度配置   220 <= X <= 500
	height:280, 			插件高度配置   240 <= X <= 350
	behindTop:10,   		插件于输入框的高度 
	format:'yyyy-MM-dd HH:mm:ss',  时间格式化
	begintime:'',  			开始时间  （单选择器默认选择此项）
	endtime:'',             结束时间  （double选择器需要）
	min:'',  				可选取时间最小范围 1900-10-01
	max: '',  				可选取时间最大范围 2099-12-31
	position:'fixed',  		定位方式  暂时只支持 fixed
	event:'click',   		事件方式 暂时只支持 click 
	zindex:100,   			z-index值
	showtime:true,  		是否显示选择时间
	showclean:true,  		是否显示清除按钮
	shownow:true,  			是否显示当前按钮
	showsubmit:true, 		是否显示提交按钮
	haveBotBtns:true, 		是否有底部按钮列表
	showsecond:true,        type='time|doubletime'时是支持选择秒单位
	calendarName:'', 		此参数勿动 表示当前时间插件实例化对象
	mounted:()=>{}, 		插件加载完成之后调用
	change:(fulltime,begintime,endtime)=>{}, 时间变更之后调用
	done:(fulltime,begintime,endtime)=>{}, 选择完成之后调用
}	


```
### 案例调用方式

```js
	默认完整选项
	zaneDate({
		elem:'#zane-calendar',
	})

	只选择年月日
	zaneDate({
		elem:'#zane-calendar',
		showtime:false,
	})

	使用英文
	zaneDate({
		elem:'#zane-calendar',
		lang:'en',
	})

	只选择年
	zaneDate({
		elem:'#zane-calendar',
		type:'year',
	})

	只选择月
	zaneDate({
		elem:'#zane-calendar',
		type:'month',
	})

	只选择时间
	zaneDate({
		elem:'#zane-calendar',
		type:'time',
	})

	格式化方式
	zaneDate({
		elem:'#zane-calendar',
		format:'yyyy年MM月dd日 HH时mm分ss秒',
	})

	限定能选择的最小最大区间
	zaneDate({
		elem:'#zane-calendar',
		min:'2017-08-01',
		max:'2017-08-20',
	})

	......

	具体的请查看demo

```

### 1.1.0 版本新增 double选择器 

```js
config.type  新增double类型  可选类型如下：day year month time doubleday doubleyear doublemonth doubletime

双日期范围选择
zaneDate({
	elem:'#demo21',
	type:'doubleday'
})

双年范围选择
zaneDate({
	elem:'#demo22',
	type:'doubleyear',
})

双月范围选择
zaneDate({
	elem:'#demo23',
	type:'doublemonth',
})

双时间选择
zaneDate({
	elem:'#demo24',
	type:'doubletime', 
})


```

### 1.2.0 版本
### 1.doubleday类型新增选择时间，支持时分秒选择
### 2.double类型检测距离右边window边线的距离，若不足，自动排列为上下两个日期

```js
config.type doubleday支持选择时间范围

双日期范围选择
zaneDate({
	elem:'#demo25',
	format:'yyyy-MM-dd HH:mm:ss',
	type:'doubleday',
	showtime:true
})

```

### 1.2.1 版本  新增z-index 参数
```js
zaneDate({
	elem:'#zane-calendar',
	zindex:500,
})

```

### 1.2.2 版本 完善日历插件文档

### 2.0.9 版本 修复单页面BUG，修复safair苹果信息 相关BUG

### 2.1.0 版本 修复双选择器有默认值的bug，更新demo图片

### 2.2.0 版本 修复上一月下一月跳月问题

### 2.2.3 版本 修复点击多次重复生成日历问题

### 2.2.4 版本 增加结束时间大于开始时间的判断

### 2.2.5 版本 增加双选择器区间选中样式效果

### 2.2.6 版本 修复双选择器默认选中颜色相关bug

### 2.2.7 版本 type='time|doubletime'时是支持选择秒单位

