# 欢迎使用 easy-check.js

---

## 使用：

```
 area.js存放区域编码的一个常量。由于easy-check.js里面的getPersonInfo18()方法需要调用这个常量，所以在easy-check.js之前引入。如果不需要用到这个方法也可以不引入area.js
 <script type="text/javascript" src="area.js" ></script>
 <script type="text/javascript" src="easy-check.js" ></script>
```
## 该javaScript库相关API介绍：
### 1、手机号码校验； 

-  是否是手机号码（只校验长度）
	 >isPhoneNumBySize: function(value)

-  手机号码（严格校验）
	 >isPhoneNum: function(value)
	 
-  手机号码（电信）
	 >isChinaTelecomPhoneNum: function(value)	 

-  手机号码（联通）
	 >isChinaUnicomPhoneNum: function(value)
 
-  手机号码（移动）
     >isChinaMobilePhoneNum: function(value)
     
-  是否是电话号码
	 >isPhoneCallNum: function(value)


### 2、邮箱校验； 

-  邮箱格式校验 

	 >isEmail: function(value)
	 
	 
	 
### 3、字符串常用校验； 

-  空字符串
	 >isEmpty: function(value)

-  不是空字符串
	 >isNotEmpty: function(value)
	 
-  空字符串，可为空格
	 >isBlank: function(value)	 

-  不是空字符串，也不是空格
	 >isNotBlank: function(value)
 
-   去掉前后空格
     >trim: function(value)
     
-  是否以某个字符串开头
	 >startsWith: function(value, prefix)
	 
-  是否以某个字符串结束
	 >endsWith: function(value, suffix)
	 
-  是否包含某个字符串
	 >contains: function(value, searchSeq)	 

-  是否和某个字符串相等
	 >isNotBlank: function(value, value2)
 
-  是否和某个字符串相等（不区分大小写）
     >equalsIgnoreCase: function(value, value2)
     
-  生成指定个数的字符
	 >repeat: function(value, repeatTimes)

-   删除空格
	 >deleteWhitespace: function(value)

-  右侧补全
	 >rightPad: function(value, size, padStr)

-  左侧补全
	 >leftPad: function(value, size, padStr)

-  首字符大写
	 >capitalize: function(value)

-  首字母小写
	 >uncapitalize: function(value)

-  大小写互转
	 >swapCase: function(value)

-  获取字符串中某个个字符串出现的次数
	 >countMatches: function(value, sub)

-  是否只包含字母
	 >isAlpha: function(value)

-  是否只包含字母、数字
	 >isAlphanumeric: function(value)

-  是否只包含字母、数字和空格
	 >isAlphanumericSpace: function(value)

-  是否只是数字
	 >isDecimal: function(value)

-  是否是小数
	 >isDecimal: function(value)

-  是否是负小数
	 >isNegativeDecimal: function(value)

-  是否是正小数
	 >isPositiveDecimal: function(value)

-  是否是整数
	 >isInteger: function(value)

-  是否是正整数
	 >isPositiveInteger: function(value)

-  是否是负整数
	 >isNegativeInteger: function(value)

-  是否只包含数字和空格
	 >isNumericSpace: function(value)

-  是否全为小写字母
	 >isAllLowerCase: function(value)

-  是否全为大写字母
	 >isAllUpperCase: function(value)

-  字符串反转
	 >reverse: function(value)

- 	消息格式化{@param {String} message, @param {Array} arr}

    >	format: function(message, arr) 
```
//栗子
var message='我的{0}是{1}';
var arr=['爱好','share'];
EasyCheck.StringUtils.format(message,arr);
```
```
我的爱好是share
```

-  把连续出现多次的字母字符串进行压缩。如输入:xxxxtttl  输出:4x3t1l
	 >compressRepeatedStr: function(value, ignoreCase)
	 
-  中文校验
	 >isChinese: function(value)	 
	 
-  去掉字符串中的中文字符
	 >removeChinese: function(value)	 

-  转义字符串中的元字符
     >escapeMetacharacterOfStr: function(value)
 
-  中文转为unicode编码
     >chineseToUnicode: function(value)	 
 



### 4、身份证校验； 
-  18位身份证简单校验
	>	isIdCard18Simple: function(idCard) 

-  15位身份证简单校验
	>	isIdCard15Simple: function(idCard) 

-  18位身份证严格校验
	>	isIdCard: function(idCard) 
-  根据18身份证号码获取人员信息
	>	getPersonInfo:function(idCard)


### 5、日期相关
-  获取当前时间
    > getCurrentTime:function()

```
EasyCheck.IdCardUtils.getCurrentTime();
```
```
2017-9-1 16:28:50
```

-  比较时间大小(1 , -1 , 0)
    > compareTime: function(time1, time2)

-  是否闰年
    >	isLeapYear: function(year) 

-  获取某个月的天数，从0开始
    >	getDaysOfMonth: function(year, month)

-  距离现在几天的日期：负数表示今天之前的日期，0表示今天，整数表示未来的日期. 如-1表示昨天的日期，0表示今天，2表示后天
	>	fromToday: function(days) 

-  /**
		 * 日期时间格式化
		 * @param {Object} dateTime 需要格式化的日期时间
		 * @param {String} pattern  格式化的模式，
		 * 如yyyy-MM-dd hh(HH):mm:ss.S a k K E D F w W z Z
		 */
    >	format: function(dateTime, pattern)

```
//demo
Bee.DateUtils.formt(new Date(),'yyyy-MM-dd hh(HH):mm:ss.S a k K E D F w W z Z');
```
```
2017-09-01 04(16):37:25.246 下午 16 4 五 244 0 35 1 GMT +0800
```
```
//demo
Bee.DateUtils.formt(new Date(),'yyyy年MM月dd日  a hh(HH)时mm分ss秒S毫秒 星期E 今年的第D天  这个月的第W周 今年的第w周');
```
```
2017年09月01日  下午 05(17)时07分14秒678毫秒 星期五 今年的第244天  这个月的第1周 今年的第35周
```
-  计算一个日期是当年的第几天
	>	dayOfTheYear: function(date)

-  获得时区名和值
    > getZoneNameValue: function(dateObj) 

### 6、数组； 
-  获取数组最大值
	>	getMaxValue: function(array) 

-  获取数组最小值
	>	getMinValue: function(array) 


# 持续更新...


### create by xiatl
xiatianlong@hotmail.com   


