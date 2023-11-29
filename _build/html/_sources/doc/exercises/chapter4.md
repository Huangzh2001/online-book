# 第四章作业

```{prf:example}
2.7：证明定理2.6.2.

（1）设$\{N(t),t\geq 0\}$是具有强度函数$\{\lambda(s)>0,s\geq 0\}$的非时齐泊松过程. 令$m(t)=\int_0^t\lambda(s)ds,m^{-1}(t)$是$m(t)$的反函数，即

$$
m^{-1}(u)=\inf \{t:t>0,m(t)\geq u,u\geq 0\},
$$

记$M(u)=N\{m^{-1}(u)\}$，则$\{M(u),u\geq 0\}$是时齐泊松过程.

（2）设$\{M(u),u\geq 0\}$是时齐泊松过程，参数$\lambda =1.$若给定强度函数$\{\lambda(s)>0,s\geq 0\}$，令$m(t)=\int_0^t\lambda(s)ds,N(t)=M\{m(t)\}$，则$\{N(t)\}$时非时齐的且具有强度函数$\{\lambda(s),s\geq 0\}$的泊松过程.
```

```{prf:proof}
（1）$M(0)=N\{m^{-1}(0)\}=0$

任取$0<t_1<t_2<\cdots <t_n$
因为$m(t)$是递增函数，所以有$$m^{-1}(t_1)<m^{-1}(t_2)<\cdots<m^{-1}(t_n)$$

所以有

$$
M(t_1)=N\{m^{-1}(t_1)\};M(t_i-t_{i-1})=N\{m^{-1}(t_i)-m^{-1}(t_{i-1})\},(i>1)
$$

由$N(t)$的独立增量性可得$M(t)$也具有独立增量性.$\forall s,t\geq 0,n\geq 0 $有：

$$
\begin{aligned}
P\{M(s+t)-M(t)=n\}&=P[N\{m^{-1}(s+t)\}-N\{m^{-1}(t)\}=n]\\
&=\frac{[m\{m^{-1}(s+t)\}-m\{m^{-1}(t)\}]^n}{n!}\exp\{-[m\{m^{-1}(s+t)\}-m\{m^{-1}(t)\}]\}\\
&=\frac{s^n}{n!}e^{-s}
\end{aligned}
$$

由定义2.1.2，$\{M(u)\}$满足参数为$1$的时齐泊松过程

（2）$N(0)=0$以及独立增量性易得
对任意的$t\geq 0$和充分小的$h>0$，有：

$$
\begin{aligned}
P\{N(t+h)-N(t)=1\}&=P[M\{m(t+h)\}-M\{m(t)\}=1]\\
&=\{m(t+h)-m(t)\}e^{-\lambda \{m(t+h)-m(t)\}}\\
&=\lambda(t)h+o(h)
\end{aligned}
$$

同理可得$$P\{N(t+h)-N(t)=n\}=o(h ), (n\geq 2)$$
```

---

```{prf:example}
2.8：证明定理2.6.1.
令$m(t)=\int_0^t\lambda(s)ds$，若$\{N(t),t\geq 0\}$是非时齐具有强度函数$\{\lambda(t),t\geq 0\}$的泊松过程，则$\forall s,t\geq 0,$有

$$
P\{N(s+t)-N(s)=n\}=\frac{[m(s+t)-m(s)]^n}{n!}\exp\{-[m(s+t)-m(s)]\} (n\geq 0)
$$
```

