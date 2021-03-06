# 1、初识Java





# 2、熟悉Eclipse开发工具





# 3、Java语言基础





# 4、流程控制





# 5、字符串



## 5.1、String类



## 5.2、连接字符串



## 5.3、获取字符串信息



## 5.4、字符串操作

### 5.4.8、字符串分割

1. 哪些字符用作分割符需要转义？

   答：”|.+*^?[\\{()$”。

   代码1：将”.”作为分割符。

   ```java
   String str="192.168.0.1";
   String[] firstArray=str.split("\\.");
   System.out.println("str的原值为：[" + str + "]");
   System.out.println("全部分割的结果：");
   for(String a : firstArray) {
   	System.out.print("[" + a + "]");
   }
   ```

   输出1：

   ```txt
   str的原值为：[192.168.0.1]
   全部分割的结果：
   [192][168][0][1]
   ```

   总结1：

   - 使用”.”作为分割符，在split()方法中要使用”\\”进行转义，即str.split(“\\.”)。

   

   代码2：将”|”作为分割符。

   ```java
   String str="192|168|0|1";
   String[] firstArray=str.split("\\|");
   System.out.println("str的原值为：[" + str + "]");
   System.out.println("全部分割的结果：");
   for(String a : firstArray) {
   	System.out.print("[" + a + "]");
   }
   ```

   输出2：

   ```txt
   str的原值为：[192|168|0|1]
   全部分割的结果：
   [192][168][0][1]
   ```

   总结2：

   - 使用”.”作为分割符，在split()方法中要使用”\\”进行转义，即str.split(“\\|”)。
   - 对于以上转义字符，如果要用split()方法分割，写法为str.split(“\\转义字符”)。



## 5.5、格式化字符串

### 5.5.1、日期和时间字符串格式化

1. 常用的日期格式化转换符

   代码1：采用转化符“%te”

   ```java
   Date date=new Date();				   // 创建Date对象data
   String day=String.format("%te", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(day);
   ```

   输出1：

   ```txt
   Wed May 27 14:32:39 CST 2020
   27
   ```

   总结1：

   - “%te”可以输出Date对象data中“年月日”中的“日”。

   

   代码2：采用转化符“%tb”

   ```java
   Date date=new Date();					// 创建Date对象data
   String month=String.format("%tb", date);// 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(month);
   ```

   输出2：

   ```txt
   Wed May 27 14:45:27 CST 2020
   5月
   ```

   总结2：

   - “%tb”可以显示指定语言环境月份简称。

   

   代码3：采用转化符“%tB”

   ```java
   Date date=new Date();					// 创建Date对象data
   String month=String.format("%tB", date);  // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(month);
   ```

   输出3：

   ```txt
   Wed May 27 14:50:28 CST 2020
   五月
   ```

   总结3：

   - “%tB”可以显示指定语言环境月份全称。

   

   代码4：采用转化符“%tA”

   ```java
   Date date=new Date();					// 创建Date对象data
   String week=String.format("%tA", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(week);
   ```

   输出4：

   ```txt
   Wed May 27 14:52:46 CST 2020
   星期三
   ```

   总结4：

   - “%tA”可以显示指定语言环境星期几的全称。

   

   代码5：采用转化符“%ta”

   ```java
   Date date=new Date();					// 创建Date对象data
   String week=String.format("%ta", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(week);
   ```

   输出5：

   ```txt
   Wed May 27 14:55:03 CST 2020
   周三
   ```

   总结5：

   - “%ta”可以显示指定语言环境星期几的简称。

   

   代码6：采用转化符“%tc”

   ```java
   Date date=new Date();					// 创建Date对象data
   String anotherData=String.format("%tc", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(anotherData);
   ```

   输出6：

   ```txt
   Wed May 27 14:56:15 CST 2020
   周三 5月 27 14:56:15 CST 2020
   ```

   总结6：

   - “%tc”是另一种显示全部日期和时间信息的格式。

   

   代码7：采用转化符“%tY”

   ```java
   Date date=new Date();					// 创建Date对象data
   String year=String.format("%tY", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(year);
   ```

   输出7：

   ```txt
   Wed May 27 14:59:46 CST 2020
   2020
   ```

   总结7：

   - “%tY”可以显示“年月日”中的4位“年”。

   

   代码8：采用转化符“%tj”

   ```java
   Date date=new Date();					// 创建Date对象data
   String whichDay=String.format("%tj", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(whichDay);
   ```

   输出8：

   ```txt
   Wed May 27 15:03:11 CST 2020
   148
   ```

   总结8：

   - “%tj”可以显示一个Date对象date的日期是所属年的哪一天。

   

   代码9：采用转化符“%tm”

   ```java
   Date date=new Date();					// 创建Date对象data
   String month=String.format("%tm", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(month);
   ```

   输出9：

   ```txt
   Wed May 27 15:07:37 CST 2020
   05
   ```

   总结9：

   - “%tm”可以显示二位数字月份。

   

   代码10：采用转化符“%td”

   ```java
   Date date=new Date();					// 创建Date对象data
   String day=String.format("%td", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(day);
   ```

   输出10：

   ```txt
   Wed May 27 15:13:22 CST 2020
   27
   ```

   总结10：

   - “%td”和”%te”的区别是“%td”显示的是“年月日”中的二位数字“日”。

   

   代码11：采用转化符“%ty”

   ```java
   Date date=new Date();					// 创建Date对象data
   String year=String.format("%ty", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(year);
   ```

   输出11：

   ```txt
   Wed May 27 15:17:39 CST 2020
   20
   ```

   总结11：

   - “%ty”可以显示二位数字年份。

   

2. 时间格式化转换符

   代码1：采用转化符“%tH”

   ```java
   Date date=new Date();					// 创建Date对象data
   String hour=String.format("%tH", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(hour);
   ```

   输出1：

   ```txt
   Wed May 27 15:23:04 CST 2020
   15
   ```

   总结1：

   - “%tH”可以显示二位数字24时制的小时。

   

   代码2：采用转化符“%tI”

   ```java
   Date date=new Date();					// 创建Date对象data
   String hour=String.format("%tI", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(hour);
   ```

   输出2：

   ```txt
   Wed May 27 15:25:01 CST 2020
   03
   ```

   总结2：

   - “%tI”可以显示二位数字12时制的小时。

   

   代码3：采用转化符“%tk”

   ```java
   Date date=new Date();					// 创建Date对象data
   String hour=String.format("%tk", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(hour);
   ```

   输出3：

   ```txt
   Wed May 27 15:26:28 CST 2020
   15
   ```

   总结3：

   - “%tk”和“%tH”的区别就是5小时显示的是“5”而不是“05”。

   

   代码4：采用转化符“%tl”

   ```java
   Date date=new Date();					// 创建Date对象data
   String hour=String.format("%tl", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(hour);
   ```

   输出4：

   ```txt
   Wed May 27 15:29:28 CST 2020
   3
   ```

   总结4：

   - “%tl”与”%tI”的区别是5小时小时“5”而不是“05”。

   

   代码5：采用转化符“%tM”

   ```java
   Date date=new Date();					// 创建Date对象data
   String minute=String.format("%tM", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(minute);
   ```

   输出5：

   ```txt
   Wed May 27 15:33:47 CST 2020
   33
   ```

   总结5：

   - “%tM”可以显示二位数字分钟。

   

   代码6：采用转化符“%tS”

   ```java
   Date date=new Date();					// 创建Date对象data
   String second=String.format("%tS", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(second);
   ```

   输出6：

   ```txt
   Wed May 27 15:36:19 CST 2020
   19
   ```

   总结6：

   - “%tS”可以显示二位数字秒钟。

   

   代码7：采用转化符“%tL”

   ```java
   Date date=new Date();					// 创建Date对象data
   String milliSecond=String.format("%tL", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(milliSecond);
   ```

   输出7：

   ```txt
   Wed May 27 15:39:45 CST 2020
   892
   ```

   总结7：

   - “%tL”可以显示三位数字毫秒。

   

   代码8：采用转化符“%tN”

   ```java
   Date date=new Date();					// 创建Date对象data
   String microSecond=String.format("%tN", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(microSecond);
   ```

   输出8：

   ```txt
   Wed May 27 15:50:53 CST 2020
   456000000
   ```

   总结8：

   - “%tN”可以显示9位微秒。

   

   代码9：采用转化符“%tp”

   ```java
   Date date=new Date();					// 创建Date对象data
   String morningOrAfternoon=String.format("%tp", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(morningOrAfternoon);
   ```

   输出9：

   ```txt
   Wed May 27 15:52:11 CST 2020
   下午
   ```

   总结9：

   - “%tp”可以显示指定语言环境的上下午。

   

   代码10：采用转化符“%tz”

   ```java
   Date date=new Date();					// 创建Date对象data
   String timeZoneOffset=String.format("%tz", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(timeZoneOffset);
   ```

   输出10：

   ```txt
   Wed May 27 15:54:28 CST 2020
   +0800
   ```

   总结10：

   - “%tz”可以显示相对于GMTRFC82格式的数字时区偏移量。

   

   代码11：采用转化符“%tZ”

   ```java
   Date date=new Date();					// 创建Date对象data
   String timeZone=String.format("%tZ", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(timeZone);
   ```

   输出11：

   ```txt
   Wed May 27 15:57:50 CST 2020
   CST
   ```

   总结11：

   - “%tZ”可以显示时区缩写的字符串。

   

   代码12：采用转化符“%ts”

   ```java
   Date date=new Date();					// 创建Date对象data
   String passedSecond=String.format("%ts", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(passedSecond);
   ```

   输出12：

   ```txt
   Wed May 27 15:59:32 CST 2020
   1590566372
   ```

   总结12：

   - “%ts”可以显示从1970-01-01 00:00:00至现在经过的秒数。

   

   代码13：采用转化符“%tQ”

   ```java
   Date date=new Date();					// 创建Date对象data
   String passedMillisecond=String.format("%tQ", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(passedMillisecond);
   ```

   输出13：

   ```txt
   Wed May 27 16:02:14 CST 2020
   1590566534984
   ```

   总结13：

   - “%tQ”可以显示从1970-01-01 00:00:00至现在经过的毫秒数。

   

3. 常见的日期和时间组合的格式

   代码1：采用转化符“%tF”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tF", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出1：

   ```txt
   Wed May 27 16:10:10 CST 2020
   2020-05-27
   ```

   总结1：

   - “%tF”显示的格式形如0000-00-00。

   

   代码2：采用转化符“%tD”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tD", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出2：

   ```txt
   Wed May 27 16:12:07 CST 2020
   05/27/20
   ```

   总结2：

   - “%tD”显示的格式形如00/00/00。

   

   代码3：采用转化符“%tc”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tc", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出3：

   ```txt
   Wed May 27 16:14:47 CST 2020
   周三 5月 27 16:14:47 CST 2020
   ```

   总结3：

   - “%tc”显示的格式如上。

   

   代码4：采用转化符“%tr”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tr", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出4：

   ```txt
   Wed May 27 16:16:29 CST 2020
   04:16:29 下午
   ```

   总结4：

   - “%tr”可以显示“时分秒”和上下午。

   

   代码5：采用转化符“%tT”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tT", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出5：

   ```txt
   Wed May 27 16:17:31 CST 2020
   16:17:31
   ```

   总结5：

   - “%tT”可以显示“时分秒”。

   

   代码6：采用转化符“%tR”

   ```java
   Date date=new Date();					// 创建Date对象data
   String yearMonthDay=String.format("%tR", date); // 通过format()方法对date进行格式化
   System.out.println(date);
   System.out.println(yearMonthDay);
   ```

   输出6：

   ```txt
   Wed May 27 16:18:36 CST 2020
   16:18
   ```

   总结6：

   - “%tR”可以显示时分。

   

### 5.5.2、常规类型格式化

1. 常规转换符

   代码1：采用转换符”%b”或”%B”

   ```java
   // 测试3>5转化成boolean格式的字符串
   String boolTest=String.format("%b", 3>5);
   System.out.println(3>5);
   System.out.println("测试3>5转化成boolean格式的字符串:" + boolTest);
   // 测试3转化成boolean格式的字符串
   String boolTest1=String.format("%b", 3);
   System.out.println(3);
   System.out.println("测试3转化成boolean格式的字符串:" + boolTest1);
   // 测试0转化成boolean格式的字符串
   String boolTest2=String.format("%b", (int)0);
   System.out.println(0);
   System.out.println("测试0转化成boolean格式的字符串:" + boolTest2);
   // 测试-1转化成boolean格式的字符串
   String boolTest3=String.format("%b", -1);
   System.out.println(-1);
   System.out.println("测试-1转化成boolean格式的字符串:" + boolTest3);
   // 测试null转化成boolean格式的字符串
   String boolTest4=String.format("%b", null);
   System.out.println("null");
   System.out.println("测试null转化成boolean格式的字符串:" + boolTest4);
   ```

   输出1：

   ```txt
   false
   测试3>5转化成boolean格式的字符串:false
   3
   测试3转化成boolean格式的字符串:true
   0
   测试0转化成boolean格式的字符串:true
   -1
   测试-1转化成boolean格式的字符串:true
   null
   测试null转化成boolean格式的字符串:false
   ```

   总结1：

   - ”%b”或”%B”可以将3>5这个Boolean类型的变量转化成boolean格式的字符串。

   

   代码2：采用转化符”%h”或”%H”

   ```java
   // 测试long类型变量num的散列码
   long num=32123133132132123L;
   String longTest=String.format("%h", num);
   System.out.println("测试long类型变量num的散列码:" + longTest);
   ```

   输出2：

   ```txt
   测试long类型变量num的散列码:c31bd0ca
   ```

   总结2：

   - ”%h”或”%H”可以获取一个变量的散列码。可以用HashMap利用散列码和该变量值形成一个键值对，做到对该变量的快速查询。

   - 散列码就是通过一种不可逆的散列(hash)算法，对一个数据进行计算，获得一个“唯一”的值。这个值可以对这个数据进行标识，在查找数据的时候，可以通过这个值来快速定位数据，从而有效减少开销。	
   - 由于散列长度是有限和固定的，因抄此在数据极多的情况下散列值会出现重复，用术语讲就是“碰撞”。这个时候就需要其它方法来消除这种碰撞，比如再散列、拉链算法等。

   

   代码3：采用转化符”%s”或”%S”

   ```java
   // 测试long类型变量num转换成字符串
   long num=23423432423423423L;
   String longTest=String.format("%s", num);
   System.out.println("测试long类型变量num转换成字符串:" + longTest);
   ```

   输出3：

   ```txt
   测试long类型变量num转换成字符串:23423432423423423
   ```

   总结3：

   - ”%s”或”%S”可以将一个变量变成字符串。比较接近C++的语法。

   

   代码4：采用转化符”%c”或”%C”

   ```java
   // 测试int类型变量num转换成对应字符
   int num=83;
   String intTest=String.format("%c", num);
   System.out.println("测试int类型变量num转换成对应字符:" + intTest);
   ```

   输出4：

   ```txt
   测试int类型变量num转换成对应字符:S
   ```

   总结4：

   - 如果第二个参数是int类型，使用转换符”%c”或”%C”，会按照ascii码进行转化。

   

   代码5：采用转化符”%d”

   ```java
   // 测试int类型变量num转换成对应十进制的字符串
   int num=01232;                                  // 一个八进制数
   String intTest=String.format("%d", num);
   System.out.println("测试int类型变量num转换成对应十进制的字符串:" + intTest);
   ```

   输出5：

   ```txt
   测试int类型变量num转换成对应十进制的字符串:666
   ```

   总结5：

   - ”%d”可以将非十进制整数转换成符合十进制规则的字符串输出。

   

   代码6：采用转化符”%o”

   ```java
   // 测试int类型变量num转换成对应八进制的字符串
   int num=333; // 一个十进制数
   String intTest=String.format("%o", num);
   System.out.println("测试int类型变量num转换成对应八进制的字符串:" + intTest);
   ```

   输出6：

   ```txt
   测试int类型变量num转换成对应八进制的字符串:515
   ```

   总结6：

   - ”%o”可以将非八进制整数转换成符合八进制规则的字符串输出。

   

   代码7：采用转化符”%x”或”%X”

   ```java
   // 测试int类型变量num转换成对应十六进制的字符串
   int num=333; // 一个十进制数	
   String intTest=String.format("%x", num);
   System.out.println("测试int类型变量num转换成对应十六进制的字符串:" + intTest);
   ```

   输出7：

   ```txt
   测试int类型变量num转换成对应十六进制的字符串:14d
   ```

   总结7：

   - ”%x”可以将非八进制整数转换成符合十六进制规则的字符串输出。

   

   代码8：采用转化符”%e”

   ```java
   // 测试float类型变量num转换成对应计算机科学计数法表示的十进制的字符串
   float num=1000000.00f; // 一个十进制数
   String floatTest=String.format("%e", num);
   System.out.println("测试floatTest类型变量num转换成对应计算机科学计数法表示的十进制的字符串:" + floatTest);
   ```

   输出8：

   ```txt
   测试int类型变量num转换成对应计算机科学计数法表示的十进制的字符串:1.000000e+06
   ```

   总结8：

   - ”%e”可以将一个float类型转换成符合计算机科学计数法的十进制的字符串输出。

   

   代码9：采用转化符”%a”

   ```java
   // 测试float类型变量num转换成对应带有效位数和指数的十六进制浮点数的字符串
   float num=1000000.00f; // 一个十进制数
   String floatTest=String.format("%a", num);
   System.out.println("测试float类型变量num转换成对应带有效位数和指数的十六进制浮点数的字符串:" + floatTest);
   ```

   输出9：

   ```txt
   测试float类型变量num转换成对应带有效位数和指数的十六进制浮点数的字符串:0x1.e848p19
   ```

   总结9：

   - ”%a”可以将一个float类型转换成对应带有效位数和指数的十六进制浮点数的字符串。



## 5.6、使用正则表达式



## 5.7、字符串生成器

1. StringBuffer和StringBuilder的区别

   StringBuffer 和 StringBuilder 它们都是可变的字符串，而String类型是不可变的字符串，只能对字符常量进行操作，虽然可以通过“+”运算符进行字符串的拼接，但是每次拼接都会在内存创建一个新的字符对象，然后修改原String对象的索引，如果拼接的次数多了，会造成内存的负担。
   
   - 区别1：线程安全
   
     StringBuffer：线程安全，StringBuilder：线程不安全。因为 StringBuffer 的所有公开方法都是 synchronized 修饰的，而 StringBuilder 并没有 synchronized 修饰。
   
     StringBuffer 代码片段：
   
     ```java
     @Override
     public synchronized StringBuffer append(String str) {
         toStringCache = null;
         super.append(str);
         return this;
     }
     ```
   
     因此StringBuffer相比于StringBuilder在节约内存的同时，还保证了线程安全。详细的关于StringBuffer和StringBuilder的说明参见Java API。
   
     代码1：StringBuffer的创建与使用append方法进行字符串附加
   
     ```java
     // 创建一个新的StringBuffer对象并赋初值
     StringBuffer sbf=new StringBuffer("门前大桥下，");
     // 调用append方法进行字符串的修改，传入的参数可以是一个字符串
     sbf.append("游过一群鸭，");
     // 创建一个新的StringBuffer对象并赋初值
     StringBuffer tmp=new StringBuffer("快来快来数一数，");
     // 调用append方法进行字符串的修改，传入的参数可以是一个字符串生成器
     sbf.append(tmp);
     int x=24678;
     // 调用append方法进行字符串的修改，传入的参数可以是一个整数
     sbf.append(x);
     System.out.println(sbf.toString());
     ```
   
     输出1：
   
     ```txt
     门前大桥下，游过一群鸭，快来快来数一数，24678
     ```
   
     总结1：
   
     - XXX
   
     代码2：StringBuffer的创建与使用setCharAt方法修改字符串的某个位置的字符
   
     ```java
     StringBuffer sbf = new StringBuffer("0123456");
     sbf.setCharAt(3, 'A');
     System.out.println(sbf);
     ```
   
     输出2：
   
     ```txt
     012A456
     ```
   
     总结2：
   
     - XXX
   
     代码3：使用insert方法将某个字符串的到字符串生成器的某个位置
   
     ```java
     StringBuffer sbf=new StringBuffer("0123456");
     sbf.insert(5, "F");
     System.out.println(sbf);
     ```
   
     输出3：
   
     ```txt
     01234F56
     ```
   
     总结3：
   
     - XXX
   
     代码4：使用delete方法将删除子字符串
   
     ```java
     StringBuffer sbf=new StringBuffer("天行健，君子以自强不息");
     sbf=sbf.delete(4, 7);
     System.out.println(sbf);
     ```
   
     输出4：
   
     ```txt
     天行健，自强不息
     ```
   
     总结4：
   
     - XXX
   
     StringBuilder几乎和StringBuffer一样，只是单线程运行效率更高。
   
     以下是StringBuffer，StringBuilder和String的不同之处：
   
     ![img](file:///C:\Users\24189\AppData\Roaming\Tencent\Users\2418942810\TIM\WinTemp\RichOle\(AT[XJ{O[BV9CRV8]Y~)1@O.png)
   
     
   
     ![img](file:///C:\Users\24189\AppData\Roaming\Tencent\Users\2418942810\TIM\WinTemp\RichOle\%7@]_125R_93`LJ557`GV`S.png)
   
     
   
     ![img](file:///C:\Users\24189\AppData\Roaming\Tencent\Users\2418942810\TIM\WinTemp\RichOle\RRY[}SMHW93N$W94BPCVWCL.png)
   
   
   
   - 区别2：缓冲区
   
     StringBuffer 代码片段：
   
     ```java
     private transient char[] toStringCache;
     
     @Override
     public synchronized String toString() {
         if (toStringCache == null) {
             toStringCache = Arrays.copyOfRange(value, 0, count);
         }
         return new String(toStringCache, true);
     }
     ```
   
     StringBuilder 代码片段：
   
     ```java
     @Override
     public String toString() {
         // Create a copy, don't share the array
         return new String(value, 0, count);
     }
     ```
   
     可以看出，StringBuffer 每次获取 toString 都会直接使用缓存区的 toStringCache 值来构造一个字符串。
   
     而 StringBuilder 则每次都需要复制一次字符数组，再构造一个字符串。
   
     所以，缓冲区是对 StringBuffer 的一个优化吧，不过 StringBuffer 的这个toString 方法仍然是同步的。
   
   - 区别3：性能
   
     既然 StringBuffer 是线程安全的，它的所有公开方法都是同步的，StringBuilder 是没有对方法加锁同步的，所以毫无疑问，StringBuilder 的性能要远大于 StringBuffer。
     
   - 总结：
   
     所以，StringBuffer 适用于用在多线程操作同一个 StringBuffer 的场景，如果是单线程场合StringBuilder 更适合。

# 6、数组



## 6.1、数组概述



## 6.2、一维数组的创建和使用

### 6.2.1、创建一维数组

1. 声明的同时为数组分配内存的两种写法

   ```java
   int arr[]=new int[234234];
   int[] arr1=new int[234234];
   ```

### 6.2.2、初始化一维数组

1. 采用初始化的方法创建一维数组，内存如何分配

   代码1：测试初试化数组的系统分配数组的内存大小

   ```java
   int[] arr={1, 2, 3, 4, 5}; // 第一种初始化的方法
   int[] arr1=new int[2342342]; // 申明数组变量的同时为变量申请内存
   int[] arr2=new int[]{1, 2, 3, 4, 5}; // 第二种初始化方法
   System.out.println(arr.length);
   System.out.println(arr1.length);
   System.out.println(arr2.length);
   ```

   输出1：

   ```txt
   5
   2342342
   5
   ```

   总结1：

   - 由以上代码可见，初始化的时候大括号里面有多少元素，系统就会自动申请多少内存。

## 6.3、二维数组的创建及使用

### 6.3.2、二维数组的初始化

1. 二维数组初始化样例

   代码1：二维数组初始化样例

   ```java
   // 声明一个二维数组并初始化
   int arr[][]= {{1, 2}, {3, 4}, {5, 6}, {7, 8}};
   System.out.println(arr.length);
   System.out.println(arr[0].length);
   ```

   输出1：

   ```txt
   4
   2
   ```

### 6.3.3、使用二维数组

1. 遍历二维数组的写法

   代码1：遍历二维数组

   ```java
   int a[][]=new int[3][4];
   // 注意下面是如何使用二维数组对象的成员变量length的
   for(int i=0;i<a.length;i++) {
       for(int j=0;j<a[i].length;j++) {
           System.out.print(a[i][j]);
       }
       System.out.println();
   }
   ```

   输出1：

   ```txt
   0000
   0000
   0000
   ```

   总结1：整型数组分配内存后默认初始值为0。获取每一维的长度可以调用length参数。

### 6.4.1、遍历数组

1. 使用foreach遍历二维数组

   代码1：foreach遍历二维数组

   ```java
   // 定义二维数组并初始化
   int arr2[][]= {{4, 3}, {1, 2}};
   System.out.println("数组中的元素是：");
   // 定义外层计数器变量
   int i=0;
   // 外层循环变量为一维数组
   for(int x[] : arr2) {
       // 外层计数器递增
       i++;
       // 定义内层循环计数器
       int j=0;
       // 循环遍历每一个数组元素
       for(int e : x) {
           // 内层计数器递增
           j++;
           // 判断是否为最后一个元素
           if(i == arr2.length && j == x.length) {
               System.out.print(e);
           } else {
               System.out.print(e+"、");
           }
       }
   }
   ```

   输出1：

   ```txt
   数组中的元素是：
   4、3、1、2
   ```

   注意1：掌握是否是最后一个元素的写法。

### 6.4.4、复制数组

1. 将一个分配了内存的数组直接赋值给另一个未分配内存的数组是否会指向共同的内存空间？

   代码1：

   ```java
   int arr[]=new int[] {1, 2, 4};
   int newArr[]=arr;
   /**
    *  将一个分配了内存的数组直接赋值给另一个数组，
    *  他们指向的内存地址相同
    */
   System.out.println(newArr);
   System.out.println(arr);
   ```

   输出1：

   ```txt
   [I@2a17b7b6
   [I@2a17b7b6
   ```

   总结1：将一个分配了内存的数组直接赋值给另一个未分配内存的数组会指向共同的内存空间。

2. 使用copyOf()方法进行数组复制

   代码2：使用copyOf()方法

   ```java
   int arr[]=new int[] {1, 2, 4};
   int newarr[]=Arrays.copyOf(arr, 5);
   // 查看是否指向同一个内存
   System.out.println(arr);
   System.out.println(newarr);
   // 输出每个元素
   for(int val : newarr) {
       System.out.println(val);
   }
   ```

   输出2：

   ```txt
   [I@76707e36
   [I@614ddd49
   1
   2
   4
   0
   0
   ```

   总结2：复制的一个数组和原数组的内存空间是不一样的。对于整型数组，如果指定的长度大于原数组长度，那么会自动补0。

### 6.4.5、数组查询

1. 关于binarySearch()方法返回值的问题

   代码1：

   ```java
   int arr[]=new int[] {4, 25, 10};
   Arrays.sort(arr);
   int index=Arrays.binarySearch(arr, 10);
   int index1=Arrays.binarySearch(arr, 3);
   int index2=Arrays.binarySearch(arr, 8);
   int index3=Arrays.binarySearch(arr, 11);
   int index4=Arrays.binarySearch(arr, 26);
   System.out.println(index);
   System.out.println(index1);
   System.out.println(index2);
   System.out.println(index3);
   System.out.println(index4);
   ```

   输出1：

   ```txt
   1
   -1
   -2
   -3
   -4
   ```

   总结1：如果查询成功会返回对应的下标，如果没有成功会返回一个负数，这个负数的绝对值就是第一个比要查询的数大的数是数组中的第几个数（从1开始，而不是0），如果查询的数最大，那么绝对值就是数组的长度。

# 7、类和对象

## 7.4、静态变量、常量和方法

1. 关于静态代码块的执行

   代码1：

   ```java
   public class StaticTest {
   	
   	public static int test;
   
   	static {
   		test=1;
   		System.out.println("这里是静态代码块！");
   	}
   	
   	{
   		System.out.println("这里是非静态代码块！");
   	}
   	
   	public StaticTest() {
   		System.out.println("这里是构造方法！");
   	}
   	
   	public void method() {
   		System.out.println("这里是成员方法！");
   	}
   	
   	public static void main(String[] args) {
   		
   		StaticTest st = new StaticTest();
   		st.method();
   		System.out.println(StaticTest.test);
   		StaticTest st1 = new StaticTest();
   		st1.method();
   		System.out.println(StaticTest.test);
   		
   	}
   	
   }
   ```

   输出1：

   ```txt
   这里是静态代码块！
   这里是非静态代码块！
   这里是构造方法！
   这里是成员方法！
   1
   这里是非静态代码块！
   这里是构造方法！
   这里是成员方法！
   1
   ```

   总结1：

   - 以上就是在声明一个对象的时候各个代码块执行的先后顺序。
   - 如果将静态代码块和非静态代码块前后顺序互换，先执行的依然是静态代码块。
   - 当根据一个类创建多个对象的时候，静态代码块只执行一次。
   - 可以利用静态代码块对一个类的静态成员变量赋值。

## 7.5、类的主方法

1. 关于住房法中的args参数

   String [] args为一个字符数组，表示命令行参数，当需要在命令行向主函数传入参数时，args就起作用啦。

# 8、包装类

## 8.1、Integer

1. 关于Integer类的两种构造方法

   代码1：Integer类有以下两种构造方法

   ```java
   Integer num = new Integer(123);
   Integer num1 = new Integer("345");
   ```

   总结1：

   - 这两个方法如果在eclipse上编写，new关键字后面的Integer会有一个删除线，意思就是虽然这两个构造方法是可以完成创建Integer对象的工作，但是当前最新的JDK版本已经将这两种方法弃用了，这两种构造方法对应的最新版本推荐的方法见：代码2。

   代码2：Integer类有以下两种创建方法

   ```java
   // 对应 Integer num = new Integer(123);
   Integer num1=Integer.valueOf(123);
   // 对应 Integer num1 = new Integer("345");
   Integer num1=Integer.valueOf("345");
   ```

   总结2：

   - 这是目前比较推荐的两种静态创建方法。

2. 关于Integer常用的方法

   代码1：测试Integer类的各种方法

   ```java
   System.out.println("以下是测试Integer类的常用方法：");
   Integer num = Integer.valueOf(333);
   System.out.println("\n输出静态方法valueOf返回的Integer对象的类型：" + num.getClass());
   System.out.println("输出静态方法valueOf返回的Integer对象num的值：" + num);
   int cmpto1=num.compareTo(350);
   int cmpto2=num.compareTo(333);
   int cmpto3=num.compareTo(300);
   System.out.println("\n输出compareTo()方法中的anothernum > num 的情况：" + cmpto1);
   System.out.println("输出compareTo()方法中的anothernum = num 的情况：" + cmpto2);
   System.out.println("输出compareTo()方法中的anothernum < num 的情况：" + cmpto3);
   boolean eq1=num.equals(333);
   boolean eq2=num.equals(336);
   System.out.println("\n输出使用equals()方法两个比较的数相等的情况：" + eq1);
   System.out.println("输出使用equals()方法两个比较的数不相等的情况：" + eq2);
   int strToInt=Integer.parseInt("333");
   System.out.println("\n输出Integer类的静态方法parseInt()的返回值：" + strToInt);
   ```

   输出1：

   ```txt
   以下是测试Integer类的常用方法：
   
   输出静态方法valueOf返回的Integer对象的类型：class java.lang.Integer
   输出静态方法valueOf返回的Integer对象num的值：333
   
   输出compareTo()方法中的anothernum > num 的情况：-1
   输出compareTo()方法中的anothernum = num 的情况：0
   输出compareTo()方法中的anothernum < num 的情况：1
   
   输出使用equals()方法两个比较的数相等的情况：true
   输出使用equals()方法两个比较的数不相等的情况：false
   
   输出Integer类的静态方法parseInt()的返回值：333
   
   ```

   总结1：

   - valueOf可以根据传入的参数创建一个Integer对象。其是一个静态方法。
   - compareTo()方法是一个实例方法，需要通过实例名.方法名来使用，如果传入的参数大于Integer对象中的int值，那么会返回一个大于0的数，等于则会返回一个等于0的数，小于就会返回一个小于0的数。
   - equals()方法是一个实例方法，需要通过实例名.方法名来使用，可以判断传入的参数和Integer对象中的值是否相等。
   - parseInt()方法是Integer类的一个静态方法，其可以将传入的参数变成一个int类型返回，注意，返回的是int类型。

## 8.2、Boolean

1. 关于Boolean类的构造方法

   Boolean的构造方法和Integer类一样，最新的JDK版本已经弃用，取而代之的是Boolean.valueOf()静态方法。

2. 关于Boolean类中的常量

   代码1：测试Boolean类中的常量

   ```java
   System.out.println("Boolean.TRUE的类型是：" + Boolean.TRUE.getClass());
   System.out.println("Boolean.FALSE的类型是：" + Boolean.FALSE.getClass());
   ```

   输出1：

   ```txt
   Boolean.TRUE的类型是：class java.lang.Boolean
   Boolean.FALSE的类型是：class java.lang.Boolean
   ```

   总结1：

   - Boolean类中的静态常量TRUE和FALSE分别是boolean值为true和false的Boolean对象。

# 9、数字处理类

## 9.1、数字格式化

1. DecimalFormat类中的格式化模板

   代码1：使用DecimalFormat()构造函数和applyPattern()方法。

   ```java
   package Number;
   
   import java.text.DecimalFormat;
   
   public class DecimalFormatSimpleDemo {
   	
   	// 通过构造方法创建DecimalFormat对象
   	static public void simgleFormat(String pattern, double value) {
   		
   		DecimalFormat myFormat=new DecimalFormat(pattern);
   		String output=myFormat.format(value);
   		System.out.println("\n格式化模板：" + pattern);
   		System.out.println("原先的数字：" + value);
   		System.out.println("格式化后的数字：" + output);
   		
   	}
   	
   	// 使用applyPattern()方法对数字进行格式化
   	static public void useApplyPatternMethodFormat(String pattern, double value) {
   		
   		DecimalFormat myFormat=new DecimalFormat();
   		myFormat.applyPattern(pattern);
   		String output=myFormat.format(value);
   		System.out.println("\n格式化模板：" + pattern);
   		System.out.println("原先的数字：" + value);
   		System.out.println("格式化后的数字：" + output);
   		
   	}
   
   	public static void main(String[] args) {
   		
   		String pattern="";
   		double value;
   		System.out.println("通过构造方法创建DecimalFormat对象，并初始化格式模板：");
   		pattern="###,###.###";
   		value=123456.789;
   		simgleFormat(pattern, value);
   		
   		pattern="00000000.###kg";
   		value=123456.789;
   		simgleFormat(pattern, value);
   		
   		pattern="000000.00";
   		value=123.78;
   		simgleFormat(pattern, value);
   		
   		System.out.println("\n使用applyPattern()方法设置格式化模板：");
   		
   		pattern="#.###%";
   		value=0.789;
   		useApplyPatternMethodFormat(pattern, value);
   		
   		pattern="###.##";
   		value=123456.789;
   		useApplyPatternMethodFormat(pattern, value);
   		
   		pattern="0.00\u2030";
   		value=0.789;
   		useApplyPatternMethodFormat(pattern, value);
   		
   	}
   	
   }
   ```

   输出1：

   ```txt
   通过构造方法创建DecimalFormat对象，并初始化格式模板：
   
   格式化模板：###,###.###
   原先的数字：123456.789
   格式化后的数字：123,456.789
   
   格式化模板：00000000.###kg
   原先的数字：123456.789
   格式化后的数字：00123456.789kg
   
   格式化模板：000000.00
   原先的数字：123.78
   格式化后的数字：000123.78
   
   使用applyPattern()方法设置格式化模板：
   
   格式化模板：#.###%
   原先的数字：0.789
   格式化后的数字：78.9%
   
   格式化模板：###.##
   原先的数字：123456.789
   格式化后的数字：123456.79
   
   格式化模板：0.00‰
   原先的数字：0.789
   格式化后的数字：789.00‰
   
   ```

   总结1：

   - #字符：可以表示一个阿拉伯数字。如果整数部分位数没有格式化字符串#字符数多，那么多余的#会被省略，如果整数部分数字多于#字符，对于的整数部分是不会被省略的。对于小数部分来说，如果小数位数多于#个数，多余的会被四舍五入，如果小数位数少于#个数，则不会有任何变化。
   - 0字符：可以表示一个阿拉伯数字，如果整数部分位数没有格式化字符串0字符数多，那么多余的0是不会被省略，如果整数部分数字多于0字符，整数部分不会变。对于小数部分来说，如果小数位数多于0个数，多余的会被四舍五入，如果小数位数少于0个数，则会进行补0操作。
   - #.###%格式模板：会先根据格式模板#.###的要求把相应的浮点数变成格式化的数，之后对格式化后的数乘100，加上一个百分号。
   - .字符：小数点分隔符。
   - ,字符：分组分隔符。
   - %字符：将数字乘100，显示%字符。
   - \u2030：表示千分号，类似于百分号。

2. DecimalFormat类中设置分组的方法

   代码1：使用setGroupingSize()方法和setGroupingUsed()方法

   ```java
   package Number;
   
   import java.text.DecimalFormat;
   
   public class DecimalMethod {
   
   	
   	public static void main(String[] args) {
   		
   		DecimalFormat myFormat = new DecimalFormat();
   		myFormat.setGroupingSize(2);
   		String output=myFormat.format(123456.789444);
   		System.out.println("将数字以每两个数字分组：" + output);
   		myFormat.setGroupingUsed(false);
   		String output1=myFormat.format(123456.789444);
   		System.out.println("不允许数字分组：" + output1);
   		
   	}
   	
   }
   
   ```

   输出1：

   ```txt
   将数字以每两个数字分组：12,34,56.789
   不允许数字分组：123456.789
   ```

   总结1：

   - setGroupingSize()方法可以设置分成几组。
   - setGroupingUsed()方法可以设置是否分组。

## 9.3、随机数

### 9.3.1、Math.random()方法

1. Math.random()方法生成任意范围的随机数

   代码1：

   ```java
   System.out.println("生成num1~num2之间的随机数：");
   int num1=10;
   int num2=20;
   System.out.println("10~20的一个随机数为：" + (num1+(int)(Math.random()*(num2-num1))));
   ```

   输出1：

   ```txt
   生成num1~num2之间的随机数：
   10~20的一个随机数为：17
   ```

   总结1：

   - m+(int)(Math.random()*n)会返回一个大于等于m小于m+n的一个随机数。

2. Math.random()方法生成随机字符

   代码1：

   ```java
   package Number;
   
   public class MathRandomChar {
   
   	static public char GetRandomChar(char ch1, char ch2) {
   		return (char)(ch1 + (int)(Math.random()*(ch2-ch1+1)));
   	}
   	
   	public static void main(String[] args) {
   		
   		System.out.println("获取a~z的随机字符：" + GetRandomChar('a', 'z'));
   		System.out.println("获取A~Z的随机字符：" + GetRandomChar('A', 'Z'));
   		System.out.println("获取0~9的随机字符：" + GetRandomChar('0', '9'));
   		
   	}
   	
   }
   ```

   输出1：

   ```txt
   获取a~z的随机字符：x
   获取A~Z的随机字符：W
   获取0~9的随机字符：7
   ```

3. Math.random()方法的细节说明

   ​	计算机不会产生绝对随机的随机数，计算机只能产生“伪随机数”。其实绝对随机的随机数只是一种理想的随机数，即使计算机怎样发展，它也不会产生一串绝对随机的随机数。计算机只能生成相对的随机数，即伪随机数。

   ​	伪随机数并不是假随机数，这里的“伪”是有规律的意思，就是计算机产生的伪随机数既是随机的又是有规律的。怎样理解呢？产生的伪随机数有时遵守一定2113的规律，有时不遵守任何规律；伪随机数有一部分遵守一定的规律；另一部分不遵守任何规律。

   ​	所以Math.random()方法实际上是伪随机数，是通过复杂的运算而得到一系列的数的。该方法是以当前时间作为随机数生成器的参数，所以每次执行程序都会产生不同的随机数。

### 9.3.2、Random类

1. Random类常见的获取随机数的方法以及关于随机种子的说明

   代码1：

   ```java
   package Number;
   
   import java.util.Random;
   
   public class RandomDemo {
   	
   	public static void main(String[] args) {
   		
   		Random r = new Random();
   		System.out.println("随机产生一个整数：" + r.nextInt());
   		System.out.println("随机产生一个大于等于0小于10的整数：" + r.nextInt(10));
   		System.out.println("随机产生一个大于等于100小于200的整数：" + (100 + r.nextInt(200-100)));
   		System.out.println("随机产生一个布尔型的值：" + r.nextBoolean());
   		System.out.println("随机产生一个双精度：" + r.nextDouble());
   		System.out.println("随机产生一个浮点型：" + r.nextFloat());
   		System.out.println("随机产生一个概率密度为高斯分布的双精度值：" + r.nextGaussian());
   	}
   	
   }
   
   ```

   输出1：

   ```txt
   随机产生一个整数：-1662301671
   随机产生一个大于等于0小于10的整数：5
   随机产生一个大于等于100小于200的整数：184
   随机产生一个布尔型的值：true
   随机产生一个双精度：0.17160967354222334
   随机产生一个浮点型：0.5965727
   随机产生一个概率密度为高斯分布的双精度值：0.4985079487120251
   
   ```

   总结1：

   - 随机数和种子之间的关系遵从以下两个规则：

     种子不同，产生不同的随机数。

     种子相同，即使实例不同也产生相同的随机数。

     Random类的默认种子（无参构造）是System.nanoTime()的返回值（JDK 1.5版本以前默认种子是System.  currentTimeMillis()的返回值），注意这个值是距离某一个固定时间点的纳秒数，不同的操作系统和硬件有不同的固定时间点，也就是说不同的操作系统其纳秒值是不同的，而同一个操作系统纳秒值也会不同，随机数自然也就不同了。（顺便说下，System.nanoTime不能用于计算日期，那是因为“固定”的时间点是不确定的，纳秒值甚至可能是负值，这点与System. currentTimeMillis不同。）

     new Random(1000)显式地设置了随机种子为1000，运行多次，虽然实例不同，但都会获得相同的三个随机数。所以，除非必要，否则不要设置随机种子。

     顺便提一下，在Java中有两种方法可以获得不同的随机数：通过java.util.Random类获得随机数的原理和Math.random方法相同，Math.random()方法也是通过生成一个Random类的实例，然后委托nextDouble()方法的，两者是殊途同归，没有差别。

     所以，若非必要，不要设置随机数种子。

## 9.4、大数字运算

### 9.4.2、BigDecimal

1. BigDecimal的加减乘除运算

   代码1：BigDecimal的加减乘除运算方法的应用

   ```java
   package Number;
   
   import java.math.BigDecimal;
   
   public class BigDecimalDemo {
   	// 设置小数点后面的位数
   	static final int LOCATION=10;
   	// 加法
   	public BigDecimal add(double value1, double value2) {
   		
   		BigDecimal b1=new BigDecimal(Double.toString(value1));
   		BigDecimal b2=new BigDecimal(Double.toString(value2));
   		return b1.add(b2);
   	}
   	// 减法
   	public BigDecimal sub(double value1, double value2) {
   		
   		BigDecimal b1=new BigDecimal(Double.toString(value1));
   		BigDecimal b2=new BigDecimal(Double.toString(value2));
   		return b1.subtract(b2);
   	}
   	// 乘法
   	public BigDecimal mul(double value1, double value2) {
   		
   		BigDecimal b1=new BigDecimal(Double.toString(value1));
   		BigDecimal b2=new BigDecimal(Double.toString(value2));
   		return b1.multiply(b2);
   	}
   	// 减法
   	// 如果传入两个参数就调用下面那个传入三个参数的div方法
   	public BigDecimal div(double value1, double value2) {
   		return div(value1, value2, LOCATION);
   	}
   	
   	public BigDecimal div(double value1, double value2, int b) {
   		if(b<0) {
   			System.out.println("b 值必须大于等于0");
   		}
   		BigDecimal b1=new BigDecimal(Double.toString(value1));
   		BigDecimal b2=new BigDecimal(Double.toString(value2));
           // 下面第三个参数是近似处理模式
   		return b1.divide(b2, b, BigDecimal.ROUND_HALF_UP);
   	}
   	
   	public static void main(String[] args) {
   		
   		BigDecimalDemo b=new BigDecimalDemo();
   		double value1, value2;
   		
   		value1=-7.5;
   		value2=8.9;
   		System.out.println("两个数字相加结果：" + b.add(value1, value2));
   		
   		value1=-7.5;
   		value2=8.9;
   		System.out.println("两个数字相加结果：" + b.sub(value1, value2));
   		
   		value1=-7.5;
   		value2=8.9;
   		System.out.println("两个数字相加结果：" + b.mul(value1, value2));
   		
   		value1=10;
   		value2=2;
   		System.out.println("两个数字相加结果：" + b.div(value1, value2));
   		
   		value1=-7.5;
   		value2=8.9;
   		System.out.println("两个数字相加结果：" + b.div(value1, value2, 5));
   		
   	}
   	
   }
   
   ```

   输出1：

   ```txt
   两个数字相加结果：1.4
   两个数字相加结果：-16.4
   两个数字相加结果：-66.75
   两个数字相加结果：5.0000000000
   两个数字相加结果：-0.84270
   
   ```

   总结1：

   - 大浮点数的近似处理模式有很多，见课本a168。


# 10、接口、继承与多态

## 10.1、类的继承

1. 实例化子类对象的时候父类对象是否也会被实例化

   代码1：

   ```java
   package Number;
   
   class Parent {
   	
   	Parent() {
   		System.out.println("调用了父类的Parent()构造方法！");
   	}
   	
   }
   
   class SubParent extends Parent {
   	
   	SubParent() {
   		System.out.println("调用子类的SubParent()构造方法！");
   	}
   	
   }
   
   public class Subroutine extends SubParent {
   
   	public Subroutine() {
   		System.out.println("调用子类的Subroutine()构造方法！");
   	}
   	
   	public static void main(String[] args) {
   		
   		Subroutine s=new Subroutine();
   		
   	}
   	
   }
   
   ```

   输出1：

   ```txt
   调用了父类的Parent()构造方法！
   调用子类的SubParent()构造方法！
   调用子类的Subroutine()构造方法！
   
   ```

   总结1：

   - 在对子类进行实例化的时候，会先将他的父类先实例化，调用父类的构造函数，然后才会对子类进行实例化。
   - 在实例化子类对象时，父类无参构造方法将被自动调用，如果想要调用有参构造方法，只能使用super关键字显示地调用父类的构造方法。

