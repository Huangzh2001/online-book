随机过程的基本概念

这一节介绍的是随机过程的基本概念

# 什么是随机过程?

下面测试一下公式好不好用

测试一下行内公式:$\int_{-\infty}^{\infty}e^{-x^2}dx=\sqrt{\pi}$.再测试一下行间公式:

$$
\int_{-\infty}^{\infty}e^{-x^2}dx=\sqrt{\pi}
$$

下面测试一下表格好不好用

| 1   | 2   | 3   |
| --- | --- | --- |
| 我   | 是   | 谁   |

# 随机过程的分类

下面是插图的测试,下面是一张星空的图片:

![星空](image/sky.jpg)

我们测试一下各种漂亮的代码块

```{note}
这是一个笔记.
```

```{warning}
这是一个警告!
```

然后我们测试一下定理和命题,引理,证明

定理

```{prf:theorem}
:label: my-theorem
Given $y \in \mathbb R^n$ and linear subspace $S \subset \mathbb R^n$,
there exists a unique solution to the minimization problem
```{math}
\hat y := \argmin_{z \in S} \|y - z\|
```

The minimizer $\hat y$ is the unique vector in $\mathbb R^n$ that satisfies

* $\hat y \in S$

* $y - \hat y \perp S$
  The vector $\hat y$ is called the **orthogonal projection** of $y$ onto $S$.
  
  ```
  
  ```

证明

```{prf:proof}
We'll omit the full proof.
But we will prove sufficiency of the asserted conditions.
To this end, let $y \in \mathbb R^n$ and let $S$ be a linear subspace of $\mathbb R^n$.
Let $\hat y$ be a vector in $\mathbb R^n$ such that $\hat y \in S$ and $y - \hat y \perp S$.
Let $z$ be any other point in $S$ and use the fact that $S$ is a linear subspace to deduce

Hence $\| y - z \| \geq \| y - \hat y \|$, which completes the proof.
```

公理

```{prf:axiom}
:label: my-axiom
Every Cauchy sequence on the real line is convergent.
```

引理

```{prf:lemma}
:label: my-lemma
If $\hat P$ is the fixed point of the map $\mathcal B \circ \mathcal D$ and $\hat F$ is the robust policy as given in [(7)](https://python-advanced.quantecon.org/robustness.html#equation-rb-oc-ih), then

$$
\begin{cases}
x=1\\
y=2
\end{cases}
$$
```

定义

```{prf:definition}
:label: my-definition
The *economical expansion problem* (EEP) for
$(A,B)$ is to find a semi-positive $n$-vector $p>0$
and a number $\beta\in\mathbb{R}$, such that
$$
&\min_{\beta} \hspace{2mm} \beta \\
&\text{s.t. }\hspace{2mm}Bp \leq \beta Ap
$$
```

第二个引理
```{prf:lemma}
:label: my-lemma
If $\hat P$ is the fixed point of the map $\mathcal B \circ \mathcal D$ and $\hat F$ is the robust policy as given in [(7)](https://python-advanced.quantecon.org/robustness.html#equation-rb-oc-ih), then

$$
\begin{cases}
x=1\\
y=2
\end{cases}
$$
```
