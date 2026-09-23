Math induction is a way to prove some pattern that holds for all $n$. 
There are two types of induction - weak and strong
#### Weak induction
Weak induction consist of
1. Some statement $P(n)$ for $n$ in domain $D$ by some condition that we want to prove.
2. **Induction hypothesis**: claim (assumption) that $P(n)$ holds true for any integer $k=n$ 
3. **Base case** (basis step) $P(n_0)$, where $n_0$ is the smallest value of $n$ in domain $D$ of $n$ we want to prove
4. **Induction step**: proval that statement holds for $P(n)$ where $n=k+1$ applying **induction hypothesis**
First, we have to prove $P(n_0)$ by any technique we want, then we have to prove that it holds for $P(k+1)$ assuming that $P(k)$ that is true again by any technique we want. Both, base case and induction step must be proved. The <u>important part</u> is that we can prove induction with **any tenchique we want**, some proves require clever tricks.

Example 1: prove $\sum_{j=1}^{n}j = \dfrac{n(n+1)}{2}$ for $n \in \mathbb{N}$
1. Statement $P(n)$ that $\sum_{j=1}^{n}j = \dfrac{n(n+1)}{2}$ for $n \in \mathbb{N}$
2. Induction hypothesis - assume that $P(k)$ is true for $k>=1$, e.g $\sum_{j=1}^{n}j = \dfrac{k(k+1)}{2}$
3. Base case proval $P(n_0) = P(1) = \dfrac{1*(1+1)}{2} = 1$ which is true, because $\sum_{j=1}^{1}j = 1$
4. Induction step proval
   $\sum_{j=1}^{n}j + k+1 = P(k+1)$
   $\dfrac{k(k+1)}{2} + k + 1= \dfrac{(k+1)*((k+1)+1)}{2}$
   $\dfrac{k^2+k + 2k + 2}{2}= \dfrac{k^2+3k+2}{2}$
   $\dfrac{k^2+3k+ 2}{2}= \dfrac{k^2+3k+2}{2}$
   Both sides are equal, which means that statement is true

Example 2: prove $2^n > n+4$ for $n\geq 3,n \in \mathbb{N}$
1. Statement $P(n)$ that  $2^n > n+4$ for $n\geq 3,n \in \mathbb{N}$
2. Induction hypothesis that $P(k)$ is true for $k>=3$, $2^k > k+4$
3. Base case proval $P(n_0) = P(3) = 2^3 > 3+4$,  $8>7$, which confirms statement for base case
4. Induction step proval
   * $2^{k+1} > (k+1) + 4$
   * $2^{k+1} = 2*2^{k}$ and we know that $2^k>k+4$, so multiplying the other side by 2 we get $2*2^k> 2(k+4)$, thus $2^{k+1}>2k + 8$
   * Since $2k > k+1$ and $8 > 4$, then statement is true
#### Strong induction
Strong induction is similar to weak induction but
1. We prove statement $P(n)$ that will be hold for some $n >= a$, where $a$ is some minimal value that $n$ will have.
2. Base case is some range of $P(a)$ to $P(b)$ of proves, not just $P(a)$. We have to decide what values are needed to prove any case
3. Induction hypothesis consists of assumption that $P(i)$ is true for $a \le i \le k$, e.g it applied all levels below $k$ including $k$, such as $P(k-1)$ and etc

Example having $a_1 = 1, a_2=3$, prove that $a_n = a_{n-2} + 2a_{n-1}$ is always odd
1. Statement $a_n = a_{n-2} + 2a_{n-1}$ is always odd
2. Since $a_1$ and $a_2$ are required to prove any $a_n$, then $a_1$ and $a_2$ are base cases. Both numbers are odd, base cases are true
3. Induction step
  * $a_{k+1} = a_{k-1} + 2a_k$ since by induction hypothesis are levels below and including $k$ by hypothesis are odd, then $a_{n-1}$ is odd and $2a_n$ are also odd
  * we can write both in odd form $2p+1$
  * $a_{k+1} = 2r + 1 + 2(2q+1) = 2(r+2q+1) + 1$, since it's odd form $2p+1$ where $p = r+2q+1$, are hypothesis is true



