---
title: 速查表 - 基础数学
categories: Basics
toc_level: 2
tags: Notes
---

## 基础数学范围


### 1. 数与运算（实数体系）

**要点**

* 数集链： $$  \mathbb N\subset\mathbb Z\subset\mathbb Q\subset\mathbb R\subset\mathbb C $$ 
* 近似与有效数字；科学记数法；绝对值与距离。

**常用公式**

* 交换/结合/分配： $$ a+b=b+a $$ ， $$ (a+b)+c=a+(b+c) $$ ， $$ a(b+c)=ab+ac $$ 。
* 绝对值： $$ \|a\|=\sqrt{a^2} $$ ， $$ \|ab\|=\|a\|\|b\| $$ ， $$ \|a+b\|\le\|a\|+\|b\| $$ 。
* 平方差： $$ a^2-b^2=(a-b)(a+b) $$ 。
* 科学记数： $$ a\times10^n $$ （ $$ 1\le a<10 $$ ）。
* 有理/有限/循环小数互化； $$ \sqrt{a}\sqrt{b}=\sqrt{ab} $$ （限  $$ a,b\ge0 $$ ）。

**易错**

*  $$ \sqrt{a+b}\ne \sqrt a+\sqrt b $$ ； $$ \|a+b\|=\|a\|+\|b\| $$ 仅当同号或其一为零。
* 有效数字与四舍五入位次混淆。


### 2. 因数与整除（初等数论入门）

**要点**

* 质合数；最大公因数gcd、最小公倍数lcm；欧几里得算法；同余。
* 质因数分解唯一性。

**常用公式**

*  $$ ab=\gcd(a,b)\cdot\mathrm{lcm}(a,b) $$ 。
* 整除判别： $$ 2,3,4,5,8,9,11 $$ 等规则。
* 裴蜀等式： $$ \gcd(a,b)=ax+by $$ 。
* 同余： $$ a\equiv b\pmod m \iff m\mid(a-b) $$ 。

**易错**

* 误把 $$ \gcd(a,b)=a $$ 当作“ $$ a\mid b $$ ”的充分条件。
* 同余加减乘可传递，除法需满足可逆条件（与 $$ m $$ 互素）。


### 3. 代数式与因式分解

**要点**

* 括号化简、幂指运算；常用恒等式；二项式定理。

**常用公式**

* 完全平方： $$ a^2\pm2ab+b^2=(a\pm b)^2 $$ 。
* 立方和差： $$ a^3\pm b^3=(a\pm b)(a^2\mp ab+b^2) $$ 。
* 多项式除法、余式定理： $$ P(a)= $$  以 $$ (x-a) $$ 除之余数。
* 二项式： $$ (x+y)^n=\sum_{k=0}^n\binom nk x^{n-k}y^k $$ 。

**易错**

*  $$ a^2+b^2 $$ 不可再因式分解于实数域。
* 展开与合并同类项的指数与系数对齐错误。


### 4. 方程与不等式

**要点**

* 一元、二元方程与方程组；一元二次判别式；根与系数。
* 绝对值与分式方程的整式化；不等式的区间解集。

**常用公式**

* 一元二次： $$ ax^2+bx+c=0\Rightarrow x=\frac{-b\pm\sqrt{b^2-4ac}}{2a} $$ 。
* 判别式： $$ \Delta=b^2-4ac $$ ；韦达： $$ x_1+x_2=-\frac ba $$ ， $$ x_1x_2=\frac ca $$ 。
* 线性方程组（消元、克拉默）： $$ \Delta\ne0 $$ 有唯一解。
* 基本不等式： $$ (x-a)(x-b) $$ 号定区间； $$ \|x-a\|<r\Rightarrow a-r<x<a+r $$ 。

**易错**

* 绝对值方程需“拆符号分段”；分式方程需排除使分母为零的根。
* 解不等式时乘以负数需“翻号”。


### 5. 函数与图像变换

**要点**

* 定义域、值域、单调、奇偶、周期；平移、伸缩、对称。
* 基本库：一次、二次、幂函数、指数、对数、根式、分式、绝对值。

**常用公式**

* 指数： $$ a^x a^y=a^{x+y} $$ ， $$ (a^x)^y=a^{xy} $$ 。
* 对数： $$ \log_a bc=\log_a b+\log_a c $$ ， $$ \log_a b=\frac{\log_c b}{\log_c a} $$ 。
* 变换： $$ y=f(x)\to y=f(x-h)+k $$ 平移； $$ y=af(bx) $$ 纵横伸缩。

