# AddressCrawer
全国各城市地名抓取，包含街道、村落、小区、商店、景点等
### 博客链接：
[https://www.cnblogs.com/bincoding/p/9168040.html](https://www.cnblogs.com/bincoding/p/9168040.html)

> 之前做命名实体识别地址时，因为丽江很多地名比较奇怪，不能直接用pyltp提取，准备添加自定义字典，增加地址提取准确率。
### 地址数据源：
[http://poi.mapbar.com/lijiang/](http://poi.mapbar.com/lijiang/)
这里以丽江为例，其他地方的地名爬取原理一样的。

### 获取地址分类：
``` javascript
// 当前页面地址：http://poi.mapbar.com/lijiang/901/
// css选择器
$(".sortBox a")
// init(211) [a#520, a#530, a#541, a
$(".sortBox a")[0].innerHTML
// "超市"
$(".sortBox a")[0].href
// "http://poi.mapbar.com/lijiang/520/"
```

### 提取地名：

``` javascript
// 提取某个分类下所有地名标签
// css选择器
$(".sortC a")
// init(328) [a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, a, …]
// 获取标签文字
$(".sortC a")[0].innerHTML
// "爱尚里"
$(".sortC a")[1].innerHTML
// "八河"
$(".sortC a")[1].href
// "http://poi.mapbar.com/lijiang/MAPIJPHRCNHOFNHIJNTRC"
```



### 数据源示例：
![](https://images2018.cnblogs.com/blog/771778/201806/771778-20180611172307530-461473783.png)