###According to **ERRATA TO VOLUME 1 (AFTER 2010)**:

  - (Amendment):

    **Page 476** replacement for answer 4 (22 Dec 2013)

    - Before: **4.** $x-1\lt\lfloor{x}\rfloor≤x$; so $-x+1\gt-\lfloor{x}\rfloor≥-x$; hence the result.
    - Actual: **4.** By part (f), $x\le\lceil{x}\rceil\lt x+1$; hence $-x-1\lt\lceil{x}\rceil\le-x$; use part (e).

###Some of the most important errors of the digital edition I have fixed [*](#note1):<a id="title"></a>

The app01.html file was a mess, particulary with the images. Some of them incompletes or just incorrect. Let me know if you find one of my corrections wrong.

  - On id="page\_29":

    - Before: [...] is that $∑\_{R(j)}∣aj∣$ exists.]
    - Actual: [...] is that $∑\_{R(j)}|a\_{j}|$ exists.]

  - On id="page\_29":

    - Before: — that is, if $∑\_{R(i)} ∑\_{S(j)}∣aj∣$ exists —
    - Actual: — that is, if $∑\_{R(i)} ∑\_{S(j)}|a\_{ij}|$ exists —

  - Answer **5** of **Section 1.2.4**:

    - Before: &lt;em&gt;except&lt;/em&gt; when $1=\frac12$.
    - Actual: &lt;em&gt;except&lt;/em&gt; when $x\bmod1=\frac12$.

  - Answer **6** of **Section 1.2.4**:

    - Before: $\lfloor\sqrt{x}\rfloor=n⇔n^{2}≤x\lt(n+1)^{2}⇔n^{2}≤\lfloor{x}\rfloor\lt(n+1)^{2}⇔\lfloor\sqrt{x}\rfloor=n$
    - Actual: $\lfloor\sqrt{x}\rfloor=n⇔n^{2}≤x\lt(n+1)^{2}⇔n^{2}≤\lfloor{x}\rfloor\lt(n+1)^{2}⇔\left\lfloor\sqrt{\lfloor{x}\rfloor}\right\rfloor=n$

  - Answer **17** of **Section 1.2.7**:

    - Before: By exercise 4.6.2–6, we have ${p\brack k}\equiv\delta\_{kp}-\delta\_{k1}\text{ (modulo }p)$
    - Actual: By exercise 4.6.2–6, we have $x^{\overline p}\equiv x^{p}-x\text{ (modulo }p)$

  - Answer **21** of **Section 1.2.8**:

    - Before: [...] the solution is $(x^{n+1}F\_{n+1}+x^{n+2}F\_{n-x})/(x^{2}+x-1)$
    - Actual: [...] the solution is $(x^{n+1}F\_{n+1}+x^{n+2}F\_{n}-x)/(x^{2}+x-1)$

  - Answer **36** of **Section 1.2.8**:

    - Before: [...] if and only if $\lfloor(k+1)\phi^{-1}\rfloor=1$
    - Actual: [...] if and only if $\lfloor(k+1)\phi^{-1}\rfloor-\lfloor k\phi^{-1}\rfloor=1$

  - Answer **37** of **Section 1.2.8**:

    - Before: &lt;em&gt;Proof:&lt;/em&gt; Let $μ$
    - Actual: &lt;em&gt;Proof:&lt;/em&gt; Let $μ(m)=F\_j$;

  - Answer **6** of **Section 1.2.10**:

    - Before: $6\sqrt{2}/5\approx1.697$
    - Actual: $\ln(q+pe^{t})=\ln\left(1+pt+\frac{pt^{2}}{2}+\frac{pt^{3}}{6}+\cdots\right)=pt+p(1-p)\frac{t^{2}}{2}+p(1-p)(1-2p)\frac{t^{3}}{6}+\cdots$

  - Answer **22** of **Section 1.2.10**:

    - Before: [...] it is $1/2$.
    - Actual: [...] it is $\lt 1/2$.


<a id="note1"></a>[*](#title) The list does not include all errors found, only those in which I'm not entirely sure if the correction is correct.