**易错**

* 对数底与真数条件： $$ a>0,a\ne1; b>0 $$ 。
* 值域常需配方法或分段分析，勿机械代入。


### 6. 多项式与方程根性态

**要点**

* 因式定理；重根；综合除法；有理根判别。
* 根与系数对称关系的利用。

**常用公式**

*  $$ P(x)=(x-r)^mQ(x)\Rightarrow r $$ 为 $$ m $$ 重根且 $$ P^{(k)}(r)=0 $$ （ $$ k<m $$ ）。
* 有理根定理：若 $$ P\in\mathbb Z[x] $$ ，有理根形如 $$ \pm\frac{因数(c)}{因数(a)} $$ 。

**易错**

* 只测 $$ P(r)=0 $$ 忽略重根判定；有理根并非一定存在。


### 7. 数列与求和

**要点**

* 等差、等比；通项、前 $$ n $$ 项和；错位相减；递推与归纳。

**常用公式**

* 等差： $$ a_n=a_1+(n-1)d $$ ， $$ S_n=\frac n2(2a_1+(n-1)d)=\frac n2(a_1+a_n) $$ 。
* 等比： $$ a_n=a_1q^{n-1} $$ ， $$ S_n=a_1\frac{1-q^n}{1-q}\,(q\ne1) $$ 。
* 无限等比： $$ \|q\|<1\Rightarrow S_\infty=\frac{a_1}{1-q} $$ 。
* 求和技巧：错位相减，分组，裂项，配凑二项式系数。

**易错**

* 等比和式符号与首末项位置； $$ \|q\|<1 $$ 判定遗漏。


### 8. 平面几何

**要点**

* 全等与相似；平行线角；三角形性质；四边形；圆几何。
* 证明思路：角度、长度、面积与比；辅助线；相似放缩。

**常用公式**

* 三角形面积： $$ S=\frac12ab\sin C=\frac12ah_a $$ 。
* 正弦定理： $$ \frac a{\sin A}=\frac b{\sin B}=\frac c{\sin C}=2R $$ 。
* 余弦定理： $$ c^2=a^2+b^2-2ab\cos C $$ 。
* 圆周角/弧度：弧长  $$ l=R\theta $$ ，扇形面积  $$ S=\frac12R^2\theta $$ 。

**易错**

* 正弦定理的“钝角分支”；相似比与面积比、体积比的次方关系。
* 圆幂与切割定理使用条件忽略垂直性或共圆性。


### 9. 解析几何（坐标法）

**要点**

* 直线、圆；距离与夹角；点到直线距离；简单轨迹。
* 圆锥曲线入门（可选）：抛物线、椭圆、双曲线的标准式与焦点定义。

**常用公式**

* 直线：点斜式  $$ y-y_1=k(x-x_1) $$ ；两点式；一般式  $$ Ax+By+C=0 $$ 。
* 夹角： $$ \tan\theta=\frac{k_2-k_1}{1+k_1k_2} $$ ；距离  $$ d=\frac{\|Ax_0+By_0+C\|}{\sqrt{A^2+B^2}} $$ 。
* 圆： $$ (x-a)^2+(y-b)^2=R^2 $$ 。
* 抛： $$ y^2=2px $$ ；椭： $$ \frac{x^2}{a^2}+\frac{y^2}{b^2}=1 $$ ；双： $$ \frac{x^2}{a^2}-\frac{y^2}{b^2}=1 $$ 。

**易错**

* 直线一般式系数同乘常数等价；点到直线距离分子取绝对值。
* 圆锥曲线焦半径定义与离心率混淆。


### 10. 三角学

**要点**

* 弧度；单位圆定义；诱导公式；和差、倍半角；积化和与和化积；解三角形。

**常用公式**

* 基本： $$ \sin^2x+\cos^2x=1 $$ ， $$ 1+\tan^2x=\sec^2x $$ 。
* 和差： $$ \sin(\alpha\pm\beta)=\sin\alpha\cos\beta\pm\cos\alpha\sin\beta $$ 。
* 倍角： $$ \cos2x=\cos^2x-\sin^2x=1-2\sin^2x=2\cos^2x-1 $$ 。
* 半角： $$ \sin^2\frac x2=\frac{1-\cos x}{2} $$ ， $$ \cos^2\frac x2=\frac{1+\cos x}{2} $$ 。
* 积化和： $$ \sin A\sin B=\frac12[\cos(A-B)-\cos(A+B)] $$ 。
* 正弦、余弦定理（见几何）。

