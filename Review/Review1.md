## 1 Moment Generating Functions

#### Definition 2.3.1 

For each integer $n$, the $n^{th}$ moment of $X$ (or $F_X(x)$), $\mu_n^{'}$, is
$$
\mu_n^{'}=E[X^n].
$$
The $n$th central moment of $X$, $\mu_n$, is 
$$
\mu_n=E[(X-\mu)^n],
$$
where $\mu=\mu_1^{'}=E[X]$.

#### Definition 2.3.2 

The variance of a random variable $X$ is its second central moment, $Var[X]=E[(X-E[X])^2]$ . The positive square root of $Var[X]$ is the standard deviation of $X$.

#### Definition 2.3.6

Let $X$ be a random variable with cdf $F_X$. The moment generating function (mgf) of $X$ (or $F_X$), denoted by $M_X(t)$, is 
$$
M_X(t)=E[e^{tX}],
$$
provided that the expectation exists for $t$ in some neighborhood of $0$. That is, there is an $h>0$ such that, for all $t$ in $-h<t<h$, $E[e^{tX}]$ exists. If the expectation does not exist in a neighborhood of $0$, we say that the moment generating function does not exist.

If $X$ is continuous, then $M_X(t)=\int_{-\infty}^{\infty} e^{tx}f_X(x)dx$

If $X$ is discrete, then $M_X(t)=\sum_{x}e^{tx}P(X=x)$

#### Theorem 2.3.7 

If $X$ has mgf $M_X(t)$, then 
$$
E[X^n]=M_X^{(n)}(0),
$$
where we define
$$
M_X^{(n)}(0)=\frac{d^n}{dt^n}M_X(t)|_{t=0}.
$$
That is, the $n$th moment is equal to the $n$th derivative of $M_X(t)$ evaluated at $t=0$.



## 2 Transformation of Random Variables

If $(X,Y)$ is a continuous random vector with joint pdf $f_{X,Y}(x,y)$, then the joint pdf of $(U,V)$ can be expressed in terms of $f_{X,Y}(x,y)$ as:
$$
f_{U,V}(u,v)=f_{X,Y}(h_1(u,v), h_2(u,v))|J|,
$$
where $|J|$ is the absolute value of $J$. 
$$
J=|\begin{matrix}
\frac{\partial x}{\partial u} & \frac{\partial x}{\partial v}\\
\frac{\partial y}{\partial u} & \frac{\partial y}{\partial v}\\
\end{matrix}|
$$
Multiple Transformation:

![image-20221203201250903](https://github.com/Xianlyu/Application2023Fall/blob/master/Review/casella185.png)





## 3 Convergence Concepts

#### Definition 5.5.1 (convergence in probability)

A sequence of random variables, $X_1,X_2,...,$ converges in probability to a random variable $X$ if, for every $\epsilon > 0$,
$$
\lim_{n \rightarrow \infty} P(|X_n-X|\geq \epsilon)=0\quad or, equivalently, \lim_{n\rightarrow \infty} P(|X_n-X|<\epsilon)=1.
$$

#### Definition 5.5.6 (almost sure convergence)

A sequence of random variables, $X_1,X_2,...,$ converges almost surely to a random variable $X$ if, for every $\epsilon>0$, 
$$
P(\lim_{n\rightarrow \infty}|X_n-X|<\epsilon)=1
$$
Convergence almost surely implies convergence in probability. But the converse is flase.

#### Definition 5.5.10 (convergence in distribution)

A sequence of random variables, $X_1,X_2,...,$ converges in distribution to a random variable $X$ if
$$
\lim_{n\rightarrow \infty} F_{X_n}(x)=F_X(x)
$$
at all points $x$ where $F_X(x)$ is continuous.

#### Theorem 5.5.12 (convergence in probability implies convergence in distribution)

If the sequence of random variables, $X_1,X_2,...,$ converging in probability to a random variable $X$, the sequence also converges in distribution to $X$.

#### Theorem 5.5.13 (convergence in probability and convergence in distribution, sufficient and necessary conditions)

The sequence of random variables, $X_1,X_2,...,$ converges in probability to a constant $\mu$ if and only if the sequence also converges in distribution to $\mu$.



## 4 Law of Large Number

Difference between WLLN and SLLN is the convergence type. The existence of mean and variance are both needed.

#### Theorem 5.5.2 (Weak Law of Large Numbers)

Let $X_1,X_2,...$ be iid random variables with $E[X_i]=\mu$ and $Var[X_i]=\sigma^2<\infty$.

 Define $\bar{X}_n=\frac{1}{n}\sum_{i=1}^n X_i$. 

Then, for every $\epsilon$ > $0$,
$$
\lim_{n \rightarrow \infty} P(|\bar{X}_n-\mu|<\epsilon)=1
$$
that is, $\bar{X}_n$ converges in probability to $\mu$.

#### Theorem 5.5.9 (Strong Law of Large Numbers)

Let $X_1,X_2,...$ be iid random variables with $E[X_i]=\mu$ and $Var[X_i]=\sigma^2<\infty$, and define $\bar{X}_n=\frac{1}{n}\sum_{i=1}^n X_i$. Then, for every $\epsilon>0$,
$$
P(\lim_{n\rightarrow \infty}|\bar{X}_n-\mu|<\epsilon)=1;
$$
that is, $\bar{X}_n$ convergences almost surely to $\mu$.



## 5 Central Limit Theorem

*Condition of the general CLT: mgfs exist.*

#### Theorem 5.5.14 (Central Limit Theorem)

Let $X_1,X_2,...$ be a sequence of iid random variables whose **mgfs exist** in a neighborhood of $0$ (that is, $M_{X_i}(t)$ exists for $|t|<h$, for some positive $h$). Let $E[X_i]=\mu$ and $Var[X_i]=\sigma^2>0$. (Both $\mu$ and $\sigma^2$ are finite since the mgf exists.)  

Define $\bar{X}_n=\frac{1}{n}\sum_{i=1}^n X_i$. 

Let $G_n(x)$ denote the cdf of $\sqrt{n}(\bar{X}_n-\mu)/\sigma$. Then, for any $x$, $-\infty < x < \infty$, 
$$
\lim_{n\rightarrow \infty} G_n(x)=\int_{-\infty}^x \frac{1}{\sqrt{2\pi}}e^{-\frac{y^2}{2}}dy;
$$
that is, $\sqrt{n}(\bar{X}_n-\mu)/\sigma$ has a limiting standard normal distribution.

**Proof**:  *mgf+Taylor expansion+...*



#### Theorem 5.5.15 (Stronger form of the Central Limit Theorem)

*Condition: mean and variance exist, but the existence of mgf is not required. The proof uses characteristic function——there always exist characteristic functions.*

Let $X_1$, $X_2$,... be a sequence of iid random variables with $E[X_i]=\mu$ and  $0 < Var[X_i]=\sigma^2<\infty$. 

Define $\bar{X}_n=\frac{1}{n}\sum_{i=1}^n X_i$.

 Let $G_n(x)$ denote the cdf of $\sqrt{n}(\bar{x}_n-\mu)/\sigma$.

 Then, for any $x$, $-\infty < x< \infty$, 


$$
\lim_{n\rightarrow\infty} G_n(x)=\int_{-\infty}^x \frac{1}{\sqrt{2\pi}}e^{\frac{-y^2}{2}}dy;
$$


that is, $\sqrt{n}(\bar{X}_n-\mu)/\sigma$ has a limiting standard normal distribution.





## 6 Slutsky's Theorem

If $X_n \rightarrow X$ in distribution and $Y_n \rightarrow a$, $a$ is a constant, in probability, then 

a.  $Y_nX_n \rightarrow aX$ in distribution

b. $X_n+Y_n \rightarrow X+a$ in distribution





## 7 Delta Method

Casella Chapter 5 243-245

#### Theorem 5.5.24 (Delta Method)  

Let $Y_n$ be a sequence of random variables that satisfies $\sqrt{n}(Y_n-\theta)\rightarrow N(0,\sigma^2)$ in distribution. For a given function $g$ and a specific value of $\theta$, suppose that $g^{'}(\theta)$ exists and is not $0$. Then
$$
\sqrt{n}[g(Y_n)-g(\theta)]\rightarrow N(0,\sigma^2[g^{'}(\theta)]^2) \quad in \quad distribution.
$$
**Proof**: 

The Taylor expansion of $g(Y_n)$ around $Y_n=\theta$ is
$$
g(Y_n)=g(\theta)+g^{'}(\theta)(Y_n-\theta)+Remainder,
$$
Since $Y_n$ convergences to $\theta$  in distribution, by Theorem 5.5.13, $Y_n$ convergences to $\theta$ in probability, thus $Y_n-\theta$ convergences to $0$ in probability, and it follows that the remainder $\rightarrow 0$ in probability. 

By Theorem 5.5.12 (Convergence in probability implies convergence in distribution), we have $(Y_n-\theta)$ convergences in distribution to $0$ and  Remainder convergences to $0$ in probability. 

Then by Slustky's theorem, we have $\sqrt{n}(g(Y_n)-g(\theta))$ convergence to $\sqrt{n}g^{'}(\theta)(Y_n-\theta)$ in distribution.  



#### Theorem 5.5.26 (Second-order Delta Method)

Let $Y_n$ be a sequence of random variables that satisfies $\sqrt{n}(Y_n-\theta) \rightarrow N(0,\sigma^2)$ in distribution. For a given function $g$ and a specific value of $\theta$, suppose that $g^{'}(\theta)=0$ and $g^{''}(\theta)$ exists and is not 0. Then
$$
n[g(Y_n)-g(\theta)]\rightarrow \sigma^2\frac{g^{''}(\theta)}{2}\chi_1^2 \quad in \quad distribution.
$$

#### Theorem 5.5.28 (Multivariate Delta Method)

Let $X_1,...,X_n$ be a random sample with $E(X_{ij})=\mu_i$ and $Cov(X_{ik},X_{jk})=\sigma_{ij}$. For a given function $g$ with continuous **first partial derivatives** and a specific value of $\mu=(\mu_1,...,\mu_p)$ for which  $r^2=\sum\sum_{\sigma_{ij}}\frac{\partial g(\mu)}{\partial \mu_i}\frac{\partial g(\mu)}{\partial \mu_j}>0$,
$$
\sqrt{n}[g(\bar{X}_1,...,\bar{X}_s)-g(\mu_1,...,\mu_p)] \rightarrow N(0,\tau^2)\quad in \quad distribution.
$$
