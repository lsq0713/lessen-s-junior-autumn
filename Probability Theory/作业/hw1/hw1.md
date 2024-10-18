# 概率论与数理统计作业一

## 33 设$A_1, A_2,\cdots ,A_n$是随机事件，试用归纳法证明下列公式

$$
P(A_1\cup A_2\cup \cdots \cup A_n)\\
=\sum\limits^{n}_{i=1}P(A_i)-\sum\limits_{1\le i\le j\le n}P(A_iA_j)+\sum\limits_{1\le i\lt j\lt k\le n}P(A_i A_j A_k)-\cdots +(-1)^{n-1}P(A_1A_2\cdots A_n)
$$

已知$P(A_1) = \sum\limits_{i=1}^{1}P(A_i)$

假设成立：
$$
P(A_1\cup A_2\cup \cdots \cup A_n)\\
=\sum\limits^{n}_{i=1}P(A_i)-\sum\limits_{1\le i\le j\le n}P(A_iA_j)+\sum\limits_{1\le i\lt j\lt k\le n}P(A_i A_j A_k)-\cdots +(-1)^{n-1}P(A_1A_2\cdots A_n)
$$
则要证
$$
P(A_1\cup A_2\cup \cdots \cup A_n \cup A_{n+1})\\
=\sum\limits^{n+1}_{i=1}P(A_i)-\sum\limits_{1\le i\le j\le n+1}P(A_iA_j)+\sum\limits_{1\le i\lt j\lt k\le n+1}P(A_i A_j A_k)-\cdots +(-1)^{n}P(A_1A_2\cdots A_{n+1})
$$
不妨令事件$B=A_1\cup A_2\cup \cdots \cup A_n$，则$P(A_1\cup A_2\cup \cdots \cup A_n \cup A_{n+1})=P(B\cup A_{n+1})=P(B)+P(A_{n+1})-P(BA_{n+1})$

$P(BA_{n+1})=P((A_1\cup A_2\cup \cdots\cup A_n)\cap A_{n+1})=P((A_1\cap A_{n+1})\cup (A_2\cap A_{n+1})\cup \cdots \cup (A_n\cap A_{n+1}))$

令$C_i = A_iA_{n+1}$，则
$$
P(BA_{n+1})=P(C_1\cup C_2\cup \cdots \cup C_n)\\=\sum\limits^{n}_{i=1}P(A_iA_{n+1})-\sum\limits_{1\le i\le j\le n}P(A_iA_jA_{n+1})+\cdots +(-1)^{n-1}P(A_1A_2\cdots A_{n}A_{n+1})
$$
故
$$
P(B\cup A_{n+1})\\
=(\sum\limits^{n}_{i=1}P(A_i)+P(A_{n+1}))-(\sum\limits_{1\le i\le j\le n}P(A_iA_j)+\sum\limits^{n}_{i=1}P(A_iA_{n+1}))+\cdots +\\
(-1)^{n}P(A_1A_2\cdots A_nA_{n+1})\\
=\sum\limits^{n+1}_{i=1}P(A_i)-\sum\limits_{1\le i\le j\le n+1}P(A_iA_j)+\sum\limits_{1\le i\lt j\lt k\le n+1}P(A_i A_j A_k)-\cdots +(-1)^{n}P(A_1A_2\cdots A_{n+1})
$$
归纳假设成立，题设得证



## 39 用概率论想法求N阶行列式的展开式中包含主对角线元素的项数

展开式的样本空间即（1，2，...，n）与（1，2，...，n）上不同双射的数量，为$A_n^n=n!$

将各双射作为等可能事件处理

出现任一对角线元素$(i,i)$的概率是$\frac{1}{n}$，未出现$(i,i)$的概率是$\frac{n-1}{n}$

若未出现$(i,i)$而是出现$(i,j)$，则删去第i行与第j列以及第j行，下一个元素在主对角线上的概率为$\frac{1}{n-2}$

依次类推，若n为奇数，则有$\lfloor n/2\rfloor$次删除后，最后一个元素在主对角线上的概率为1，包含主对角线的项数为$n!*1=n!$

若n为偶数，则有$\lfloor n/2\rfloor$次删除后不存在主对角线元素，出现此情况概率为$\frac{1}{n*(n-2)*\cdots*2}$

包含主对角线元素的项数为$n!*(1-\frac{1}{n*(n-2)*\cdots*2})=n!-(n-1)*(n-3)*\cdots *1$

综上

N阶行列式包含主对角线的项数为
$$
\left\{
\begin{array}{rcl}
&n! & (n为奇数)\\
&n!-(n-1)*(n-3)*\cdots *1 & (n为偶数)
\end{array}
\right.
$$
