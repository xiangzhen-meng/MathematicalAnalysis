# Q 分段折线函数对连续函数的逼近

### 问题描述与背景

给定一段定义在 $[0,1]$ 上的连续函数 $f$，首先选定有限的序列 $\{x_n\}$，使得：
$$
x_{0}=0,x_{n}=1,x_{k-1} < x_k <x_{k+1},\forall 1\leq k\leq n-1
$$
这也即将 $[0,1]$ 分成 $n$ 段

另外构造一系列新函数 $\varphi(x_{k},x)$ 如下：
$$
\varphi(x_{k},x)=\begin{cases}
\dfrac{1}{x_k-x_{k-1}}(x-x_{k-1}),&x\in[x_{k-1},x_k] \\
\dfrac{1}{x_k-x_{k+1}}(x-x_{k+1}),&x\in(x_k,x_{k+1}] \\
0,&\text{otherwize}
\end{cases},1\leq k\leq n-1
$$
可以证明的是，如果将这些段分的足够细的话，这一系列函数的叠加，能够足够好地逼近已知的函数 $f$ ，也即：
$$
\tilde{f}(x)=f(x_{1})\varphi(x_{1},x)+f(x_{2})\varphi(x_{2},x)+\dots+f(x_n)\varphi(x_n,x)
$$
使得：
$$
\forall\varepsilon>0,\exists\delta>0,s.t.\forall k,|x_k-x_{k+1}|<\delta ,|f(x)-\tilde{f}(x)|<\varepsilon
$$
这个问题事实上是一个重要的方法：有限元方法 (finite element method, FEM) 的基础

### 证明

构造函数 $G$，使得：
$$
G(x)=|\tilde{f}(x)-f(x)|,x\in[0,1]
$$
显然有：$G(x)$ 是闭区间上的连续函数。因此由最值定理：
$$
\exists \xi\in(0,1),s.t.G(\xi)=\max_{x\in[0,1]}G(x)
$$
并且，$\xi$ 是某个区间 $(x_k,x_{k+1})$ 的内点，因为在任意区间端点上函数取值为零

考察这一段区间：
$$
G(\xi)=\left|\frac{\xi-x_{k+1}}{x_k-x_{k+1}}f(x_k)+ \frac{\xi-x_{k}}{x_k-x_{k+1}}f(x_{k+1})-f(\xi)\right|
$$
对于 $f(x_k)$ 在 $x=\xi$ 处做带拉格朗日余项的泰勒展开，得到：
$$
f(x_k)=f(\xi)+f'(\eta_{1})(x_k-\xi),f(x_{k+1})=f(\xi)+f'(\eta_{2})(x_{k+1}-\xi)
$$
代入原式，得到：
$$
\begin{align}
RHS&=\left| tf'(\eta_{1})(x_k-\xi)+(1-t)f'(\eta_{2})(x_{k+1}-\xi) \right|
\end{align}
$$
取定：$M=\max |f'(x)|$ ，得到：
$$
RHS\leq M|x_k-x_{k+1}|
$$
则：
$$
\forall\varepsilon>0,\exists\delta=\frac{\varepsilon}{M},M=\max_{x\in[0,1]}|f'(x)|,s.t.|x_k-x_{k+1}|<\delta
$$
依如上取法，则有：
$$
G(x)\leq G(\xi)\leq M\delta<\varepsilon
$$
证毕
