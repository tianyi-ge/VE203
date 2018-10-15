# VE203 mid2 18 SUMMER

### 20 Subsets of size k
#### 20.1 Definition 

1. Let $A$ be a finite set and $0\leq k \leq |A|$.
2. $\mathcal{P}_k(A)=\{x\in\mathcal{P}(A)||x|=k\}$

#### 20.2 Definition
1. $\binom{n}{k}=|\mathcal{P}_k([n])|,\quad 0\leq k\leq n$

#### 20.3 Pascal's Triangle
1. $0\leq k \leq n$, $\binom{n}{k}=\binom{n}{n-k}$
> $F(x)=[n]\backslash x$ is a bijection

2. $\binom{n+1}{k}=\binom{n}{k}+\binom{n}{k-1}$
> $A=\{x\cup\{n\}|x\in \mathcal{P}_{k-1}([n])\}$ and $B=\mathcal{P}_k([n])$
> $A\cap B=\emptyset$.
> $|A|=\binom{n}{k-1}$, $|B|=\binom{n}{k}$, $A\cup B=\mathcal{P}_k([n+1])$

### 21. Binomial Theorem
归纳法证明
[广义二项式定理](https://baike.baidu.com/item/%E4%BA%8C%E9%A1%B9%E5%BC%8F%E5%AE%9A%E7%90%86/7134359?fr=aladdin)
1. Corollary
> $(1+y)^n=\sum_{k=0}^n\binom{n}{k}y^k$
> $\sum_{k=0}^n\binom{n}{k}=2^n$

2. Theorem
> $|\mathcal{P}_n([2n])|=\sum_{k=0}^n \binom{n}{k}^2$ 左边一版挑k个，右边一半挑n-k个
> $(1+x)^n(1+x)^n=(1+x)^{2n}$, $$(\sum_{k=0}^n\binom{n}{k}x^k)^2=\sum_{k=0}^{2n}\binom{2n}{k}x^k$$
> For $x^n$, $$\sum_{k=0}^n\binom{n}{k}\binom{n}{n-k}=\sum_{k=0}^{2n}\binom{2n}{n}$$

3. Theorem
  $|\mathcal{P}([n])|=2^n$
> $$\mathcal{P}([n])=\bigcup_{k=0}^n\mathcal{P}_k([n])$$, $\mathcal{P}_i([n])\cap \mathcal{P}_j([n])=\emptyset$

### 22. Counting
#### 22.1 Example
$|[n]^k|=n^k$
#### 22.2 Theorem
$x_1+\cdots+x_n=r$, $$\binom{n+r-1}{r}$$ 隔板法
> $A=\{(x_1,\cdots,x_n)\in \mathbb{N}^n|x_1+\cdots+x_n=r\}$
> To see $|A|=|\mathcal{P}_r([n+r-1])|$, since $|\mathcal{P}_r([n+r-1])|=|\mathcal{P}_{n-1}([n+r-1])|$, it's sufficient to find a bijection between $A$ and $\mathcal{P}_{n-1}([n+r-1])$.
> Let $F:A\rightarrow \mathcal{P}_{n-1}([n+r-1])$, $$F(x_1,\cdots,x_n)=\{x_1,x_1+x_2+1,\cdots,n-2+\sum_{i=1}^{n-1}x_i\}$$, an element of $\mathcal{P}_{n-1}([n+r-1])$, hence injective
> surjective: 每个y都能解码成相对应的x
> 利用了递增的性质保证不重复

#### 22.3 Theorem
从n个物体中挑r个，顺序无所谓，可重复选择
$\binom{n+r-1}{r}$?
A: 有n个不同物体，$x_n$记录了n号物体被选中了多少次

####22.4 Theorem
$|\{f|f:[n]\rightarrow[n]\ is\ a\ bijection\}|=n!$
归纳法

### 23. Group
#### 23.1 Definition
$(G,\cdot)$, $\cdot$ is $G\times G\rightarrow G$ called group operation (the product)
1. Associativity $(x\cdot y)\cdot z=x\cdot(y\cdot z)$
2. Identity, $\forall x\in G$, $e\cdot x=x\cdot e=x$. There exists $y\in G$, $x\cdot y=y\cdot x=e$

> Lemma:
> $e$ ($e_G$) and $y$ ($x^{-1}$) are unique

#### 23.2 Abelian Group

1. For all $x,y\in G$, $x\cdot y=y\cdot x$.
2. $(\mathbb{Z},\cdot)$ is not a group. $0$ has no inverse. $0\cdot 1=0$.
3. $(\mathbb{Q}\backslash \{0\},\cdot)$ is an abelian group
4. $X=\{f:\mathbb{N}\rightarrow\mathbb{N}|f\ is\ a\ bijection\}$. Then $(X,\circ)$ is a group. Identity is $id_\mathbb{N}$. Inverse is $f^{-1}$
5. $X=\{f:\mathbb{R}\rightarrow\mathbb{R}|f\ is\ linear\ and\ not\  horizontal\}$. Then $(X,\circ)$ is a group but not abelian.
6. $X'=\{f\in X|f(0)=0\}$, then $(X',\circ)$ is abelian.
7. Lemma:
  Let $(G,\cdot)$ be a group. If $a,b,c\in G$ and $a\cdot b=a\cdot c$, then $b=c$