```{prf:proof}
记$P_n(t)=P\{N(t)=n\}$

往证

$$
P\{N(s+t)-N(s)=n\}=\frac{[m(s+t)-m(s)]^n}{n!}\exp\{-[m(s+t)-m(s)]\} (n\geq 0)
$$

即证

$$
P_{n}(t)=\frac{\{m(t)\}^n}{n!}e^{-m(t)}
$$ 

$n=0:$

$$
\begin{aligned}
    P_0(t+h) &= P\{ N(t+h)=0 \} = P\{ N(t+h)-N(t) =0,N(t)=0 \}\\
    &=  P\{N(t)=0 \}\cdot P\{ N(t+h)-N(t) =0\}\\
    &=P_0(t)\cdot\{1-\lambda(t) h-o(h)\}
\end{aligned}
$$

由$(1)$得： 

$$
\frac{P_0(t+h)-P_0(t)}{h} = -P_0(t)(\lambda(t)+o(1) )
$$

令 $h\to 0$,得：$$P'_0(t)=-\lambda(t) P_0(t)$$

由ODE知识并且$P_0(0)=P\{N(0)=0\}=1$，得：

$$
P_0(t)=e^{-\int_0^t\lambda(s)ds}=e^{-m(t)}
$$

n>0:

$$
\begin{aligned}
    P_n(t+h) &= P\{ N(t+h)=n \} \\
    &= P\{ N(t+h)-N(t) =0,N(t)=n \}+P\{ N(t+h)-N(t) =1,N(t)=n-1 \}+o(h)\\
    &=  P\{N(t)=n \}\cdot P\{ N(t+h)-N(t) =0\}+  P\{N(t)=n-1 \}\cdot P\{ N(t+h)-N(t) =1\} \\
    &=P_n(t)\cdot\{1-\lambda(t)-o(h)\}+P_{n-1}\cdot (\lambda(t) h+o(h))+o(h)
\end{aligned}
$$

由$(2)$变换并令$h\to 0$得：

$$
P'_n(t)=-\lambda(t) P_n(t)+\lambda(t) P_{n-1}(t) 
$$

经变换可得到：

$$
\frac{d}{dt}[e^{m(t)}P_n(t)]=\lambda(t) e^{m(t)}P_{n-1}(t)
$$

当$n=1$时

$$
\frac{d}{dt}[e^{m(t)}P_1(t)]=\lambda(t) 
$$

所以

$$
P_1(t)=m(t)e^{-m(t)}
$$

再由归纳法可得

$$
P_{n}(t)=\frac{\{m(t)\}^n}{n!}e^{-m(t)}
$$
```

---    
```{prf:example}
2.9:求在$N(t)=n$的条件下，$S_k(k<n)$的条件概率密度
```
```{prf:proof}
解：记$Y_1,Y_2,\cdots,Y_n$是$[0,t]$上独立同均匀分布的一组随机变量

$S_k$的条件p.d.f实际上就是$Y_{(k)}$的p.d.f

所以有：

$$
        \begin{aligned}
            f_k(y_k)&=\frac{n!}{(k-1)!(n-k)!}\{F(y_k)\}^{k-1}\{1-F(y_k)\}^{n-k}f(y_k)\\
                         &=\frac{n!}{(k-1)!(n-k)!}(\frac{y_k}{t})^{k-1}(1-\frac{y_k}{t})^{n-k}\frac 1t\cdot I_{(y_k\in [0,t])}
        \end{aligned}
$$

所以在给定$N(t)=n$的条件下$\frac{S_k}{t}$服从$Be(k,n-k+1)$分布.
```

---
```{prf:example}
2.23、2.24：设$n$个零件的寿命$X_1,X_2,\cdots ,X_n$是独立同指数分布，参数为$\lambda.$该$n$个零件从$t=0$开始工作，记$X_{(1)}\leq X_{(2)}\leq \cdots \leq X_{(n)}$为相继失效时刻，试求：

（1）$X_{(1)},X_{(2)},\cdots,X_{(r)} $的联合p.d.f$(1\leq r\leq n)$

（2）令$Y_1=X_{(1)},Y_i=X_{(i)}-X_{(i-1)},2\leq i\leq n.$，判断$Y_1,Y_2,\cdots ,Y_n$是否独立？是否同分布？并证明你的猜想.
```
```{prf:proof}
解：（1）$X_k$的p.d.f为：

$$
f(x_k)=\lambda e^{-\lambda x_k}\cdot I_{(x_k\geq 0)}
$$

$X_k$的分布函数为：

$$
F(x_k)=1-e^{-\lambda x_k}\cdot I_{(x_k\geq 0)}
$$

$(X_{(1)},X_{(2)},\cdots,X_{(r)})$的联合p.d.f为：

$$
\begin{aligned}
f(t_1,t_2,\cdots,t_r)&=\frac{n!}{(n-r)!}\{1-F(t_r)\}^{n-r}\prod\limits_{k=1}^rf(t_k)\\
&=\frac{n!}{(n-r)!}e^{-\lambda\{(n-r)t_r+\sum\limits_{i=1}^rt_i\}}\cdot I_{(0\leq t_1\leq t_2\cdots \leq t_r)}
\end{aligned}
$$

（2）$(X_{(1)},X_{(2)},\cdots,X_{(n)})$的联合p.d.f为：

$$
f(t_1,t_2,\cdots,t_n)=n!\cdot exp\{-\lambda \sum\limits_{i=1}^nt_i\}\cdot I_{(0\leq t_1\leq t_2\leq\cdots\leq t_n)}
$$

又jacobi行列式为

$$
J=\frac{\partial(Y_1,Y_2,\cdots,Y_n)}{\partial(X_1,X_2,\cdots,X_n)}=1
$$

所以$(n!Y_1,Y_2,\cdots,Y_n)$的联合p.d.f为：

$$
g(y_1,y_2,\cdots,y_n)=n!\cdot exp\{-\lambda\sum\limits_{i=1}^n i\cdot y_i\}\cdot I_{(y_i\geq 0,1\leq i\leq n)}
$$

计算$Y_k$的边际p.d.f：

$$
g_k(y_k)=(n-k+1)\lambda e^{-\lambda (n-k+1)y_k}\cdot I_{(0\leq y_k)}
$$

因为

$$
g(y_1,y_2,\cdots,y_n)=\prod\limits_{i=1}^ng_i(y_i)
$$

所以$(Y_1,Y_2,\cdots,Y_n)$独立但是不同分布.
```

