---
title: 速查表 - 基础数学
categories: Basics
toc_level: 2
tags: Notes
---

## 基础数学范围

### 数与运算

* 运算顺序：先括号 → 乘除 → 加减；同级自左向右。
* 绝对值： $$ \|x\|=\begin{cases}x,&x\ge0\\-x,&x<0\end{cases} $$ ； $$ \|ab\|=\|a\|\|b\| $$ ， $$ \|a+b\|\le\|a\|+\|b\| $$ 。
* 分数/百分数/小数： $$ \frac{a}{b}=a\div b $$ ；百分数=小数×100%。
* 因数与倍数：质合数、最大公因数（辗转相除）、最小公倍数（ $$ ab/\gcd(a,b) $$ ）。

**易错点**：1. 忘记先约分；2. 负号分配错误（特别是括号前有负号）；3. 近似值保留位数不清。

### 代数（恒等式·因式分解·方程/不等式）

* 常用恒等式：
   $$ (a\pm b)^2=a^2\pm2ab+b^2 $$ ； $$ a^2-b^2=(a-b)(a+b) $$ ；
   $$ a^3\pm b^3=(a\pm b)(a^2\mp ab+b^2. $$ 。
* 因式分解：提公因式；公式法；分组分解；十字相乘（整式二次）。
* 一元二次： $$ ax^2+bx+c=0\Rightarrow x=\frac{-b\pm\sqrt{b^2-4ac}}{2a} $$ ；顶点式配方。
* 根与系数：和 $$ -\frac{b}{a} $$ ，积 $$ \frac{c}{a} $$ （ $$ ax^2+bx+c=0 $$ ）。
* 不等式：同向加减不变号；乘除负数需**翻转**不等号；绝对值不等式分段。

**易错点**：1. 开平方忽略 $$ \pm $$ ；2. 乘负数未翻号；3. 忘写增根检查（分式/根式方程）。

### 函数常识

* 一次函数： $$ y=kx+b $$ ；斜率 $$ k $$  表示变化率。
* 二次函数： $$ y=ax^2+bx+c $$ ，对称轴 $$ x=-\frac{b}{2a} $$ ，顶点 $$ (-\frac{b}{2a},f(-\frac{b}{2a})) $$ 。
* 指数/对数： $$ a^{m}a^{n}=a^{m+n} $$ ， $$ (a^{m})^{n}=a^{mn} $$ ； $$ \log_a MN=\log_a M+\log_a N $$ ，换底 $$ \log_a b=\frac{\log_c b}{\log_c a} $$ 。

**易错点**：1. 指数/对数定义域遗漏（底 $$ a>0,a\neq1 $$ ；真数 $$ >0 $$ ）；2. 图像平移/伸缩方向记反。

### 三角（弧度·恒等·解三角）

* 角度↔弧度： $$ \theta_{\text{rad}}=\theta_{°}\cdot\frac{\pi}{180} $$ ；周期： $$ \sin,\cos $$ 为 $$ 2\pi $$ ， $$ \tan $$ 为 $$ \pi $$ 。
* 基本： $$ \sin^2x+\cos^2x=1 $$ ， $$ \tan x=\frac{\sin x}{\cos x} $$ 。
* 二倍角举例： $$ \sin2x=2\sin x\cos x $$ ， $$ \cos2x=\cos^2x-\sin^2x $$ 。
* 解三角：正弦定理 $$ \frac{a}{\sin A}=\frac{b}{\sin B}=\frac{c}{\sin C} $$ ；
  余弦定理： $$ c^2=a^2+b^2-2ab\cos C $$ 。

**易错点**：1. 度弧混用；2. 反三角函数值域忽视；3. 解三角丢失“第二解”（正弦定理的歧义）。

### 解析几何（平面）

* 直线：斜截式 $$ y=kx+b $$ ；两点式 $$ \frac{y-y_1}{x-x_1}=\frac{y_2-y_1}{x_2-x_1} $$ 。
* 距离：两点间 $$ d=\sqrt{(x_2-x_1)^2+(y_2-y_1)^2} $$ ；点到直线 $$ \frac{\|Ax_0+By_0+C\|}{\sqrt{A^2+B^2}} $$ 。
* 圆： $$ (x-a)^2+(y-b)^2=r^2 $$ 。

**易错点**：1. 斜率分母为0（垂直线）未单列；2. 距离公式坐标代错；3. 点到直线公式未先化为一般式。

### 平面/立体几何与测量

* 角与平行：同位角=内错角（判平行）；三角形内角和 $$ 180^\circ $$ 。
* 全等：SSS、SAS、ASA、AAS、RHS；相似：AA、SAS（比）、SSS（比）。
* 勾股： $$ a^2+b^2=c^2 $$ （直角三角形）；常见勾股数组：3-4-5，5-12-13，8-15-17。
* 面积：矩形 $$ ab $$ ；三角形 $$ \frac12 ab\sin C $$ 或 $$ \frac{1}{2}bh $$ ；梯形 $$ \frac{(a+b)h}{2} $$ ；圆 $$ \pi r^2 $$ ；扇形 $$ S=\frac12 r^2\theta $$ （ $$ \theta $$ 弧度）。
* 体积：圆柱 $$ \pi r^2h $$ ；圆锥 $$ \frac13\pi r^2h $$ ；球 $$ \frac43\pi r^3 $$ 。

**易错点**：1. 扇形角度未转弧度；2. 体积/表面积混用；3. 相似比→面积比平方→体积比立方忘记层次。

### 数列

* 等差：通项 $$ a_n=a_1+(n-1)d $$ ，和 $$ S_n=\frac{n(a_1+a_n)}{2}=\frac{n[2a_1+(n-1)d]}{2} $$ 。
* 等比：通项 $$ a_n=a_1q^{n-1} $$ ，和 $$ S_n=a_1\frac{1-q^n}{1-q}\,(q\neq1) $$ 。

**易错点**：1. 首项、公差/公比位置代反；2. “项数 $$ n $$ ”与“末项 $$ a_n $$ ”混淆。

### 计数原理与二项式

* 原理：互斥用加法；独立步骤用乘法。
* 排列： $$ P(n,k)=\frac{n!}{(n-k)!} $$ ；组合： $$ C(n,k)=\frac{n!}{k!(n-k)!} $$ 。
* 二项式： $$ (a+b)^n=\sum_{k=0}^{n}C(n,k)a^{n-k}b^k $$ ；第 $$ k+1 $$ 项为 $$ C(n,k)a^{n-k}b^k $$ 。

**易错点**：1. 排列/组合混淆（是否区分顺序）；2. 重复计数未剔重；3. “至少/至多”题未用补集法。

### 概率与统计

* 概率： $$ P=\frac{\text{有利}}{\text{等可能总数}} $$ ；互斥： $$ P(A\cup B)=P(A)+P(B) $$ ；独立： $$ P(AB)=P(A)P(B) $$ 。
* 条件概率： $$ P(A\|B)=\frac{P(AB)}{P(B)} $$ ；全概率与贝叶斯（入门识记）。
* 期望方差：离散型 $$ E(X)=\sum xp(x) $$ ， $$ \operatorname{Var}(X)=E(X^2. -[E(X)]^2 $$ 。
* 常见模型：二项分布 $$ P(X=k)=C(n,k)p^k(1-p)^{n-k} $$ ，均值 $$ np $$ ，方差 $$ np(1-p) $$ 。
* 描述统计：均值/中位数/众数；极差；直方图与频率。

**易错点**：1. 把互斥当独立；2. 条件概率分母错写 $$ P(A) $$ ；3. 期望直接取最大概率项而非 $$ \sum xp $$ 。

### 导数初步（函数性质与切线）

* 基本求导： $$ \frac{d}{dx}x^n=nx^{n-1} $$ ； $$ \frac{d}{dx}e^x=e^x $$ ； $$ \frac{d}{dx}a^x=a^x\ln a $$ ；
   $$ \frac{d}{dx}\ln x=\frac{1}{x} $$ ； $$ \frac{d}{dx}\sin x=\cos x $$ ； $$ \frac{d}{dx}\cos x=-\sin x $$ ； $$ \frac{d}{dx}\tan x=\sec^2 x $$ 。
* 法则：乘法 $$ (uv)'=u'v+uv' $$ ；商法 $$ (\frac{u}{v})'=\frac{u'v-uv'}{v^2} $$ 。
* 应用：单调区间（看 $$ f' $$ 正负）、极值（驻点与端点）、切线 $$ y=f'(x_0)(x-x_0)+f(x_0) $$ 。

**易错点**：1. 忘检查定义域（如 $$ \ln x $$ 、分母为0）；2. 只找驻点不判区间；3. 切线式子代错点或代错斜率。

### 单位与常量

* 角度： $$ 180^\circ=\pi $$ （rad）；速度： $$ v=\frac{s}{t} $$ ；密度： $$ \rho=\frac{m}{V} $$ 。
* 圆周率 $$ \pi\approx3.1416 $$ ；自然常数 $$ e\approx2.7183 $$ 。
  **易错点**：度↔弧度换算；百分比与小数互化位数。

### 证明与常见方法

* 直接法、反证法、数学归纳法（两步：基础步+归纳步）、构造法、分类讨论、数形结合。

**易错点**：1. 结论先行、前提缺失；2. 没交代“存在/唯一”条件；3. 画图未注明已知与求证。

## 二项式定理

英语：Binomial theorem

二项式的幂的代数展开。

根据二项式定理，可以将 x+y 的任意次幂展开为和的形式，即：

$$
(x+y)^{n}={n \choose 0}x^{n}y^{0}+{n \choose 1}x^{n-1}y^{1}+{n \choose 2}x^{n-2}y^{2}+\cdots +{n \choose n-1}x^{1}y^{n-1}+{n \choose n}x^{0}y^{n},
$$

其中每个 $$ {\tbinom nk} $$ 为一个称作二项式系数的特定正整数，其等于 $$ {\frac {n!}{k!(n-k)!}} $$ 。

使用求和符号，可写作：

$$
(x+y)^{n}=\sum _{k=0}^{n}{n \choose k}x^{n-k}y^{k}=\sum _{k=0}^{n}{n \choose k}x^{k}y^{n-k}
$$

后面的表达式只是将根据 x 与 y 的对称性得出的，通过比较发现公式中的二项式系数也是对称的。

### 数学归纳法证明

当 n=1，

$$
(a+b)^{1}=\sum _{k=0}^{1}{1 \choose k}a^{1-k}b^{k}={1 \choose 0}a^{1}b^{0}+{1 \choose 1}a^{0}b^{1}=a+b
$$

假设二项展开式在 n=m 时成立。若 n=m+1，

$$
{\displaystyle {\begin{aligned}(a+b)^{m+1}&=a(a+b)^{m}+b(a+b)^{m}
\\&=a\sum _{k=0}^{m}{m \choose k}a^{m-k}b^{k}+b\sum _{j=0}^{m}{m \choose j}a^{m-j}b^{j}
\\&=\sum _{k=0}^{m}{m \choose k}a^{m-k+1}b^{k}+\sum _{j=0}^{m}{m \choose j}a^{m-j}b^{j+1}\ \ \ \ \ {\text{( 將 }}a{\text{, }}b{\text{) }}
\\&=a^{m+1}+\sum _{k=1}^{m}{m \choose k}a^{m-k+1}b^{k}+\sum _{j=0}^{m}{m \choose j}a^{m-j}b^{j+1}\ \ \ \ \ {\text{ 取出 }}k=0{\text{ 的項 }}
\\&=a^{m+1}+\sum _{k=1}^{m}{m \choose k}a^{m-k+1}b^{k}+\sum _{k=1}^{m+1}{m \choose k-1}a^{m-k+1}b^{k}\ \ \ \ \ {\text{設 }}j=k-1\\&=a^{m+1}+\sum _{k=1}^{m}{m \choose k}a^{m-k+1}b^{k}+\sum _{k=1}^{m}{m \choose k-1}a^{m+1-k}b^{k}+b^{m+1}\ \ \ \ \ {\text{取出 }}k=m+1{\text{項 }}\\&=a^{m+1}+b^{m+1}+\sum _{k=1}^{m}\left[{m \choose k}+{m \choose k-1}\right]a^{m+1-k}b^{k}\ \ \ \ \ {\text{兩者加起 }}\\&=a^{m+1}+b^{m+1}+\sum _{k=1}^{m}{m+1 \choose k}a^{m+1-k}b^{k}\ \ \ \ \ {\text{套用帕斯卡法則 }}\\&=\sum _{k=0}^{m+1}{m+1 \choose k}a^{m+1-k}b^{k}\end{aligned}}}
$$

## 三角函数

### 正弦函数、余弦函数

**正弦函数**： $$ y = \sin x $$

符号：sin，英语：Sine

数学意义：对边与斜边之比；与余割函数互为倒数。

性质：最小正周期为 2π，函数图像于原点对称，奇函数，定义域(-∞,∞)，值域[-1,1]，不动点为 0

函数图像：
![](http://math001.com/wp-content/uploads/trigonometry/sin_arcsin.gif)
特定值：

- 当 x 取 $$ \frac {(4n+1)\pi }{2} $$ （n 为整数）时，函数有最大值 1；
- 当 x 取 $$ \frac {(4n+3)\pi }{2} $$ （n 为整数）时，函数有最小值 -1；
- 当 x 取 $$ k\pi $$ (k 为整数）时，函数为 0。
- 当 x 取 $$ \frac{\pi}{6} $$ 时，函数为 $$\frac{1}{2}$$ 。
- 当 x 取 $$ \frac{\pi}{4} $$ 时，函数为 $$\frac{\sqrt{2}}{2}$$ 。
- 当 x 取 $$ \frac{\pi}{6} $$ 时，函数为 $$\frac{\sqrt{3}}{2}$$ 。

**反正弦函数**： $$y = \arcsin x$$

符号： $$\arcsin、\sin ^{-1} $$ ，英文：Arcsine

数学意义：正弦值的反函数（正弦函数不是双射函数，无反函数）

性质：奇函数，定义域[-1, 1]，值域 $$\left[-\frac\pi 2, \frac\pi 2\right]$$ ，于原点对称，严格递增

反正弦函数与反余弦函数图像：
![](http://math001.com/wp-content/uploads/trigonometry/arcsinx_arccosx.gif)

**恒等式**

用其他三角函数表示：

$$
sin\theta
= \sqrt{1 - \cos^2\theta}
= \frac{\tan\theta}{\sqrt{1 + \tan^2\theta}}
= \frac{1}{\csc\theta}
= \frac{\sqrt{\sec^2\theta - 1}}{\sec\theta}
= \frac{1}{\sqrt{1 + \cot^2\theta}}
$$

两角和公式： $$\sin (x+y)=\sin x \cos y + \cos x \sin y $$

两角差公式： $$\sin (x-y)=\sin x \cos y - \cos x \sin y$$

二倍角公式： $$\sin 2\theta = \sin \theta \cos \theta $$

三倍角公式： $$\sin 3\theta = 3 \sin \theta- 4 \sin^3\theta$$

半角公式： $$\sin \frac{\theta}{2} = \pm\, \sqrt\frac{1 - \cos \theta}{2}$$

和化积公式： $$\sin \theta + \sin \phi = 2 \sin\left( \frac{\theta + \phi}{2} \right) \cos\left( \frac{\theta - \phi}{2} \right)$$

差化积公式： $$\sin \theta - \sin \phi = 2 \cos\left({\theta + \phi \over 2}\right) \sin\left({\theta - \phi\over 2}\right)$$

万能公式： $${\displaystyle \sin \alpha ={\frac {2\tan {\frac {\alpha }{2}}}{1+\tan ^{2}{\frac {\alpha }{2}}}}}$$

余弦函数： $$ y = \cos x $$

符号：cos，英语：Cosine

数学意义：邻边与斜边之比；与正割函数互为倒数。

性质：最小正周期为 2π，函数图像于 Y 轴对称，偶函数，定义域(-∞,∞)，值域[-1,1]，不动点为 0.7390851332152...

函数图像：
![](http://math001.com/wp-content/uploads/trigonometry/cos_arecos.gif)
特定值：

- 当 x 取 $$ 2n\pi $$ （n 为整数）时，函数有最大值 1；
- 当 x 取 $$ (2n+1)\pi $$ （n 为整数）时，函数有最小值 -1；
- 当 x 取 $$ k\pi + \frac{\pi}{2}$$ (k 为整数）时，函数为 0。
- 当 x 取 $$ \frac{\pi}{6} $$ 时，函数为 $$\frac{1}{\sqrt{3}}{2}$$ 。
- 当 x 取 $$ \frac{\pi}{4} $$ 时，函数为 $$\frac{\sqrt{2}}{2}$$ 。
- 当 x 取 $$ \frac{\pi}{6} $$ 时，函数为 $$\frac{1}{2}$$ 。

**反余弦函数**： $$y = \arccos x$$

符号： $$\arccos、\cos ^{-1} $$ ，英文：Arccosine

数学意义：余弦值的反函数（余弦函数不是双射函数，无反函数）

性质：奇函数，定义域[-1, 1]，值域 $$[0, \pi]$$ ，严格递减，对称于点 $$ (0,{\frac {\pi }{2}}) $$

**恒等式**

用其他三角函数表示：

$$
\cos\theta
= \sqrt{1 - \sin^2\theta}
= \frac{1}{\sqrt{1 + \tan^2\theta}}
= \frac{\sqrt{\csc^2\theta - 1}}{\csc\theta}
= \frac{1}{\sec\theta}
= \frac{\cot\theta}{\sqrt{1 + \cot^2\theta}}
$$

两角和公式： $$\cos (x + y)=\cos x \cos y - \sin x \sin y$$

两角差公式： $$\cos (x - y)=\cos x \cos y + \sin x \sin y$$

二倍角公式： $$ \cos(2\theta )=\cos ^{2}\theta -\sin ^{2}\theta =2\cos ^{2}\theta -1=1-2\sin ^{2}\theta $$

三倍角公式： $$\cos 3\theta = 4 \cos^3\theta - 3 \cos \theta$$

半角公式： $$\cos \frac{\theta}{2} = \pm\, \sqrt\frac{1 + \cos \theta}{2}$$

幂约减公式： $$ \cos^2\theta = \frac{1 + \cos 2\theta}{2}$$ $$\cos^3\theta = \frac{3 \cos\theta + \cos 3\theta}{4}$$

和化积公式： $$\cos \theta + \cos \phi = 2 \cos\left( \frac{\theta + \phi} {2} \right) \cos\left( \frac{\theta - \phi}{2} \right)$$

差化积公式： $$ \cos \theta - \cos \phi = -2\sin\left( {\theta + \phi \over 2}\right) \sin\left({\theta - \phi \over 2}\right)$$

万能公式： $$ \cos\alpha = \frac{1 - \tan^2 \frac{\alpha}{2}}{1 + \tan ^2 \frac{\alpha }{2}} $$

### 正切函数、余切函数

**正切函数**： $$ y = \tan x $$

符号：tan，英语：Tangent

数学意义：对边与邻边之比；与余切函数互为倒数。

性质：最小正周期为 π，函数图像于原点对称，奇函数，定义域 $$\{x\|x≠kπ+π/2, k∈Z\} $$ ，值域 (-∞,∞)，不动点为 0

函数图像：
![](http://math001.com/wp-content/uploads/trigonometry/tan_cot.gif)

特定值：

- 当 x 取 $$ k\pi$$ (k 为整数）时，函数为 0。
- 当 x 取 $$ \frac{\pi}{4} $$ 时，函数为 1。

**恒等式**

用其他三角函数表示：

$$
\tan\theta
= \frac{\sin\theta}{\sqrt{1 - \sin^2\theta}}
= \frac{\sqrt{1 - \cos^2\theta}}{\cos \theta}
= \frac{1}{\cot\theta}
= \sqrt{\sec^2\theta - 1}
= \frac{1}{\sqrt{\csc^2\theta - 1}}
$$

和差公式： $$\tan(\theta\pm\psi)=\frac{\tan\theta\pm\tan\psi}{1\mp\tan\theta\tan\psi}$$

二倍角公式： $$\begin{align}\tan 2\theta &= \frac{2 \tan \theta} {1 - \tan^2 \theta}\\
& = \frac{1}{1-\tan\theta}-\frac{1}{1+\tan\theta}\\
\end{align}$$

三倍角公式： $$\tan 3\theta ={\frac  {3\tan \theta -\tan ^{3}\theta }{1-3\tan ^{2}\theta }}$$

半角公式： $$\begin{align} \tan \frac{\theta}{2} &= \csc \theta - \cot \theta \\ &= \pm\, \sqrt{1 - \cos \theta \over 1 + \cos \theta} \\ &= \frac{\sin \theta}{1 + \cos \theta} \\ &= \frac{1-\cos \theta}{\sin \theta} \\ &= \frac{\cos \theta+\sin \theta-1}{\cos \theta-\sin \theta+1} \end{align}$$

**余切函数**

余切函数： $$ y = \cot x $$

符号：cot、ctg，英语：Cotangent

数学意义：邻边与对边之比；与正切函数互为倒数。

性质：最小正周期为 π，函数图像于原点对称，奇函数，定义域 $$\{x\\|x≠kπ, k∈Z\} $$ ，值域 (-∞,∞)，不动点为 0.8603335901348...

- 当 x 取 $$ k\pi + \frac{\pi}{2}$$ (k 为整数）时，函数为 0。
- 当 x 取 $$ \frac{\pi}{4} $$ 时，函数为 1。

**恒等式**

用其他三角函数表示：

$$
\cot\theta
= {\sqrt{1-\sin ^{2}\theta } \over \sin \theta}
= {\cos \theta  \over {\sqrt  {1-\cos ^{2}\theta }}}
= {1 \over \tan \theta }
= {1 \over {\sqrt  {\sec ^{2}\theta -1}}}
= {\sqrt  {\csc ^{2}\theta -1}}
$$

和差角公式： $$\cot(\theta \pm \psi )={\frac  {\cot \theta \cot \psi \mp 1}{\cot \psi \pm \cot \theta }}$$

半角公式： $${\begin{aligned}\cot {\frac  {\theta }{2}}&=\csc \theta +\cot \theta \\&=\pm \,{\sqrt  {1+\cos \theta  \over 1-\cos \theta }}\\&={\frac  {\sin \theta }{1-\cos \theta }}\\&={\frac  {1+\cos \theta }{\sin \theta }}\\&={\frac  {\cos \theta -\sin \theta +1}{\cos \theta +\sin \theta -1}}\end{aligned}}$$

二倍角公式： $${\displaystyle {\begin{aligned}\cot 2\theta &={\frac {\cot ^{2}\theta -1}{2\cot \theta }}\\&={\frac {1}{\cot \theta -1}}-{\frac {1}{\cot \theta +1}}\\\end{aligned}}}$$

三倍角公式： $$\cot 3\theta ={\frac  {\cot ^{3}\theta -3\cot \theta }{3\cot ^{2}\theta -1}}$$

### 正割函数、余割函数

在单位圆上，正割函数位于割线上，因此将此函数命名为正割函数。

**正割函数**： $$ y = \sec x $$

符号：sec，英语：secant

数学意义：斜边与邻边之比；与余弦函数互为倒数。

函数图像：![](http://math001.com/wp-content/uploads/trigonometry/secx.gif)

**余割函数**： $$ y = \csc x $$

符号：csc，英语：cosecant

数学意义：斜边与对边之比；与正弦函数互为倒数。

函数图像：![](http://math001.com/wp-content/uploads/trigonometry/cscx.gif)

### 正矢函数、余矢函数、半正矢函数、半余矢函数

**正矢函数**

符号：versin，英语：Versine、Versed sine

定义： $$versin\theta = 2\sin^2\left(\frac{\theta}{2}\right) = 1 - \cos \theta$$

**余矢函数**

符号：coversin、cvs，英语：Coversed sine、Coversine

定义： $$coversin\theta =versin\left({\frac{\pi }{2}}-\theta \right)=1-\sin \theta $$

**半正矢函数**

符号：haversin，英语：Haversed sine、Haversine

定义： $$haversin\theta ={\frac  {versin\theta }{2}}={\frac  {1-\cos \theta }{2}}$$

**半余矢函数**

符号：hacoversin，英语：Hacoversed sine、Hacoversine

定义： $$hacoversin\theta ={\frac  {coversin}\theta}{2}}={\frac  {1-\sin \theta }{2}}$$

## 正弦定理、余弦定理、正切定理、余切定理

**正弦定理**

对于任意 $$ \triangle ABC，a、b、c $$ 分别为 $$ \angle A、\angle B、\angle C $$ 的对边， $$ R $$ 为 $$ \triangle ABC $$ 的外接圆半径，则有： $$ {\frac {a}{\sin \angle A}}={\frac {b}{\sin \angle B}}={\frac {c}{\sin \angle C}}=2R$$

**余弦定理**

余弦定理（也叫做余弦公式）是勾股定理的扩展： $$c^2=a^2+b^2-2ab\cos C$$

也表示为： $$\cos C=\frac{a^2+b^2-c^2}{2ab}$$

余弦定律用于在一个三角形的两个边和一个角已知时确定第三边。

**正切定理**

在平面三角形中，任意两条边的和除以第一条边减第二条边的差所得的商等于这两条边的对角的和的一半的正切除以第一条边对角减第二条边对角的差的一半的正切所得的商。

即： $$ \frac{a-b}{a+b}=\frac{\mathrm{tan}\, \frac{\alpha -\beta }{2}}{\mathrm{tan}\, \frac{\alpha +\beta }{2}} $$

**余切定理**

某个角一半的余切等于半周长减去这个角所对的边长再除以三角形的内切圆半径。

假设 $$ \alpha ,\beta ,\gamma $$ 是三角形的三个内角，a, b, c 是与之对应的三个对边，若 $$ {\displaystyle \zeta ={\sqrt {\frac {1}{s}}(s-a)(s-b)(s-c)}} $$ （这个三角形的内切圆半径），其中： $${\displaystyle s={\frac {a+b+c}{2}}}$$ （s 就是三角形的半周长）。

那么，余切定理告诉我们： $$\cot{ \frac{\alpha}{2 }} = \frac{s-a}{\zeta }$$

以及： $${\displaystyle {\frac {\cot(\alpha /2)}{s-a}}={\frac {\cot(\beta /2)}{s-b}}={\frac {\cot(\gamma /2)}{s-c}}}$$