8. Corollary:
  If $a\cdot a=a$, then $a=e$
  If $x\cdot y=e$, then $y\cdot x=e$.
  Prrof:

> $yx=e$, then $xy=xye=x(ye)=x(ey)=x((yx)y)=(xy)(xy)$

9. abelian $\Leftrightarrow (ab)^n=a^nb^n$

#### 23.3 Symmetric Group

1. Definition $X=\{f:[n]\rightarrow[n]|f \ is\ a\ bijection\}$. $(X,\circ)$ is a symmetric group on n elements.
2. Cycle Notation
  $(k_1k_2\cdots k_m)$, $k_1\overset{f}{\rightarrow} k_2 \overset{f}{\rightarrow} \cdots k_m\overset{f}{\rightarrow} k_1$.

#### 23.4 Cycles

1. $(023)(13)\circ(12)(13)=(02)\neq(12)(13)\circ(023)(13)=(01)$
2. inverse是倒序， $(abcdef)^{-1}=(fedcba)$
3. Theorem
  Let $n\in \mathbb{N}\backslash\{0\}$ The group $S_n$ is not abelian iff $n\geq3.$
  Proof:
  $\Leftarrow:$ $n\geq3$, then $S_n(01)S_n(012)\neq S_n(012)S_n(01)$
  $\Rightarrow:$ Brute force

4. Disjoint 两个cycle没有相同元素
> $\alpha,\beta$ 是disjoint，则$\alpha\beta=\beta\alpha$.
> Q: 如果$H\subseteq S_n$，$H$里的元素可不可以两两disjoint？
> A: 只含有2-cycle和e的情况可以。否则$x^2$和$x$不是disjoint

5. Theorem
  Every element in $S_n$ can be written as a product of disjoint cycles.
> Proof:
>     1. 找一个$x_0$ s.t. $f(x_0)\neq x_0$， 一直算f直到$f^{m+1}(x_0)=x_0$
>   假设这个方法不成立，到中间就会出现最早的循环$f^p(x_0)=f^q(x_0)$， 那么$f^{p-1}(x_0)\neq f^{q-1}(x_0)$矛盾。两个不同的元素映射到了同一个元素，就不是bijection。
>
>     2. 然后再找下一个没出现过的，不是指向自己的元素继续

6. Theorem
  Let $n\geq2$, every element of $S_n$ can be written as the product of 2-cycles.
  $(k_1\cdots k_{m+1})=(k_1k_{m+1})(k_1\cdots k_m)$

7. Definition
  $\sigma$ is odd if it can be written as a product of an odd number of 2-cycles.

8. Theorem
  $\forall\sigma\in S_n$ is either odd or even. (assignment5)

#### 23.5 Order

1. Definition
  Define $x^n$, $x^0=e$, $x^{n+1}=x\cdot x^n$

2. Definition
  If the exists an $n\geq1$ s.t. $x^n=e$, then $x$ has finite order. Otherwise $x$ has infinite order.
  就像向量 可以用来运算的状态

3. Theorem
  If $(G,\cdot)$ is a finite group, then every element of $G$ has finite order
> $x^1$到$x^k$都不是e了
> $x^k$肯定有重复，否则可以构造出无穷个$x^k$，使得$G$变成infinite
> 有$x^{-1}$
> $x^n=x^k$，那么$x^{n-k}=e$，矛盾

4. Theorem
  $H\subseteq G$, if $e\in H \wedge \forall x,y\in H,x\cdot y^{-1}\in H$ then $(H,\cdot)$ is a subgroup of $(G,\cdot)$. $H\leq G$ or $(H,\cdot)\leq(G,\cdot)$. 

- 为啥是$x\cdot y^{-1}$？因为有了$y^{-1}$保证逆存在
- 和$\forall x\in H,x^{-1}\in H$有什么区别？同时保证了乘法在$H$上运算封闭
- $(H,\cdot)$ is a group.
- Q: 去掉H以后G还可能是group吗？
- A: e唯一，是对于所有G里的元素而言的，没有这个唯一的e，剩下的部分不可能是group