---
```{prf:example}
2.25：设$\{N(t),t\geq 0\}$为时齐泊松过程，$S_1,S_2,\cdots,S_n$为到达时刻.

（1）给定$N(t)=n$条件下，试问$S_1,S_2-S_1,\cdots,S_n-S_{n-1}$是否条件独立？是否同分布？

（2）求$E\{S_1|N(t)\}$的分布律；

（3）利用（1）和（2），求$E\{S_k|N(t)\}$的分布律；

（4）求在$N(t)=n$下$S_i$与$S_k$的条件联合概率密度函数
```
```{prf:proof}
解：

（1）同分布但是不独立，理由如下：

因为$(S_1,S_2,\cdots,S_n)$在$\{N(t)=n\}$下的联合p.d.f为：

$$
f(t_1,t_2,\cdots,t_n)=\frac{n!}{t^n}I_{(0<t_1<t_2<\cdots<t_n\leq t)}
$$

所以$(X_1,X_2,\cdots,X_n)$在$\{N(t)=n\}$下的联合p.d.f为：

$$
g(x_1,x_2,\cdots,x_n)=\frac{n!}{t^n}I_{(0\leq x_1+x_2+\cdots +x_n\leq t)}
$$

由

$$
\iint_{\sum\limits_{k=1}^nx_k\leq t,x_k\geq 0}g(x_1,x_2,\cdots,x_n)dx_1dx_2\cdots dx_n=1
$$

得

$$
\iint_{\sum\limits_{k=1}^nx_k\leq t,x_k\geq 0}1dx_1dx_2\cdots dx_n=\frac{t^n}{n!}
$$

类比可得

$$
\iint_{\sum\limits_{k=1,k\neq i}^nx_k\leq t-x_i,x_k\geq 0}1dx_1dx_2\cdots dx_n=\frac{(t-x_i)^{n-1}}{(n-1)!}
$$

所以在$\{N(t)=n\}$的条件下$X_i$的边际p.d.f为：

$$
g_i(x_i)=\iint_{\sum\limits_{k=1,k\neq i}^nx_k\leq t-x_i,x_k\geq 0}g(x_1,x_2,\cdots,x_n)dx_1dx_2\cdots dx_n=\frac{n(t-x_i)^{n-1}}{t^n}I_{(0\leq x_i\leq t)}
$$

（2）由习题1.14可知：$n=0$时：

$$
\begin{aligned}
E\{X_1|N(t)=0\}&=\int_0^\infty P\{X_1>s|N(t)=0\}ds\\
&=\int_0\infty P\{N(s)=0|N(t)=0\}ds\\
&=\int_0^\infty e^{-\lambda(s-t)}ds\\
&=t+\frac 1\lambda
\end{aligned}
$$

$n\geq 1$时

$$
\begin{aligned}
E\{X_1|N(t)=n\}&=\int_0^\infty P\{X_1>s|N(t)=n\}ds\\
                &=\int_0^t \int_s^t \frac{n(t-x_1)^{n-1}}{t^n}dx_1ds\\
                &=\frac{t}{n+1}
\end{aligned}
$$

所以

$$
E\{S_1|N(t)\}=\frac{t}{N(t)+1}
$$

（3）由（1）得：$(X_1,X_2,\cdots,X_n)$，在$N(t)=n$下同分布.所以有：

$$
E\{S_k|N(t)\}=\sum\limits_{i=1}^kE\{X_i|N(t)\}=\frac{kt}{N(t)+1}
$$

（4）记$Y_1,Y_2,\cdots ,Y_n$为$[0,t]$上独立同均匀分布的随机变量.则有$S_i$在$N(t)=n$条件下，与$Y_{(i)}$同分布

所以在$N(t)=n$的条件下，$S_i$与$S_k$的联合p.d.f为：

$$
\begin{aligned}
g_{ik}(x_i,x_k)&=\frac{n!}{(i-1)!(k-i-1)!(n-k)!}\{F(x_i)\}^{i-1}\{F(x_k)-F(x_i)\}^{k-i-1}\{1-F(x_k)\}^{n-k}f(x_i)f(x_j)\\
                &=\frac{n!}{(i-1)!(k-i-1)!(n-k)!}(\frac{x_i}{t})^{i-1}(\frac{x_k-x_i}{t})^{k-i-1}(1-\frac{x_k}{t})^{n-k}\frac{1}{t^2}\cdot I_{(0\leq x_i<x_k\leq t)}
\end{aligned}
$$
```