**易错**

* 诱导公式象限符号；反三角函数值域。
* 解三角形的“歧义情形”（SSA）。


### 11. 向量与复数

**要点**

* 向量加减、数乘、点积；投影与夹角；坐标表示。
* 复数代数/几何表示；共轭；模与辐角；乘除与棣莫弗。

**常用公式**

* 点积： $$ \mathbf a\cdot\mathbf b=\|a\|\|b\|\cos\theta=a_xb_x+a_yb_y(+a_zb_z) $$ 。
* 投影： $$ \mathrm{proj}_{\mathbf b}\mathbf a=\frac{\mathbf a\cdot\mathbf b}{\\|\mathbf b\\|^2}\mathbf b $$ 。
* 复数： $$ z=a+bi $$ ， $$ \|z\|=\sqrt{a^2+b^2} $$ ， $$ \overline{z}=a-bi $$ 。
* 极式： $$ z=r(\cos\theta+i\sin\theta) $$ ； $$ z^n=r^n(\cos n\theta+i\sin n\theta) $$ 。

**易错**

* 点积为零判垂直；平行需“比例相等且同向/反向”。
* 复数除法需乘共轭化实分母。


### 12. 立体几何与空间度量

**要点**

* 棱柱、棱锥、柱锥台、球；体积与表面积；空间角与距离。

**常用公式**

* 体积：

  * 棱柱/柱： $$ V=S_{\text{底}}h $$ ；棱锥/锥： $$ V=\frac13S_{\text{底}}h $$ 。
  * 台体： $$ V=\frac h3(S_1+S_2+\sqrt{S_1S_2}) $$ 。
  * 球： $$ V=\frac43\pi R^3 $$ ， $$ S=4\pi R^2 $$ 。
* 斜高与母线关系；勾股在空间的推广。

**易错**

* 侧面积与全面积混用；高与斜高混淆；相似比对应到表面积比 $$ k^2 $$ 、体积比 $$ k^3 $$ 。


### 13. 计数原理（组合数学）

**要点**

* 分类与分步：加法、乘法原理；排列、组合；二项系数恒等式；容斥；抽屉原理；错排。

**常用公式**

* 排列： $$ A_n^m=\frac{n!}{(n-m)!} $$ ；组合： $$ \binom nm=\frac{n!}{m!(n-m)!} $$ 。
* 恒等式： $$ \binom n0+\cdots+\binom nn=2^n $$ ； $$ \binom nk=\binom n{n-k} $$ 。
* 容斥： $$ \|A\cup B\|=\|A\|+\|B\|-\|A\cap B\| $$ 。
* 错排： $$ D_n=n!\sum_{k=0}^n\frac{(-1)^k}{k!} $$ 。

**易错**

* 是否区分顺序与是否可重复；限制条件下先“选位置”再“排元素”。


### 14. 概率

**要点**

* 古典概率；条件概率与独立性；全概率与贝叶斯；二项分布。

**常用公式**

*  $$ P(A)=\frac{\text{有利}}{\text{等可能总数}} $$ 。
* 条件： $$ P(A\|B)=\frac{P(A\cap B)}{P(B)} $$ ；独立： $$ P(A\cap B)=P(A)P(B) $$ 。
* 全概率： $$ P(A)=\sum_i P(A\|B_i)P(B_i) $$ （ $$ \{B_i\} $$ 为完备划分）。
* 贝叶斯： $$ P(B_j\|A)=\frac{P(A\|B_j)P(B_j)}{\sum_i P(A\|B_i)P(B_i)} $$ 。
* 二项： $$ X\sim\mathrm{Bin}(n,p)\Rightarrow P(X=k)=\binom nk p^k(1-p)^{n-k} $$ 。

**易错**

* 把互斥与独立混为一谈；条件概率分母应为 $$ P(B)>0 $$ 。
* 多步事件应用树状分解与全概率。


### 15. 统计

**要点**

* 集中趋势：均值、中位数、众数；离散程度：极差、方差、标准差、四分位差；箱线图。

**常用公式**