5. Definition
  If $G$ is finite, then the cardinality of $G$ is called order.

6. Example
  $A=\{T,F\}$,
  $X=\{f|f:\mathbb{N}\rightarrow A\}$
  $X$ is uncountable because there's a bijection between $X$ and $[0,1]$ (Cantor's Diagonal Proof)
  或者看作到$\mathcal{P}(\mathbb{N})$的surjection，T选，F不选

### 24. Dihedral Group

1. $\sigma$操作以后n-gon依然是n-gon，没有crossing和streching

2. 镜像或者旋转
3. Theorem
  $D_n$ has order $2n$ 镜子里n

### 25. Lagrange's Theorem
#### 25.1 Definition
$H\leq G$, $a\in G$.
left coset of H, $aH=\{a\cdot x|x\in H\}$
right coset of H, $aH=\{x\cdot a|x\in H\}$

#### 25.2 Theorem
$H\leq G$, then the order of $H$ divides the order of $G$.

> Proof:
> (1) $X=\{aH|a\in G\}$ is the set of partition of G
> (2) $|aH=H|$
> (1)(2) $\Rightarrow$ $|G|=|X||H|$

1. $q\in aH\cap bH$,
2. $q=ah_1=bh_2$, 
3. $b^{-1}ah_1=h_2\in H$,
4. $b^{-1}a=h_2h_1^{-1}\in H$,
5. $a=b(b^{-1}a)\in bH$
6. $x\in aH$, $x=ah'=b(b^{-1}a)h', x\in bH$
7. $aH\subseteq bH$
8. Dual proof, $aH=bH$

9. 2: bijection
> Q: 每个|$G$|的因数都有对应的子群吗
> A: 不一定。$A_4$ has order 12, 但不存在$H$ with order 6。只有2和3的disjoint是even的。

### 26. The Division Algorithm
#### 26.1 Definition
$x\ |\ y\Leftrightarrow \exists (k\in\mathbb{Z})(kx=y)$
#### 26.2 Theorem
(Division Algorithm)
$$a=q\cdot b+r,\ 0\leq r<b$$
$(b\in\mathbb{N}\backslash\{0\})$
1. $q$ is quotient, $r$ is remainder
2. Uniqueness: $0\leq(q-\tilde{q})<1$
3. Existence: 存在最小“余数”，且小于b.
> $(\mathbb{Z},|)$ is no longer a partial order

### 27. Generated subgroups
#### 27.1 Defintion
$\left<A\right>_G$ is the $\subseteq$-least $H\leq G$.

#### 27.2 Properties

- $\left<A\right>_G$ is a recursively defined set.
- Omit $_G$

### 28. Cyclic Group
#### 28.1 Definition
$C_n=\left<a\right>$, $a$ with order n

#### 28.2 Lemma
$$\left<a\right>=\{a^m\ |\ m\in \mathbb{Z}\}$$

#### 28.3 Lemma
$C_n$ is abelian.

#### 28.4 Lemma
$|C_n|=|\left<a\right>|=n$

#### 28.5 Lemma
m-cycle has order m in $S_n$

#### 28.6 Theorem
$C_k\leq S_n$

#### 28.7 Theorem
The order of $x$ divides the order of $G$.

#### 28.8 Theorem
p is a prime, if $(G,\cdot)$ has order $p$, then $(G,\cdot)$ is $C_p$

#### 28.9 Theorem
$g\in G$ has order $n=mk$, then $g^m$ has order $k$.

> If $0<q<k$ s.t. $(g^m)^q=e,mq<n$

#### 28.10 Theorem
If $(G,\cdot)$ is a finite group with order n, then for all $g\in G$, $g^ n = e$.

#### 28.11 Theorem 

- [ ] If $(G,\cdot)$ is a group of order 6, then there exists $g\in G$ with order 2.
- [x] 挑一个p构成cyclic group，在剩余的集合里挑一个q构成cyclic group，在$G\backslash(\left<p\right>\cup\left< q\right>)$里挑一个g，$\left<g\right>$的元素有至少4种，不为3

