# <p align="center">R图形初阶</p>
<b>1.1 使用图形</b>
综述：在通常的交互式会话中，可以通过逐条输入语句构建图形，逐渐完善图形特征，直至达到想要的结果。
## 代码段一
<code>
attach(mtcars)
plot(wt,mpg)
abline(lm(mpg~wt))
title("Regression")
detach(mtcars)
</code>
相关解释
1. lm()函数
* 简单用法：lm(formula,data)
* 参数： formula 范式, data 可选的数据集
* 返回值：原文：lm returns an object of class "lm" or for multiple responses of class c("mlm", "lm").

2. abline()函数
* 简单用法：
  1. 水平线
     <code>
     abline(h=1,col="red")
     </code>
  2. 竖直线
     <code>
     abline(v=1.col="blue")
     </code>
  3. 多参数
     <code>
     abline(h = c(0,1,2), v = c(0,1,2), col = c("red", "green", "blue"))
     </code>
  4. 指定交点与斜率,a与y轴交点,b斜率
    <code>
    abline(a = 2 ,b = 1, col  = "blue")
    </code>
  5. 利用向量指定
    <code>
    abline(coef = c(2, 1), col = "blue")
    </code>


##  代码段二
<code>
pdf("myGraph.pdf")
attach(mtcars)
plot(wt,mpg)
abline(lm(mpg~wt))
title("Regression")
detach(mtcars)
dev.off()
</code>

相关解释：
1. 可以通过代码或用户界面来保存图形，将绘图语句夹在开启图形设备与关闭图形设备的语句之间即可。
2. 涉及：
* pdf()
* win.metafile()
* png()
* jpeg()
* bmp()
* tiff()
* xfig()
* postscript()

##  代码段三
<code>
dev.new()
  statements to create graph 1
dev.new()
  statements to cretae graph 2
etc
</code>

相关解释：
1. 创建多个图形，并随时查看每一个。

<b>3.2一个简单的例子</b>
##  代码段四
<code>
dose <- c(20, 30, 40, 45, 60)
drugA <- c(16, 20, 27, 40, 60)
drugB <- c(15, 18, 25, 31, 40)
plot(dose, drugA , type="b")
</code>

相关解释：
详见后续

<b>3.3图形参数</b>
总论：我们可以通过修改图形参数的选项来自定义一幅图形的多个特征(字体，颜色，坐标轴，标题等)
方法：通过函数par()来修改指定这些选项，除非再次被修改，否则在会话结束前一直有效、
## 代码段五
<code>
par(lty=2, pch=17)
plot(dose,drugA,type="b")
</code>

相关解释