* 均值： $$ \bar x=\frac1n\sum x_i $$ 。
* 方差： $$ s^2=\frac1n\sum(x_i-\bar x)^2=\overline{x^2}-\bar x^{\,2} $$ ；标准差 $$ s=\sqrt{s^2} $$ 。
* 线性变换： $$ y=ax+b\Rightarrow \bar y=a\bar x+b,\ s_y=\|a\|s_x $$ 。

**易错**

* 把样本方差与总体方差分母搞错（有时用 $$ n-1 $$ 为无偏估计）。
* 极端值对均值敏感，对中位数不敏感。


### 16. 集合与逻辑

**要点**

* 集合运算：并、交、差、补；德摩根律；区间表示。
* 命题、逆否、充要；量词及其否定。

**常用公式**

* 德摩根： $$ \overline{A\cup B}=\overline A\cap\overline B $$ ， $$ \overline{A\cap B}=\overline A\cup\overline B $$ 。
* 逻辑： $$ p\Rightarrow q $$ 等价于 $$ \lnot q\Rightarrow \lnot p $$ （逆否等价）。
* 量词否定： $$ \lnot(\forall x\,P)\equiv\exists x\,\lnot P $$ ； $$ \lnot(\exists x\,P)\equiv\forall x\,\lnot P $$ 。

**易错**

* “必要/充分”方向；区间端点是否含取决于不等式“≤/≥”。


### 17. 不等式与估计

**要点**

* 估算、放缩、配方法；均值不等式链；柯西与三角不等式。

**常用公式**

* AM-GM： $$ \frac{a_1+\cdots+a_n}{n}\ge\sqrt[n]{a_1\cdots a_n} $$ （ $$ a_i\ge0 $$ ）。
* Cauchy-Schwarz： $$ (\sum a_ib_i)^2\le(\sum a_i^2)(\sum b_i^2) $$ 。
* 三角不等式： $$ \|x+y\|\le\|x\|+\|y\| $$ 。
* Jensen（可选，凹凸函数）： $$ f(\lambda x+(1-\lambda)y)\le \lambda f(x)+(1-\lambda)f(y) $$ （凹）。

**易错**

* 适用条件缺失（非负性、等号成立条件）；把局部最值当全局。


### 18. 初等微积分入门（选学）

**要点**

* 极限直观、连续；导数与几何意义；基本求导；单调、极值；原函数与定积分几何意义。

**常用公式**

* 基本极限： $$ \lim_{x\to0}\frac{\sin x}{x}=1 $$ ， $$ \lim_{x\to\infty}(1+\frac1x)^x=e $$ 。
* 求导： $$ (x^n)'=nx^{n-1} $$ ， $$ (e^x)'=e^x $$ ， $$ (\ln x)'=\frac1x $$ ， $$ (\sin x)'=\cos x $$ ， $$ (\cos x)'=-\sin x $$ 。
* 复合链式： $$ (f(g(x)))'=f'(g(x))g'(x) $$ 。
* 不定积分表（基础）： $$ \int x^n\,dx=\frac{x^{n+1}}{n+1}+C\,(n\ne-1) $$ ； $$ \int \frac{dx}{x}=\ln\|x\|+C $$ ； $$ \int e^x dx=e^x+C $$ ； $$ \int \sin x dx=-\cos x+C $$ ； $$ \int \cos x dx=\sin x+C $$ 。
* 定积分性质：面积；区间可加；牛顿-莱布尼茨： $$ \int_a^bf'(x)dx=f(b)-f(a) $$ 。

**易错**

* 定义域与可导性忽略；链式法则漏乘内导；定积分上下限顺序。


### 19. 常用技巧与策略

**要点与公式**

* 配方法： $$ x^2+bx=(x+\tfrac b2)^2-\tfrac{b^2}{4} $$ 。
* 待定系数、换元、参数化、数形结合、单调性与界估。
* 作图法：关键点、极值点、对称性、端行为。

**易错**

* 代换的可逆性与新定义域；图像结论与代数条件互证。


### 20. 常见常数与单位速查

*  $$ \pi\approx3.14159 $$ ， $$ e\approx2.71828 $$ ， $$ \sqrt2\approx1.4142 $$ ， $$ \sqrt3\approx1.732 $$ 。
* 角度-弧度： $$ 180^\circ=\pi $$ ；常用三角特值： $$ 0,30^\circ,45^\circ,60^\circ,90^\circ $$ 。


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