- Q: 每个|$G$|的因数都有对应的子群吗
- A: 不一定。$A_4$ has order 12, 但不存在$H$ with order 6。只有2和3的disjoint是even的。
- Q: n=mk，有了m-order的子群，一定有k-order的子群吗
- A: 不一定。上面例子
- Q: $A_4$有6-order的子群吗
- A: 没有。见[画图的网站](https://hobbes.la.asu.edu/groups/groups.html)和[UCI的notes](https://www.math.uci.edu/~ndonalds/math120a/a4.pdf)

### 29. Isomorphisms and Homomorphisims
#### 29.1 Definition
$f:G\rightarrow K$ is a group homomorphisim if
$$f(a\cdot b)=f(a)\star f(b)$$

#### 29.2 Definition
$f:G\rightarrow K$ is a group isomorphisim if $f$ is a bijection and
$$f(a\cdot b)=f(a)\star f(b)$$

$(G,\cdot)\cong(K,\star)$

#### 29.3 Theorem
$g,h\in G$ both have order $n$, then $\left<g\right>\cong\left<h\right>$.

#### 29.4 Theorem
$(\mathbb{Z},+)$, for $n\in \mathbb{N}\backslash \{0\}$, $$n\mathbb{Z}=\{m\in \mathbb{Z}\ |\ (\exists k\in\mathbb{Z})(m=nk)\}$$, then $n\mathbb{Z}\leq \mathbb{Z}$ and $n\mathbb{Z}\cong\mathbb{Z}$.
子群也可以同构isomorphic
[Cayley's Theorem](https://en.wikipedia.org/wiki/Cayley%27s_theorem)

#### 29.5 Example
$a\in G$ has order $n$, then $\left<a\right>\cong C_n$

### 30 Congruency
#### 30.1 Definition
$\mathbb{Z}/ n\mathbb{Z}=\{[a]_n\ |\ a\in\mathbb{Z}\}$ 所有小于n的同余类的集合
$a\equiv b(\mod)n$ iff $n\ |\ a-b$

$\oplus_n:$ $$[a]_n\oplus_n[b]_n=[a+b]_n$$
$\otimes_n:$ $$[a]_n\otimes_n[b]_n=[ab]_n$$

#### 30.2 Theorem
$\oplus_n$ is well defined.
> Proof: n|a-c and n|b-d, then n|(a+b)-(c+d)

#### 30.3 Theorem
$\otimes_n$ is well defined.
> Proof: n|a-c and n|b-d, ab-cd=ab-cb+cb-cd=b(a-c)+c(b-d)=n(bk+cl).
> then n|(ab-cd)

#### 30.3 Lemma
if $n\in\mathbb{N}\backslash\{0\}$, then $(\mathbb{Z}/ n\mathbb{Z},\oplus_n)$ is a group
Tabular representation of a finite group $(G,\cdot)$ is called a Cayley Table

#### 30.4 Lemma
$(\mathbb{Z}/ n\mathbb{Z},\oplus_n)$ is abelian with order $n$. Moreover, $(\mathbb{Z}/ n\mathbb{Z},\oplus_n)=C_n$

> Proof: $(\mathbb{Z}/ n\mathbb{Z},\oplus_n)=\left<[1]_n\right>$

#### 30.5 Lemma

1. $(\mathbb{Z}/ n\mathbb{Z},\otimes_n)$ is not a group;
2. $(\mathbb{Z}/ n\mathbb{Z}\backslash\{[0]_n\},\otimes_n)$ is not a group if n is not prime. 如果不是质数的话，肯定有因数$k$，它的倍数不可能mod后余1
3. $[1]_n$ is identity. $kx\equiv 1(\mod n)$

#### 30.6 Definition
$(\mathbb{Z}/ n\mathbb{Z})^*=\{[k]_n\in \mathbb{Z}/n\mathbb{Z}\ |\ (\exists x\in \mathbb{Z})(kx\equiv 1(\mod n))\}$

#### 30.7 Theorem
$((\mathbb{Z}/ n\mathbb{Z})^*,\otimes_n)$ is a group.

> Proof: First $\otimes_n$ is a function.
> $kx\equiv 1(\mod n)$ and $my\equiv 1(\mod n)$
> $kx-1=np$ and $my-1=nq$
> $kmxy-1=n(npq+p+q)$

1. Example
  $((\mathbb{Z}/ 6\mathbb{Z})^*,\otimes_6)\cong ((\mathbb{Z}/ 3\mathbb{Z})^*,\otimes_3)$
  猜想：6和3的关系：互质的k一样多（$\varphi(6)=\varphi(3)$）

#### 30.8 Lemma
if $\exists d\leq m$ such that $d|m$ and $d|n$, then $[m]_n\notin(\mathbb{Z}/ n\mathbb{Z})^*$ 必须要互质

> Proof: $n|mx-1$, $dk|dlx-1$, $dky=dlx-1$, $d(ky-lx)=1$