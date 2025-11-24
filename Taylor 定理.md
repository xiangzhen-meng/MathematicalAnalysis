# Taylor 定理

## 概述

Taylor 定理给出了用多项式逼近函数的手段。

## 应用 1：逼近函数

### 例 1 需要记忆的几个常用逼近

**注意，以下全部都是在 $x=0$ 处展开的泰勒公式！！！**

首先有 $e^x$ 的展开式：
$$
e^x=1+x+\frac{1}{2}x^2+\frac{1}{3!}x^3+\dots+\frac{1}{n!}x^n+o(x^n)
$$
$\sin x$ 取偶数项，正负颠倒；$\cos x$ 取奇数项，正负颠倒

自然对数：
$$
\ln x=x-\frac{x^2}{2}+\frac{x^3}{3}+\dots+\frac{x^n}{n}+o(x^n)
$$
类似二项式定理的形式：
$$
(1+x)^\alpha=1+\alpha x+\frac{\alpha(\alpha-1)}{2}x^2+\frac{\alpha(\alpha-1)(\alpha-2)}{3!}x^3+\dots+C_\alpha^nx^n+o(x^n)
$$
系数其实就是广义的二项式系数

反正弦：
$$
\arcsin x=x+\frac{1}{6}x^3+\frac{3!!}{4!!\cdot 5}x^5+o(x^6)
$$
反余弦，利用反正弦减一下即可：
$$
\arccos x=\frac{\pi}{2}-\arcsin x
$$
正切与反正切：
$$
\tan x=x+\frac{1}{3}x^3+o(x^4)
$$
$$
\arctan x=x-\frac{1}{3}x^3+\frac{1}{5}x^5
-\frac{1}{7}x^7+\dots+\frac{(-1)^n}{2n+1}x^{2n+1}+o(x^{2n+1})$$