---
```{prf:example}
2.26：设$\{N(t),t\geq 0\}$是参数为$\lambda$的时齐泊松过程，$S_0=0,S_n$为第$n$个事件发生的时刻.求：

（1）$(S_2,S_5)$的联合p.d.f；

（2）$E\{S_1|N(t)\geq 1\}$；

（3）$(S_1,S_2)$在$N(t)=1$下的条件p.d.f
```
```{prf:proof}
解：

（1）采用微元法：
令$0<t_2<t_5$取充分小的$h$使得$[t_2,t_2+h]$和$[t_5,t_5+h]$时间内均只有一个事件发生
所以有：

$$
\begin{aligned}
P\{t_2\leq S_2<t_2+h<t_5\leq S_5<t_5+h\}&=P\{N(t_2)=1,N(t_2+h)-N(t_2)=1,\\
& N(t_5)-N(t_2+h)=2,N(t_5+h)-N(t_5)=1\}\\
&=\lambda t_2e^{-\lambda t_2 }\lambda he^{-\lambda h}\frac{\{\lambda(t_5-t_2-h)\}^2}{2}e^{-\lambda(t_5-t_2-h)}\lambda he^{-\lambda h}\\
&=\frac{\lambda^5t_2(t_5-t_2-h)^2}{2}e^{-\lambda (t_5-h)}h^2
\end{aligned}
$$

所以$(S_2,S_5)$的联合p.d.f为：

$$
\begin{aligned}
g_{2,5}(t_2,t_5)&=\lim\limits_{h\to 0}P\{t_2\leq S_2<t_2+h<t_5\leq S_5<t_5+h\}/h^2\\
&=\frac{\lambda^5t_2(t_5-t_2)^2}{2}e^{-\lambda t_5}I_{(0<t_2<t_5)}
\end{aligned}
$$

（2）因为$S_1$服从指数分布,所以$E\{S_1\}=\frac 1\lambda$

由习题2.25得

$$
E\{S_1|N(t)=0\}=t+\frac 1\lambda
$$

由于

$$
E\{S_1\}=E\{S_1|N(t)=0\}P\{N(t)=0\}+E\{S_1|N(t)\geq 1\}P\{N(t)\geq 1\}
$$

所以

$$
E\{S_1|N(t)\geq 1\}=\frac 1\lambda -\frac{te^{-\lambda t}}{1-e^{-\lambda t}}
$$

PS:$E\{S_1\}\neq \sum\limits_{n=1}^\infty E\{S_1|N(t)=n\}$！！！

（3）采用微元法：

令$0<t_1<t_2$取充分小的$h$使得$0<t_1<t_1+h<t<t_2<t_2+h$

PS：因为$N(t)=1$，所以$t_2>t$是必须的

所以：

$$
\begin{aligned}
P\{t_1\leq S_1<t_1+h\leq t<t_2\leq S_2<t_2+h,N(t)=1\}&=P\{N(t_1)=0,N(t_1+h)-N(t_1)=1\\
& ,N(t)-N(t_1+h)=0,N(t_2)-N(t)=0\\
& ,N(t_2+h)-N(t_2)=1\}\\
&=e^{-\lambda t_1}\lambda he^{-\lambda h}e^{-\lambda(t-t_1-h)}e^{-\lambda(t_2-t)}\lambda h e^{-\lambda h}\\
&=\lambda^2h^2e^{-\lambda (t_2+h)}
\end{aligned}
$$

所以：

$$
\begin{aligned}
P\{t_1\leq S_1<t_1+h\leq t<t_2\leq S_2<t_2+h|N(t)=1\}&=\frac{P\{t_1\leq S_1<t_1+h\leq t<t_2\leq S_2<t_2+h,N(t)=1\}}{P\{N(t)=1\}}\\
&=\frac{\lambda^2h^2e^{-\lambda (t_2+h)}}{\lambda te^{-\lambda t}}
\end{aligned}
$$

于是，$(S_1,S_2)$在$N(t)=1$条件下的联合p.d.f为：

$$
\begin{aligned}
f_{\{(S_1,S_2)|N(t)=1\}}(t_1,t_2)&=\lim\limits_{h\to 0}P\{t_1\leq S_1<t_1+h\leq t<t_2\leq S_2<t_2+h|N(t)=1\}/h^2\\
&=\frac\lambda t e^{-\lambda(t_2-t)}\cdot I_{(0<t_1\leq t<t_2)}
\end{aligned}
$$
```
