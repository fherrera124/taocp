---
title: |
    Section 2.4 - The Art of Computer Programming: Volume 1 / Fundamental
    Algorithms, Third Edition
...

<div class="heading">

#### Section 2.3.1 {#app01lev2sec23}

**<span
id="ch02ex_2_7_1a">[1](../Text/ch02a.html#ch02ex_2_7_1)</span>.**
${\tt INFO(T)}=A$, ${\tt INFO(RLINK(T))}=C$, etc.; the answer is *H*.

</div>

**<span
id="ch02ex_2_7_2a">[2](../Text/ch02a.html#ch02ex_2_7_2)</span>.**
Preorder: 1245367; symmetric order: 4251637; postorder: 4526731.

**<span
id="ch02ex_2_7_3a">[3](../Text/ch02a.html#ch02ex_2_7_3)</span>.** The
statement is true; notice, for example, that nodes 4, 5, 6, 7 always
appear in this order in [exercise 2](../Text/app01b.html#ch02ex_2_7_2a).
The result is immediately proved by induction on the size of the binary
tree.

**<span
id="ch02ex_2_7_4a">[4](../Text/ch02a.html#ch02ex_2_7_4)</span>.** It is
the reverse of postorder. (This is easily proved by induction.)

**<span
id="ch02ex_2_7_5a">[5](../Text/ch02a.html#ch02ex_2_7_5)</span>.** In the
tree of [exercise 2](../Text/app01b.html#ch02ex_2_7_2a), for example,
preorder is 1, 10, 100, 101, 11, 110, 111, using binary notation (which
is in this case equivalent to the Dewey system). The strings of digits
have been sorted, like words in a dictionary.

In general, the nodes will be listed in preorder if they are sorted
lexicographically from left to right, with ${\rm “blank”}\lt0\lt1$. The
nodes will be listed in postorder if they are sorted lexicographically
with $0\lt1\lt\rm “blank”$. For inorder, use $0\lt\rm “blank”\lt1$.

(Moreover, if we imagine the blanks at the left and treat the Dewey
labels as ordinary binary numbers, we get *level order*; see
[2.3.3](../Text/ch02a.html#ch02lev2sec9)–([8](../Text/ch02a.html#ch02eq-lev2sec9-8)).)

**<span
id="ch02ex_2_7_6a">[6](../Text/ch02a.html#ch02ex_2_7_6)</span>.** The
fact that $p_1p_2\ldots p_n$ is obtainable with a stack is readily
proved by induction on *n*, or in fact we may observe that [Algorithm
T](../Text/ch02a.html#ch02alg-lev2sec7-T) does precisely what is
required in its stack actions. (The corresponding sequence of S’s and
X’s, as in [exercise 2.2.1–3](../Text/ch02.html#ch02ex_2_1_3), is the
same as the sequence of 1s and 2s as subscripts in double order; see
[exercise 18](../Text/ch02a.html#ch02ex_2_7_18).)

Conversely, if $p_1p_2\ldots p_n$ is obtainable with a stack and if
$p_k=1$, then $p_1\ldots p_{k-1}$ is a permutation of $\{2,\ldots,k\}$
and $p_{k+1}\ldots p_n$ is a permutation of $\{k+1,\ldots,n\}$; these
are the permutations corresponding to the left and right subtrees, and
both are obtainable with a stack. The proof now proceeds by induction.

**<span
id="ch02ex_2_7_7a">[7](../Text/ch02a.html#ch02ex_2_7_7)</span>.** From
the preorder, the root is known; then from the inorder, we know the left
subtree and the right subtree; and in fact we know the preorder and
inorder of the nodes in the latter subtrees. Hence the tree is readily
constructed (and indeed it is quite amusing to construct a simple
algorithm that links the tree together in the normal fashion, starting
with the nodes linked together in preorder in $\tt LLINK$ and in inorder
in $\tt RLINK$). Similarly, postorder and inorder together characterize
the structure. But preorder and postorder do not; there are two binary
trees having $AB$ as preorder and $BA$ as postorder. If all nonterminal
nodes of a binary tree have *both* branches nonempty, its structure *is*
characterized by preorder and postorder.

**<span
id="ch02ex_2_7_8a">[8](../Text/ch02a.html#ch02ex_2_7_8)</span>.** (a)
Binary trees with all $\tt LLINK\rm s$ null. (b) Binary trees with zero
or one nodes. (c) Binary trees with all $\tt RLINK\rm s$ null.

**<span
id="ch02ex_2_7_9a">[9](../Text/ch02a.html#ch02ex_2_7_9)</span>.**
$\tt T1$ once, ${\tt T2}\;2n\!+\!1$ times, ${\tt T3}\;n$ times,
${\tt T4}\;n\!+\!1$ times, ${\tt T5}\;n$ times. These counts can be
derived by induction or by Kirchhoff’s law, or by examining [Program
T](../Text/ch02a.html#ch02a_pro_t).

**<span
id="ch02ex_2_7_10a">[10](../Text/ch02a.html#ch02ex_2_7_10)</span>.** A
binary tree with all $\tt RLINK\rm s$ null will cause all *n* node
addresses to be put in the stack before any are removed.

**<span
id="ch02ex_2_7_11a">[11](../Text/ch02a.html#ch02ex_2_7_11)</span>.** Let
$a_{nk}$ be the number of binary trees with *n* nodes for which the
stack in [Algorithm T](../Text/ch02a.html#ch02alg-lev2sec7-T) never
contains more than *k* items. If $g_k(z)=\sum_na_{nk}z^n$, we find
$g_1(z)=1/(1-z)$,
$g_2(z)=1/(1-z/(1-z))=(1-z)/(1-2z),\ldots,g_k(z)=1/(1-zg_{k-1}(z))=q_{k-1}(z)/q_k(z)$
where $q_{-1}(z)=q_0(z)=1,q_{k+1}(z)=q_k(z)-zq_{k-1}(z)$; hence
$g_k(z)=(f_1(z)^{k+1}-f_2(z)^{k+1})/(f_1(z)^{k+2}-f_2(z)^{k+2})$ where
$f_j(z)=\frac12{\left(1\pm\sqrt{1-4z}\right)}$. It can now be shown that
$a_{nk}=[u^n](1-u)(1+u)^{2n}(1-u^{k+1})/(1-u^{k+2})$; hence
$s_n=\sum_{k\ge1}k(a_{nk}-a_{n(k-1)})$ is
$[u^{n+1}](1-u)^2(1+u)^{2n}\sum_{j\ge1}u^j/(1-u^j)$, minus $a_{nn}$. The
technique of exercise 5.2.2–52 now yields the asymptotic series

<div class="image">

$$s_n/a_{nn}=\sqrt{\pi n}-\frac32-\frac{13}{24}\sqrt{\frac{\pi}{n}}+\frac{1}{2n}+O\left(n^{-3/2}\right)$$

</div>

[N. G. de Bruijn, D. E. Knuth, and S. O. Rice, in *Graph Theory and
Computing*, ed. by R. C. Read (New York: Academic Press, 1972), 15–22.]

When the binary tree represents a forest as described in [Section
2.3.2](../Text/ch02a.html#ch02lev2sec8), the quantity analyzed here is
the *height* of that forest (the furthest distance between a node and a
root, plus one). Generalizations to many other varieties of trees have
been obtained by Flajolet and Odlyzko [*j. Computer and System Sci.*
**25** (1982), 171–213]; the asymptotic distribution of heights, both
near the mean and far away, was subsequently analyzed by Flajolet, Gao,
Odlyzko, and Richmond [*Combinatorics, Probability, and Computing* **2**
(1993), 145–156].

**<span
id="ch02ex_2_7_12a">[12](../Text/ch02a.html#ch02ex_2_7_12)</span>.**
Visit $\tt NODE(P)$ between steps T2 and T3, instead of in step T5. For
the proof, demonstrate the validity of the statement “*Starting at step
T2 with $\ldots$ original value*
${\tt A[}1{\tt]}\ldots{\tt A[}m{\tt]}$,” essentially as in the text.

**<span
id="ch02ex_2_7_13a">[13](../Text/ch02a.html#ch02ex_2_7_13)</span>.**
(Solution by S. Araújo, 1976.) Let steps T1 through T4 be unchanged,
except that a new variable $\tt Q$ is initialized to *Λ* in step T1';
$\tt Q$ will point to the last node visited, if any. Step T5 becomes two
steps:

**T5'.** [Right branch done?] If ${\tt RLINK(P)}=\varLambda$ or
$\tt RLINK(P)=Q$, go on to T6; otherwise set $\tt A\Leftarrow P$,
$\tt P\gets RLINK(P)$ and return to T2'.

**T6'.** [Visit $\tt P$.] Visit $\tt NODE(P)$, set $\tt Q\gets P$, and
return to T4'.

A similar proof applies. (Steps T4' and T5' can be streamlined so that
nodes are not taken off the stack and immediately reinserted.)

**<span
id="ch02ex_2_7_14a">[14](../Text/ch02a.html#ch02ex_2_7_14)</span>.** By
induction, there are always exactly $n+1\varLambda$ links (counting
$\tt T$ when it is null). There are *n* nonnull links, counting $\tt T$,
so the remark in the text about the majority of null links is justified.

**<span
id="ch02ex_2_7_15a">[15](../Text/ch02a.html#ch02ex_2_7_15)</span>.**
There is a thread $\tt LLINK$ or $\tt RLINK$ pointing to a node if and
only if it has a nonempty right or left subtree, respectively. (See
[Fig. 24](../Text/ch02a.html#ch02fig24).)

**<span
id="ch02ex_2_7_16a">[16](../Text/ch02a.html#ch02ex_2_7_16)</span>.** If
${\tt LTAG(Q)}=0$, ${\tt Q}*$ is $\tt LLINK(Q)$; thus ${\tt Q}*$ is one
step down and to the left. Otherwise ${\tt Q}*$ is obtained by going
upwards in the tree (if necessary) repeatedly until the first time it is
possible to go down to the right without retracing steps; typical
examples are the trips from $\tt P$ to ${\tt P}*$ and from $\tt Q$ to
${\tt Q}*$ in the following tree:

<div class="image">

![Image](../Images/565fig01.gif)

</div>

**<span
id="ch02ex_2_7_17a">[17](../Text/ch02a.html#ch02ex_2_7_17)</span>.** If
${\tt LTAG(P)}=0$, set $\tt Q\gets LLINK(P)$ and terminate. Otherwise
set $\tt Q\gets P$, then set $\tt Q\gets RLINK(Q)$ zero or more times
until finding ${\tt RTAG(Q)}=0$; finally set $\tt Q\gets RLINK(Q)$ once
more.

**<span
id="ch02ex_2_7_18a">[18](../Text/ch02a.html#ch02ex_2_7_18)</span>.**
Modify [Algorithm T](../Text/ch02a.html#ch02alg-lev2sec7-T) by inserting
a step T2.5, “Visit $\tt NODE(P)$ the first time”; in step T5, we are
visiting $\tt NODE(P)$ the second time.

Given a threaded tree the traversal is extremely simple:

$({\tt P},1)^\varDelta=({\tt LLINK(P)},1)$ if ${\tt LTAG(P)}=0$,
otherwise $({\tt P},2)$;

$({\tt P},2)^\varDelta=({\tt RLINK(P)},1)$ if ${\tt RTAG(P)}=0$,
otherwise $({\tt RLINK(P)},2)$.

In each case, we move at most one step in the tree; in practice,
therefore, double order and the values of *d* and *e* are embedded in a
program and not explicitly mentioned.

Suppressing all the first visits gives us precisely [Algorithms
T](../Text/ch02a.html#ch02alg-lev2sec7-T) and
[S](../Text/ch02a.html#ch02alg-lev2sec6-S); suppressing all the second
visits gives us the solutions to [exercises
12](../Text/ch02a.html#ch02ex_2_7_12) and
[17](../Text/ch02a.html#ch02ex_2_7_17).

**<span
id="ch02ex_2_7_19a">[19](../Text/ch02a.html#ch02ex_2_7_19)</span>.** The
basic idea is to start by finding the parent $\tt Q$ of $\tt P$. Then if
$\tt P\neq LLINK(Q)$ we have ${\tt P\sharp}=\tt Q$; otherwise we can
find $\tt P\sharp$ by repeatedly setting $\tt Q\gets Q\$$ zero or more
times until ${\tt RTAG(Q)}=1$. (See, for example, $\tt P$ and
$\tt P\sharp$ in the tree shown.)

<div class="image">

![Image](../Images/566fig01.gif)

</div>

There is no efficient algorithm to find the parent of $\tt P$ in a
general right-threaded tree, since a degenerate right-threaded tree in
which all left links are null is essentially a circular list in which
the links go the wrong way. Therefore we cannot traverse a
right-threaded tree in postorder with the same efficiency as the stack
method of [exercise 13](../Text/ch02a.html#ch02ex_2_7_13), if we keep no
history of how we have reached the current node $\tt P$.

But if the tree is threaded in both directions, we *can* find
$\tt P\rm\unicode{39}s$ parent efficiently:

**F1.** Set $\tt Q\gets P$ and $\tt R\gets P$.

**F2.** If ${\tt LTAG(Q)}={\tt RTAG(R)}=0$, set $\tt Q\gets LLINK(Q)$
and $\tt R\gets RLINK(R)$ and repeat this step. Otherwise go to F4 if
${\tt RTAG(R)}=1$.

**F3.** Set $\tt Q\gets LLINK(Q)$, and terminate if $\tt P=RLINK(Q)$.
Otherwise set $\tt R\gets RLINK(R)$ zero or more times until
${\tt RTAG(R)}=1$, then set $\tt Q\gets RLINK(R)$ and terminate.

**F4.** Set $\tt R\gets RLINK(R)$, and terminate with $\tt Q\gets R$ if
$\tt P=LLINK(R)$. Otherwise set $\tt Q\gets LLINK(Q)$ zero or more times
until ${\tt LTAG(Q)}=1$, then set $\tt Q\gets LLINK(Q)$ and terminate.
<span class="middle">![Image](../Images/box.gif)</span>

The average running time of [Algorithm
F](../Text/ch02a.html#ch02alg-lev2sec9-F) is $O(1)$ when $\tt P$ is a
random node of the tree. For if we count only the steps
$\tt Q\gets LLINK(Q)$ when $\tt P$ is a right child, or only the steps
$\tt R\gets RLINK(R)$ when $\tt P$ is a left child, each link is
traversed for exactly one node $\tt P$.

**<span
id="ch02ex_2_7_20a">[20](../Text/ch02a.html#ch02ex_2_7_20)</span>.**

<div class="image">

![Image](../Images/567pro01.gif)

</div>

If two more lines of code are added at line 06

<div class="image">

![Image](../Images/567pro02.gif)

</div>

with appropriate changes in lines 10 and 11, the running time goes down
from $(30n+a+4)u$ to $(27a+6n-22)u$. (This same device would reduce the
running time of [Program T](../Text/ch02a.html#ch02a_pro_t) to
$(12a+6n-7)u$, which is a slight improvement, if we set $a=(n+1)/2.)$

**<span
id="ch02ex_2_7_21a">[21](../Text/ch02a.html#ch02ex_2_7_21)</span>.** The
following solution by Joseph M. Morris [*Inf. Proc. Letters* **9**
(1979), 197–200] traverses also in preorder (see [exercise
18](../Text/ch02a.html#ch02ex_2_7_18)).

**U1.** [Initialize.] Set $\tt P\gets T$ and ${\tt R}\gets\varLambda$.

**U2.** [Done?] If ${\tt P}=\varLambda$, the algorithm terminates.

**U3.** [Look left.] Set $\tt Q\gets LLINK(P)$. If ${\tt Q}=\varLambda$,
visit $\tt NODE(P)$ in preorder and go to U6.

**U4.** [Search for thread.] Set $\tt Q\gets RLINK(Q)$ zero or more
times until either $\tt Q=R$ or ${\tt RLINK(Q)}=\varLambda$.

**U5.** [Insert or remove thread.] If $\tt Q\neq R$, set
$\tt RLINK(Q)\gets P$ and go to U8. Otherwise set
${\tt RLINK(Q)}\gets\varLambda$ (it had been changed temporarily to
$\tt P$, but we’ve now traversed $\tt P\rm\unicode{39}s$ left subtree).

**U6.** [Inorder visit.] Visit $\tt NODE(P)$ in inorder.

**U7.** [Go to right or up.] Set $\tt R\gets P$, $\tt P\gets RLINK(P)$,
and return to U2.

**U8.** [Preorder visit.] Visit $\tt NODE(P)$ in preorder.

**U9.** [Go to left.] Set $\tt P\gets LLINK(P)$ and return to step U3.
<span class="middle">![Image](../Images/box.gif)</span>

Morris also suggested a slightly more complicated way to traverse in
postorder.

A completely different solution was found by J. M. Robson [*Inf. Proc.
Letters* **2** (1973), 12–14]. Let’s say that a node is “full” if its
$\tt LLINK$ and $\tt RLINK$ are nonnull, “empty” if its $\tt LLINK$ and
$\tt RLINK$ are both empty. Robson found a way to maintain a stack of
pointers to the full nodes whose right subtrees are being visited, using
the link fields in empty nodes!

Yet another way to avoid an auxiliary stack was discovered independently
by G. Lindstrom and B. Dwyer, *Inf. Proc. Letters* **2** (1973), 47–51,
143–145. Their algorithm traverses in *triple order*—it visits every
node exactly three times, once in each of preorder, inorder, and
postorder—but it does not know which of the three is currently being
done.

**W1.** [Initialize.] Set $\tt P\gets T$ and $\tt Q\gets S$, where
$\tt S$ is a sentinel value — any number that is known to be different
from any link in the tree (e.g., $-1$).

**W2.** [Bypass null.] If ${\tt P}=\varLambda$, set $\tt P\gets Q$ and
${\tt Q}\gets\varLambda$.

**W3.** [Done?] If $\tt P=S$, terminate the algorithm. (We will have
$\tt Q=T$ at termination.)

**W4.** [Visit.] Visit $\tt NODE(P)$.

**W5.** [Rotate.] Set $\tt R\gets LLINK(P)$,
$\tt LLINK(P)\gets RLINK(P)$, $\tt RLINK(P)\gets Q$, $\tt Q\gets P$,
$\tt P\gets R$, and return to W2. <span
class="middle">![Image](../Images/box.gif)</span>

Correctness follows from the fact that if we start at W2 with $\tt P$
pointing to the root of a binary tree $\tt T$ and $\tt Q$ pointing to
$\tt X$, where $\tt X$ is not a link in that tree, the algorithm will
traverse the tree in triple order and reach step W3 with $\tt P=X$ and
$\tt Q=T$.

If $\alpha({\tt T})=x_1x_2\ldots x_{3n}$ is the resulting sequence of
nodes in triple order, we have
$\alpha({\tt T})={\tt T}\;\alpha({\tt LLINK(T)})\;{\tt T}\;\alpha({\tt RLINK(T)})\tt\;T$.
Therefore, as Lindstrom observed, the three subsequences
$x_1x_4\ldots x_{3n-2},x_2x_5\ldots x_{3n-1},x_3x_6\ldots x_{3n}$ each
include every tree node just once. (Since $x_{j+1}$ is either the parent
or child of $x_j$, these subsequences visit the nodes in such a way that
each is at most three links away from its predecessor. Section 7.2.1.6
describes a general traversal scheme called *prepostorder* that has this
property not only for binary trees but for trees in general.)

**<span
id="ch02ex_2_7_22a">[22](../Text/ch02a.html#ch02ex_2_7_22)</span>.**
This program uses the conventions of [Programs
T](../Text/ch02a.html#ch02a_pro_t) and
[S](../Text/ch02a.html#ch02a_pro_s), with $\tt Q$ in r\\(\\tt I\\)6
and/or r\\(\\tt I\\)4. The old-fashioned $\tt MIX$ computer is not good
at comparing index registers for equality, so variable $\tt R$ is
omitted and the test “$\tt Q=R$” is changed to “$\tt RLINK(Q)=P$”.

<div class="image">

![Image](../Images/e568_01.gif)

</div>

The total running time is $21n+6a-3-14b$, where *n* is the number of
nodes, *a* is the number of null $\tt RLINK\rm{s}$ (hence $a-1$ is the
number of nonnull $\tt LLINK\rm{s}$), and *b* is the number of nodes on
the tree’s “right spine” $\tt T$, $\tt RLINK(T)$, $\tt RLINK(RLINK(T))$,
etc.

**<span
id="ch02ex_2_7_23a">[23](../Text/ch02a.html#ch02ex_2_7_23)</span>.**
Insertion to the right: $\tt RLINKT(Q)\gets RLINKT(P)$,
$\tt RLINK(P)\gets Q$, ${\tt RTAG(P)}\gets0$,
${\tt LLINK(Q)}\gets\varLambda$. Insertion to the left, assuming
${\tt LLINK(P)}=\varLambda$: Set $\tt LLINK(P)\gets Q$,
$\tt LLINK(Q)\gets\varLambda$, $\tt RLINK(Q)\gets P$,
${\tt RTAG(Q)}\gets1$. Insertion to the left, between $\tt P$ and
$\tt LLINK(P)\neq\varLambda$: Set $\tt R\gets LLINK(P)$,
$\tt LLINK(Q)\gets R$, and then set $\tt R\gets RLINK(R)$ zero or more
times until ${\tt RTAG(R)}=1$; finally set $\tt RLINK(R)\gets Q$,
$\tt LLINK(P)\gets Q$, $\tt RLINK(Q)\gets P$, ${\tt RTAG(Q)}\gets1$.

(A more efficient algorithm for the last case can be used if we know a
node $\tt F$ such that $\tt P=LLINK(F)$ or $\tt P=RLINK(F)$; assuming
the latter, for example, we could set
$\tt INFO(P)\leftrightarrow INFO(Q)$, $\tt RLINK(F)\gets Q$,
$\tt LLINK(Q)\gets P$, $\tt RLINKT(Q)\gets RLINKT(P)$,
$\tt RLINK(P)\gets Q$, ${\tt RTAG(P)}\gets1$. This takes a fixed amount
of time, but it is generally not recommended because it switches nodes
around in memory.)

**<span
id="ch02ex_2_7_24a">[24](../Text/ch02a.html#ch02ex_2_7_24)</span>.** No:
<span class="top">![Image](../Images/569pro01.gif)</span>

**<span
id="ch02ex_2_7_25a">[25](../Text/ch02a.html#ch02ex_2_7_25)</span>.** We
first prove (b), by induction on the number of nodes in *T*, and
similarly (c). Now (a) breaks into several cases; write $T\preceq_1T'$
if (i) holds, $T\preceq_2T'$ if (ii) holds, etc. Then $T\preceq_1T'$ and
$T'\preceq T''$ implies $T\preceq_1T''$; $T\preceq_2T'$ and
$T'\preceq T''$ implies $T\preceq_2T''$; and the remaining two cases are
treated by proving (a) by induction on the number of nodes in *T*.

**<span
id="ch02ex_2_7_26a">[26](../Text/ch02a.html#ch02ex_2_7_26)</span>.** If
the double order of *T* is $(u_1,d_1),(u_2,d_2),\ldots,(u_{2n},d_{2n})$
where the $u\rm\unicode{39}s$ are nodes and the $d\rm\unicode{39}s$ are
1 or 2, form the “trace” of the tree
$(v_1,s_1),(v_2,s_2),\ldots,(v_{2n},s_{2n})$, where
$v_j={\rm info}(u_j)$, and $s_j=l(u_j)$ or $r(u_j)$ according as
$d_j=1\;\rm or\;2$. Now $T\preceq T'$ if and only if the trace of *T*
(as defined here) *lexicographically* precedes or equals the trace of
$T'$. Formally, this means that we have either $n\le n'$ and
$(v_j,s_j)=(v'_j,s'_j)$ for $1\le j\le2n$, or else there is a *k* for
which $(v_j,s_j)=(v'_j,s'_j)$ for $1\le j\lt k$ and either
$v_k\prec v'_k$ or $v_k=v'_k$ and $s_k\lt s'_k$.

**<span
id="ch02ex_2_7_27a">[27](../Text/ch02a.html#ch02ex_2_7_27)</span>.**
**R1.** [Initialize.] Set $\tt P\gets HEAD$, $\tt P'\gets HEAD'$; these
are the respective list heads of the given right-threaded binary trees.
Go to R3.

**R2.** [Check $\tt INFO$.] If ${\tt INFO(P)\prec INFO(P')}$, terminate
$(T\prec T')$; if ${\tt INFO(P)\succ INFO(P')}$, terminate
$(T\succ T')$.

**R3.** [Go to left.] If ${\tt LLINK(P)}=\varLambda={\tt LLINK(P')}$, go
to R4; if ${\tt LLINK(P)}=\varLambda\neq{\tt LLINK(P')}$, terminate
$(T\prec T')$; if ${\tt LLINK(P)\neq\varLambda=LLINK(P')}$, terminate
$(T\succ T')$; otherwise set $\tt P\gets LLINK(P)$,
$\tt P'\gets LLINK(P')$, and go to R2.

**R4.** [End of tree?] If $\tt P=HEAD$ (or, equivalently, if
$\tt P'=HEAD'$), terminate (*T* is equivalent to $T'$).

**R5.** [Go to right.] If ${\tt RTAG(P)}=1={\tt RTAG(P')}$, set
$\tt P\gets RLINK(P)$, $\tt P'\gets RLINK(P')$, and go to R4. If
${\tt RTAG(P)}=1\neq\tt RTAG(P')$, terminate $(T\prec T')$. If
${\tt RTAG(P)}\neq1={\tt RTAG(P')}$, terminate $(T\succ T')$. Otherwise,
set $\tt P\gets RLINK(P)$, $\tt P'\gets RLINK(P')$, and go to R2. <span
class="middle">![Image](../Images/box.gif)</span>

To prove the validity of this algorithm (and therefore to understand how
it works), one may show by induction on the size of the tree $T_0$ that
the following statement is valid: *Starting at step R2 with $\tt P$ and
$\tt P'$ pointing to the roots of two nonempty right-threaded binary
trees $T_0$ and $T'_0$, the algorithm will terminate if $T_0$ and $T'_0$
are not equivalent, indicating whether $T_0\prec T'_0$ or
$T_0\succ T'_0$; the algorithm will reach step R4 if $T_0$ and $T'_0$
are equivalent, with $\tt P$ and $\tt P'$ then pointing respectively to
the successor nodes of $T_0$ and $T'_0$ in symmetric order.*

**<span
id="ch02ex_2_7_28a">[28](../Text/ch02a.html#ch02ex_2_7_28)</span>.**
Equivalent *and* similar.

**<span
id="ch02ex_2_7_29a">[29](../Text/ch02a.html#ch02ex_2_7_29)</span>.**
Prove by induction on the size of *T* that the following statement is
valid: *Starting at step C2 with $\tt P$ pointing to the root of a
nonempty binary tree *T* and with $\tt Q$ pointing to a node that has
empty left and right subtrees, the procedure will ultimately arrive at
step C6 after setting $\tt INFO(Q)\gets INFO(P)$ and attaching copies of
the left and right subtrees of $\tt NODE(P)$ to $\tt NODE(Q)$, and with
$\tt P$ and $\tt Q$ pointing respectively to the preorder successor
nodes of the trees *T* and $\tt NODE(Q)$*.

**<span
id="ch02ex_2_7_30a">[30](../Text/ch02a.html#ch02ex_2_7_30)</span>.**
Assume that the pointer $\tt T$ in
([2](../Text/ch02a.html#ch02eq-lev2sec7-2)) is $\tt LLINK(HEAD)$ in
([10](../Text/ch02a.html#ch02eq-lev2sec7-10)). Thus ${\tt LOC(T)=HEAD}$,
and $\tt HEAD\$$ is the first node of the binary tree in symmetric
order.

**L1.** [Initialize.] Set $\tt Q\gets HEAD$, $\tt RLINK(Q)\gets Q$.

**L2.** [Advance.] Set $\tt P\gets Q\$$. (See below.)

**L3.** [Thread.] If ${\tt RLINK(Q)}=\varLambda$, set
$\tt RLINK(Q)\gets P$, $\tt RTAG(Q)\gets1$; otherwise set
${\tt RTAG(Q)}\gets0$. If ${\tt LLINK(P)}=\varLambda$, set
$\tt LLINK(P)\gets Q$, ${\tt LTAG(P)}\gets1$; otherwise set
${\tt LTAG(P)}\gets0$.

**L4.** [Done?] If $\tt P\neq HEAD$, set $\tt Q\gets P$ and return to
L2. <span class="middle">![Image](../Images/box.gif)</span>

Step L2 of this algorithm implies the activation of an inorder traversal
coroutine like [Algorithm T](../Text/ch02a.html#ch02alg-lev2sec7-T),
with the additional proviso that [Algorithm
T](../Text/ch02a.html#ch02alg-lev2sec7-T) visits $\tt HEAD$ after it has
fully traversed the tree. This notation is a convenient simplification
in the description of tree algorithms, since we need not repeat the
stack mechanisms of [Algorithm T](../Text/ch02a.html#ch02alg-lev2sec7-T)
over and over again. Of course [Algorithm
S](../Text/ch02a.html#ch02alg-lev2sec6-S) cannot be used during step L2,
since the tree hasn’t been threaded yet. But Algorithm U in [answer
21](../Text/app01b.html#ch02ex_2_7_21a) *can* be used in step L2; it
provides us with a very pretty method that threads a tree without using
any auxiliary stack.

**<span
id="ch02ex_2_7_31a">[31](../Text/ch02a.html#ch02ex_2_7_31)</span>.**
**X1.** Set $\tt P\gets HEAD$.

**X2.** Set $\tt Q\gets P\$$ (using, say, [Algorithm
S](../Text/ch02a.html#ch02alg-lev2sec6-S), modified for a right-threaded
tree).

**X3.** If $\tt P\neq HEAD$, set $\tt AVAIL\Leftarrow P$.

**X4.** If $\tt Q\neq HEAD$, set $\tt P\gets Q$ and go back to X2.

**X5.** Set $\tt LLINK(HEAD)\gets\varLambda$. <span
class="middle">![Image](../Images/box.gif)</span>

Other solutions that decrease the length of the inner loop are clearly
possible, although the order of the basic steps is somewhat critical.
The stated procedure works because we never return a node to available
storage until after [Algorithm S](../Text/ch02a.html#ch02alg-lev2sec6-S)
has looked at both its $\tt LLINK$ and its $\tt RLINK$; as observed in
the text, each of these links is used precisely once during a complete
tree traversal.

**<span
id="ch02ex_2_7_32a">[32](../Text/ch02a.html#ch02ex_2_7_32)</span>.**
$\tt RLINK(Q)\gets RLINK(P)$, $\tt SUC(Q)\gets SUC(P)$,
$\tt SUC(P)\gets RLINK(P)\gets Q$, $\tt PRED(Q)\gets P$,
$\tt PRED(SUC(Q))\gets Q$.

**<span
id="ch02ex_2_7_33a">[33](../Text/ch02a.html#ch02ex_2_7_33)</span>.**
Inserting $\tt NODE(Q)$ just to the left and below $\tt NODE(P)$ is
quite simple: Set $\tt LLINKT(Q)\gets LLINKT(P)$, $\tt LLINK(P)\gets Q$,
${\tt LTAG(P)}\gets0$, $\tt RLINK(Q)\gets\varLambda$. Insertion to the
right is considerably harder, since it essentially requires finding
$*\tt Q$, which is of comparable difficulty to finding $\tt Q\sharp$
(see [exercise 19](../Text/ch02a.html#ch02ex_2_7_19)); the node-moving
technique discussed in [exercise 23](../Text/ch02a.html#ch02ex_2_7_23)
could perhaps be used. So general insertions are more difficult with
this type of threading. But the insertions required by [Algorithm
C](../Text/ch02a.html#ch02alg-lev2sec7-C) are not as difficult as
insertions are in general, and in fact the copying process is slightly
faster for this kind of threading:

**C1.** Set $\tt P\gets HEAD$, $\tt Q\gets U$, go to C4. (The
assumptions and philosophy of [Algorithm
C](../Text/ch02a.html#ch02alg-lev2sec7-C) in the text are being used
throughout.)

**C2.** If $\tt RLINK(P)\neq\varLambda$, set $\tt R\Leftarrow AVAIL$,
$\tt LLINK(R)\gets LLINK(Q)$, ${\tt LTAG(R)}\gets1$,
$\tt RLINK(R)\gets\varLambda$, $\tt RLINK(Q)\gets LLINK(Q)\gets R$.

**C3.** Set $\tt INFO(Q)\gets INFO(P)$.

**C4.** If ${\tt LTAG(P)}=0$, set $\tt R\Leftarrow AVAIL$,
$\tt LLINK(R)\gets LLINK(Q)$, ${\tt LTAG(R)}\gets1$,
$\tt RLINK(R)\gets\varLambda$, $\tt LLINK(Q)\gets R$,
${\tt LTAG(Q)}\gets0$.

**C5.** Set $\tt P\gets LLINK(P)$, $\tt Q\gets LLINK(Q)$.

**C6.** If $\tt P\neq HEAD$, go to C2. <span
class="middle">![Image](../Images/box.gif)</span>

The algorithm now seems almost too simple to be correct!

[Algorithm C](../Text/ch02a.html#ch02alg-lev2sec7-C) for threaded or
right-threaded binary trees takes slightly longer due to the extra time
to calculate ${\tt P}*$, ${\tt Q}*$ in step C5.

It would be possible to thread $\tt RLINK\rm s$ in the usual way or to
put $\tt\sharp P$ in $\tt RLINK(P)$, in conjunction with this copying
method, by appropriately setting the values of $\tt RLINK(R)$ and
$\tt RLINKT(Q)$ in steps C2 and C4.

**<span
id="ch02ex_2_7_34a">[34](../Text/ch02a.html#ch02ex_2_7_34)</span>.**
**A1.** Set $\tt Q\gets P$, and then repeatedly set
$\tt Q\gets RLINK(Q)$ zero or more times until ${\tt RTAG(Q)}=1$.

**A2.** Set $\tt R\gets RLINK(Q)$. If ${\tt LLINK(R)}=\tt P$, set
$\tt LLINK(R)\gets\varLambda$. Otherwise set $\tt R\gets LLINK(R)$, then
repeatedly set $\tt R\gets RLINK(R)$ zero or more times until
${\tt RLINK(R)}=\tt P$; then finally set $\tt RLINKT(R)\gets RLINKT(Q)$.
(This step has removed $\tt NODE(P)$ and its subtrees from the original
tree.)

**A3.** Set $\tt RLINK(Q)\gets HEAD$, $\tt LLINK(HEAD)\gets P$. <span
class="middle">![Image](../Images/box.gif)</span>

(The key to inventing and/or understanding this algorithm is the
construction of good “before and after” diagrams.)

**<span
id="ch02ex_2_7_36a">[36](../Text/ch02a.html#ch02ex_2_7_36)</span>.** No;
see the answer to [exercise
1.2.1–15](../Text/ch01.html#ch01ex_2_1_15)(e).

**<span
id="ch02ex_2_7_37a">[37](../Text/ch02a.html#ch02ex_2_7_37)</span>.** If
${\tt LLINK(P)}={\tt RLINK(P)}=\varLambda$ in the representation
([2](../Text/ch02a.html#ch02eq-lev2sec7-2)), let
${\tt LINK(P)}=\varLambda$; otherwise let ${\tt LINK(P)}=\tt Q$ where
$\tt NODE(Q)$ corresponds to $\tt NODE(LLINK(P))$ and $\tt NODE(Q+1)$ to
$\tt NODE(RLINK(P))$. The condition $\tt LLINK(P)$ or
$\tt RLINK(P)=\varLambda$ is represented by a sentinel in $\tt NODE(Q)$
or $\tt NODE(Q+1)$ respectively. This representation uses between *n*
and $2n-1$ memory positions; under the stated assumptions,
([2](../Text/ch02a.html#ch02eq-lev2sec7-2)) would require 18 words of
memory, compared to 11 in the present scheme. Insertion and deletion
operations are approximately of equal efficiency in either
representation. But this representation is not quite as versatile in
combination with other structures.

<div class="heading">

#### Section 2.3.2 {#app01lev2sec24}

**<span
id="ch02ex_2_8_1a">[1](../Text/ch02a.html#ch02ex_2_8_1)</span>.** If *B*
is empty, $F(B)$ is an empty forest. Otherwise, $F(B)$ consists of a
tree *T* plus the forest $F({\rm right}(B))$, where
${\rm root}(T)={\rm root}(B)$ and ${\rm subtrees}(T)=F({\rm left}(B))$.

</div>

**<span
id="ch02ex_2_8_2a">[2](../Text/ch02a.html#ch02ex_2_8_2)</span>.** The
number of zeros in the binary notation is the number of decimal points
in the decimal notation; the exact formula for the correspondence is

$a_1.a_2.\cdots.a_k\leftrightarrow 1^{a_1}01^{a_2-1}0\ldots01^{a_k-1}$,

where $1^a$ denotes *a* ones in a row.

**<span
id="ch02ex_2_8_3a">[3](../Text/ch02a.html#ch02ex_2_8_3)</span>.** Sort
the Dewey decimal notations for the nodes lexicographically (from left
to right, as in a dictionary), placing a shorter sequence
$a_1.\cdots.a_k$ in front of its extensions $a_1.\cdots.a_k.\cdots.a_r$
for preorder, and behind its extensions for postorder. Thus, if we were
sorting words instead of sequences of numbers, we would place the words
*cat*, *cataract* in the usual dictionary order, to get preorder; we
would reverse the order of initial subwords $(cataract,cat)$, to get
postorder. These rules are readily proved by induction on the size of
the tree.

**<span
id="ch02ex_2_8_4a">[4](../Text/ch02a.html#ch02ex_2_8_4)</span>.** True,
by induction on the number of nodes.

**<span
id="ch02ex_2_8_5a">[5](../Text/ch02a.html#ch02ex_2_8_5)</span>.** (a)
Inorder. (b) Postorder. It is interesting to formulate rigorous
induction proofs of the equivalence of these traversal algorithms.

**<span
id="ch02ex_2_8_6a">[6](../Text/ch02a.html#ch02ex_2_8_6)</span>.** We
have ${\rm preorder}(T)={\rm preorder}(T')$, and
${\rm postorder}(T)={\rm inorder}(T')$, even if *T* has nodes with only
one child. The remaining two orders are not in any simple relation; for
example, the root of *T* comes at the end in one case and about in the
middle in the other.

**<span
id="ch02ex_2_8_7a">[7](../Text/ch02a.html#ch02ex_2_8_7)</span>.** (a)
Yes; (b) no; (c) no; (d) yes. Note that reverse preorder of a forest
equals postorder of the left-right reversed forest (in the sense of
mirror reflection).

**<span
id="ch02ex_2_8_8a">[8](../Text/ch02a.html#ch02ex_2_8_8)</span>.**
$T\preceq T'$ means that either
${\rm info}({\rm root}(T))\prec{\rm info}({\rm root}(T'))$, or these
info’s are equal and the following condition holds: Suppose the subtrees
of ${\rm root}(T)$ are $T_1,\ldots,T_n$ and the subtrees of
${\rm root}(T')$ are $T'_1,\ldots,T'_{n'}$, and let $k\ge0$ be as large
as possible such that $T_j$ is equivalent to $T'_j$ for $1\le j\le k$.
Then either $k=n$ or $k\lt n$ and $T_{k+1}\preceq T'_{k+1}$.

**<span
id="ch02ex_2_8_9a">[9](../Text/ch02a.html#ch02ex_2_8_9)</span>.** The
number of nonterminal nodes is one less than the number of right links
that are *Λ*, in a nonempty forest, because the null right links
correspond to the rightmost child of each nonterminal node, and also to
the root of the rightmost tree in the forest. (This fact gives another
proof of [exercise 2.3.1–14](../Text/ch02a.html#ch02ex_2_7_14), since
the number of null left links is obviously equal to the number of
*terminal* nodes.)

**<span
id="ch02ex_2_8_10a">[10](../Text/ch02a.html#ch02ex_2_8_10)</span>.** The
forests are similar if and only if $n=n'$ and $d(u_j)=d(u'_j)$, for
$1\le j\le n$; they are equivalent if and only if in addition
${\rm info}(u_j)={\rm info}(u'_j)$, $1\le j\le n$. The proof is similar
to the previous proof, by generalizing [Lemma
2.3.1P](../Text/ch02a.html#ch02aLemma-p); let $f(u)=d(u)-1$.

**<span
id="ch02ex_2_8_11a">[11](../Text/ch02a.html#ch02ex_2_8_11)</span>.**<span
class="top">![Image](../Images/572fig01.gif)</span>

**<span
id="ch02ex_2_8_12a">[12](../Text/ch02a.html#ch02ex_2_8_12)</span>.** If
${\tt INFO(Q1)}\neq0$: Set $\tt R\gets COPY(P1)$; then if
${\tt TYPE(P2)}=0$ and ${\tt INFO(P2)}\neq2$, set
${\tt R\gets TREE(“\uparrow”,R,TREE(INFO(P2)}-1\tt))$; if
${\tt TYPE(P2)}\neq0$, set
${\tt R\gets TREE(“\uparrow”,R,TREE(“-”,COPY(P2),TREE(}1\tt)))$; then
set ${\tt Q1\gets MULT(Q1,MULT(COPY(P2),R))}$.

If ${\tt INFO(Q)}\neq0$: Set
${\tt Q\gets TREE(}“\times”{\tt,MULT(TREE(}“\rm ln”{\tt,COPY(P1)),Q),TREE(}“\uparrow”{\tt,COPY(P1),COPY(P2)))}$.

Finally go to ${\tt DIFF[}4{\tt]}$.

**<span
id="ch02ex_2_8_13a">[13](../Text/ch02a.html#ch02ex_2_8_13)</span>.** The
following program implements [Algorithm
2.3.1C](../Text/ch02a.html#ch02alg-lev2sec7-C) with
$\rm rI1\equiv\tt P$, $\rm rI2\equiv\tt Q$, $\rm rI3\equiv\tt R$, and
with appropriate changes to the initialization and termination
conditions:

<div class="image">

![Image](../Images/572pro01.gif)

</div>

<div class="image">

![Image](../Images/572pro01a.gif)

</div>

**<span
id="ch02ex_2_8_14a">[14](../Text/ch02a.html#ch02ex_2_8_14)</span>.** Let
*a* be the number of nonterminal (operator) nodes copied. The number of
executions of the various lines in the previous program is as follows:
$064–\!067,1$; $069,a$; $070–\!079,a+1$; $080–\!081,n-1$;
$082–\!088,n-1-a$; $089–\!094,n$; $095,n-a$; $096–\!098,n+1$;
$099–\!100,n-a$; $101–\!103,1$. The total time is $(36n+22)u$; we use
about 20% of the time to get available nodes, 40% to traverse, and 40%
to copy the $\tt INFO$ and $\tt LINK$ information.

**<span
id="ch02ex_2_8_15a">[15](../Text/ch02a.html#ch02ex_2_8_15)</span>.**
Comments are left to the reader.

<div class="image">

![Image](../Images/573pro01.gif)

</div>

**<span
id="ch02ex_2_8_16a">[16](../Text/ch02a.html#ch02ex_2_8_16)</span>.**
Comments are left to the reader.

<div class="image">

![Image](../Images/574pro01.gif)

</div>

**<span
id="ch02ex_2_8_17a">[17](../Text/ch02a.html#ch02ex_2_8_17)</span>.**
References to early work on such problems can be found in a survey
article by J. Sammet, *CACM* **9** (1966), 555–569.

**<span
id="ch02ex_2_8_18a">[18](../Text/ch02a.html#ch02ex_2_8_18)</span>.**
First set ${\tt LLINK[}j{\tt]\gets RLINK[}j{\tt]}\gets j$ for all *j*,
so that each node is in a circular list of length 1. Then for $j=n$,
$n-1,\ldots,1$ (in this order), if ${\tt PARENT[}j{\tt]}=0$ set
$r\gets j$, otherwise insert the circular list starting with *j* into
the circular list starting with ${\tt PARENT[}j{\tt]}$ as follows:
$k\gets{\tt PARENT[}j{\tt]}$, $l\gets{\tt RLINK[}k{\tt]}$,
$i\gets{\tt LLINK[}j{\tt]}$, ${\tt LLINK[}j{\tt]}\gets k$,
${\tt RLINK[}k{\tt]}\gets j$, ${\tt LLINK[}l{\tt]}\gets i$,
${\tt RLINK[}i{\tt]}\gets l$. This works because (a) each nonroot node
is always preceded by its parent or by a descendant of its parent; (b)
nodes of each family appear in their parent’s list, in order of
location; (c) preorder is the unique order satisfying (a) and (b).

**<span
id="ch02ex_2_8_20a">[20](../Text/ch02a.html#ch02ex_2_8_20)</span>.** If
*u* is an ancestor of *υ*, it is immediate by induction that *u*
precedes *υ* in preorder and follows *υ* in postorder. Conversely,
suppose *u* precedes *υ* in preorder and follows *υ* in postorder; we
must show that *u* is an ancestor of *υ*. This is clear if *u* is the
root of the first tree. If *u* is another node of the first tree, *υ*
must be also, since *u* follows *υ* in postorder; so induction applies.
Similarly if *u* is not in the first tree, *υ* must not be either, since
*u* precedes *υ* in preorder. (This exercise also follows easily from
the result of [exercise 3](../Text/ch02a.html#ch02ex_2_8_3). It gives us
a quick test for ancestorhood, if we know each node’s position in
preorder and postorder.)

**<span
id="ch02ex_2_8_21a">[21](../Text/ch02a.html#ch02ex_2_8_21)</span>.** If
$\tt NODE(P)$ is a binary operator, pointers to its two operands are
$\tt P1=LLINK(P)$ and $\tt P2=RLINK(P1)=\$P$. [Algorithm
D](../Text/ch02a.html#ch02alg-lev2sec8-D) makes use of the fact that
$\tt P2\$=P$, so that $\tt RLINK(P1)$ may be changed to $\tt Q1$, a
pointer to the derivative of $\tt NODE(P1)$; then $\tt RLINK(P1)$ is
reset later in step D3. For ternary operations, we would have, say,
$\tt P1=LLINK(P)$, $\tt P2=RLINK(P1)$, $\tt P3=RLINK(P2)=\$P$, so it is
difficult to generalize the binary trick. After computing the derivative
$\tt Q1$, we could set $\tt RLINK(P1)\gets Q1$ temporarily, and then
after computing the next derivative $\tt Q2$ we could set
$\tt RLINK(Q2)\gets Q1$ and $\tt RLINK(P2)\gets Q2$ and reset
$\tt RLINK(P1)\gets P2$. But this is certainly inelegant, and it becomes
progressively more so as the degree of the operator becomes higher.
Therefore the device of temporarily changing $\tt RLINK(P1)$ in
[Algorithm D](../Text/ch02a.html#ch02alg-lev2sec8-D) is definitely a
*trick*, <span id="page_575"></span>not a *technique*. A more aesthetic
way to control a differentiation process, because it generalizes to
operators of higher degree and does not rely on isolated tricks, can be
based on [Algorithm 2.3.3F](../Text/ch02a.html#ch02alg-lev2sec9-F); see
[exercise 2.3.3–3](../Text/ch02b.html#ch02ex_2_9_1).

**<span
id="ch02ex_2_8_22a">[22](../Text/ch02a.html#ch02ex_2_8_22)</span>.**
From the definition it follows immediately that the relation is
transitive; that is, if $T\subseteq T'$ and $T'\subseteq T''$ then
$T\subseteq T''$. (In fact the relation is easily seen to be a partial
ordering.) If we let *f* be the function taking nodes into themselves,
clearly $l(T)\subseteq T$ and $r(T)\subseteq T$. Therefore if
$T\subseteq l(T')$ or $T\subseteq r(T')$ we must have $T\subseteq T'$.

Suppose $f_l$ and $f_r$ are functions that respectively show
$l(T)\subseteq l(T')$ and $r(T)\subseteq r(T')$. Let $f(u)=f_l(u)$ if
*u* is in $l(T)$, $f(u)={\rm root}(T')$ if *u* is ${\rm root}(T)$,
otherwise $f(u)=f_r(u)$. Now it follows easily that *f* shows
$T\subseteq T'$; for example, if we let $r'(T)$ denote
$r(T)\backslash{\rm root}(T)$ we have
${\rm preorder}(T)={\rm root}(T){\rm preorder}(l(T)){\rm preorder}(r'(T))$;
${\rm preorder}(T')=f({\rm root}(T)){\rm preorder}(l(T')){\rm preorder}(r'(T'))$.

The converse does not hold: Consider the subtrees with roots *b* and
$b'$ in [Fig. 25](../Text/ch02a.html#ch02fig25).

<div class="heading">

#### Section 2.3.3 {#app01lev2sec25}

**<span
id="ch02ex_2_9_1a">[1](../Text/ch02b.html#ch02ex_2_9_1)</span>.** Yes,
we can reconstruct them just as
([3](../Text/ch02.html#ch02eq-lev2sec3-3)) is deduced from
([4](../Text/ch02.html#ch02eq-lev2sec3-4)), but interchanging $\tt LTAG$
and $\tt RTAG$, $\tt LLINK$ and $\tt RLINK$, and using a queue instead
of a stack.

</div>

**<span
id="ch02ex_2_9_2a">[2](../Text/ch02b.html#ch02ex_2_9_2)</span>.** Make
the following changes in [Algorithm
F](../Text/ch02a.html#ch02alg-lev2sec9-F): Step F1, change to “last node
of the forest in preorder.” Step F2, change “$f(x_d),\ldots,f(x_1)$” to
“$f(x_1),\ldots,f(x_d)$” in two places. Step F4, “If $\tt P$ is the
first node in preorder, terminate the algorithm. (Then the stack
contains $f({\rm root}(T_1)),\ldots,f({\rm root}(T_m))$, from top to
bottom, where $T_1,\ldots,T_m$ are the trees of the given forest, from
left to right.) Otherwise set $\tt P$ to its predecessor in preorder
(\\({\\tt P\\gets P}-c\\) in the given representation), and return to
F2.”

**<span
id="ch02ex_2_9_3a">[3](../Text/ch02b.html#ch02ex_2_9_3)</span>.** In
step D1, also set ${\tt S}\gets\varLambda$. (\\(\\tt S\\) is a link
variable that links to the top of the stack.) Step D2 becomes, for
example, “If $\tt NODE(P)$ denotes a unary operator, set $\tt Q\gets S$,
$\tt S\gets RLINK(Q)$, ${\tt P1\gets LLINK(P)}$; if it denotes a binary
operator, set $\tt Q\gets S$, ${\tt Q1\gets RLINK(Q)}$,
${\tt S\gets RLINK(Q1)}$, ${\tt P1\gets LLINK(P)}$,
${\tt P2\gets RLINK(P1)}$. Then perform ${\tt DIFF[TYPE(P)]}$.” Step D3
becomes “Set $\tt RLINK(Q)\gets S$, $\tt S\gets Q$.” Step D4 becomes
“Set $\tt P\gets P\$$.” The operation ${\tt LLINK(DY)\gets Q}$ may be
avoided in step D5 if we assume that ${\tt S}\equiv\tt LLINK(DY)$. This
technique clearly generalizes to ternary and higher-order operators.

**<span
id="ch02ex_2_9_4a">[4](../Text/ch02b.html#ch02ex_2_9_4)</span>.** A
representation like ([10](../Text/ch02.html#ch02eq-lev2sec3-10)) takes
$n-m$ $\tt LLINK\rm{s}$ and $n+(n-m)$ $\tt RLINK\rm{s}$. The difference
in total number of links is $n-2m$ between the two forms of
representation. Arrangement ([10](../Text/ch02.html#ch02eq-lev2sec3-10))
is superior when the $\tt LLINK$ and $\tt INFO$ fields require about the
same amount of space in a node and when *m* is rather large, namely when
the nonterminal nodes have rather large degrees.

**<span
id="ch02ex_2_9_5a">[5](../Text/ch02b.html#ch02ex_2_9_5)</span>.** It
would certainly be silly to include threaded $\tt RLINK\rm{s}$, since an
$\tt RLINK$ thread just points to $\tt PARENT$ anyway. Threaded
$\tt LLINK\rm{s}$ as in
[2.3.2](../Text/ch02a.html#ch02lev2sec8)–([4](../Text/ch02a.html#ch02eq-lev2sec8-4))
would be useful if it is necessary to move leftward in the tree, for
example if we wanted to traverse a tree in reverse postorder, or in
family order; but these operations are not significantly harder without
threaded $\tt LLINK\rm{s}$ unless the nodes tend to have very high
degrees.

**<span
id="ch02ex_2_9_6a">[6](../Text/ch02b.html#ch02ex_2_9_6)</span>.**
**L1.** Set $\tt P\gets FIRST$, ${\tt FIRST}\gets\varLambda$.

**L2.** If ${\tt P}=\varLambda$, terminate. Otherwise set
$\tt Q\gets RLINK(P)$.

**L3.** If ${\tt PARENT(P)}=\varLambda$, set $\tt RLINK(P)\gets FIRST$,
$\tt FIRST\gets P$; otherwise set $\tt R\gets PARENT(P)$,
$\tt RLINK(P)\gets LCHILD(R)$, $\tt LCHILD(R)\gets P$.

**L4.** Set $\tt P\gets Q$ and return to L2. <span
class="middle">![Image](../Images/box.gif)</span>

**<span
id="ch02ex_2_9_7a">[7](../Text/ch02b.html#ch02ex_2_9_7)</span>.**
$\{1,5\}\{2,3,4,7\}\{6,8,9\}$.

**<span
id="ch02ex_2_9_8a">[8](../Text/ch02b.html#ch02ex_2_9_8)</span>.**
Perform step E3 of [Algorithm E](../Text/ch02a.html#ch02alg-lev2sec9-E),
then test if $j=k$.

**<span
id="ch02ex_2_9_9a">[9](../Text/ch02b.html#ch02ex_2_9_9)</span>.** <span
class="top">![Image](../Images/576pro01.gif)</span>

**<span
id="ch02ex_2_9_10a">[10](../Text/ch02b.html#ch02ex_2_9_10)</span>.** One
idea is to set $\tt PARENT$ of each *root* node to the negative of the
number of nodes in its tree (these values being easily kept up to date);
then if $|{\tt PARENT[}j{\tt]}|\gt |{\tt PARENT[}k{\tt]}|$ in step E4,
the roles of *j* and *k* are interchanged. This technique (due to M. D.
McIlroy) ensures that each operation takes $O(log n)$ steps.

For still more speed, we can use the following suggestion due to Alan
Tritter: In step E4, set ${\tt PARENT[}x{\tt]}\gets k$ for all values
$x\neq k$ that were encountered in step E3. This makes an extra pass up
the trees, but it collapses them so that future searches are faster.
(See Section 7.4.1.)

**<span
id="ch02ex_2_9_11a">[11](../Text/ch02b.html#ch02ex_2_9_11)</span>.** It
suffices to define the transformation that is done for each input
$({\tt P},j,{\tt Q},k)$:

**T1.** If $\tt PARENT(P)\neq\varLambda$, set $j\gets j+\tt DELTA(P)$,
$\tt P\gets PARENT(P)$, and repeat this step.

**T2.** If $\tt PARENT(Q)\neq\varLambda$, set $k\gets k+\tt DELTA(Q)$,
$\tt Q\gets PARENT(Q)$, and repeat this step.

**T3.** If $\tt P=Q$, check that $j=k$ (otherwise the input erroneously
contains contradictory equivalences). If $\tt P\neq Q$, set
${\tt DELTA(Q)}\gets j-k$, $\tt PARENT(Q)\gets P$,
${\tt LBD(P)\gets\min(LBD(P),LBD(Q)+DELTA(Q))}$, and
${\tt UBD(P)\gets\max(UBD(P),UBD(Q)+DELTA(Q))}$. <span
class="middle">![Image](../Images/box.gif)</span>

*Note:* It is possible to allow the ${\tt ARRAY\;X[}l:u\tt]$
declarations to occur intermixed with equivalences, or to allow
assignment of certain addresses of variables before others are
equivalenced to them, etc., under suitable conditions that are not
difficult to understand. For further development of this algorithm, see
*CACM* **7** (1964), 301–303, 506.

**<span
id="ch02ex_2_9_12a">[12](../Text/ch02b.html#ch02ex_2_9_12)</span>.** (a)
Yes. (If this condition is not required, it would be possible to avoid
the loops on $\tt S$ that appear in steps A2 and A9.) (b) Yes.

**<span
id="ch02ex_2_9_13a">[13](../Text/ch02b.html#ch02ex_2_9_13)</span>.** The
crucial fact is that the $\tt UP$ chain leading upward from $\tt P$
always mentions the same variables and the same exponents for these
variables as the $\tt UP$ chain leading upward from $\tt Q$, except that
the latter chain may include additional steps for variables with
exponent zero. (This condition holds throughout most of the algorithm,
except during the execution of steps A9 and A10.) Now we get to step A8
either from A3 or from A10, and in each case it was verified that
${\tt EXP(Q)}\neq0$. Therefore ${\tt EXP(P)}\neq0$, and in particular it
follows that ${\tt P}\neq\varLambda$, ${\tt Q}\neq\varLambda$,
${\tt UP(P)}\neq\varLambda$, ${\tt UP(Q)}\neq\varLambda$; the result
stated in the exercise now follows. Thus the proof depends on showing
that the $\tt UP$ chain condition stated above is preserved by the
actions of the algorithm.

**<span
id="ch02ex_2_9_14a">[14](../Text/ch02b.html#ch02ex_2_9_14)</span>, <span
id="ch02ex_2_9_15a">[15](../Text/ch02b.html#ch02ex_2_9_15)</span>.** See
Martin Ward and Hussain Zedan, “Provably correct derivation of
algorithms using FermaT,” *Formal Aspects of Computing* **27** (2015),
to appear.

**<span
id="ch02ex_2_9_16a">[16](../Text/ch02b.html#ch02ex_2_9_16)</span>.** We
prove (by induction on the number of nodes in a *single tree *T**) that
if $\tt P$ is a pointer to *T*, and if the stack is initially empty,
steps F2 through F4 will end with the single value $f({\rm root}(T))$ on
the stack. This is true for $n=1$. If $n\gt1$, there are
$0\lt d={\tt DEGREE}({\rm root}(T))$ subtrees $T_1,\ldots,T_d$; by
induction and the nature of a stack, and since postorder consists of
$T_1,\ldots,T_d$ followed by ${\rm root}(T)$, the algorithm computes
$f(T_1),\ldots,f(T_d)$, and then $f({\rm root}(T))$, as desired. The
validity of [Algorithm F](../Text/ch02a.html#ch02alg-lev2sec9-F) for
forests follows.

**<span
id="ch02ex_2_9_17a">[17](../Text/ch02b.html#ch02ex_2_9_17)</span>.**
**G1.** Set the stack empty, and let $\tt P$ point to the root of the
tree (the last node in postorder). Evaluate $f({\tt NODE(P)})$.

**G2.** Push $\tt DEGREE(P)$ copies of $f({\tt NODE(P)})$ onto the
stack.

**G3.** If $\tt P$ is the first node in postorder, terminate the
algorithm. Otherwise set $\tt P$ to its predecessor in postorder (this
would be simply ${\tt P\gets P}-c$ in
([9](../Text/ch02.html#ch02eq-lev2sec3-9))).

**G4.** Evaluate $f({\tt NODE(P)})$ using the value at the top of the
stack, which is equal to $f({\tt NODE(PARENT(P))})$. Pop this value off
the stack, and return to G2. <span
class="middle">![Image](../Images/box.gif)</span>

*Note:* An algorithm analogous to this one can be based on preorder
instead of postorder as in [exercise
2](../Text/ch02b.html#ch02ex_2_9_2). In fact, family order or level
order could be used; in the latter case we would use a queue instead of
a stack.

**<span
id="ch02ex_2_9_18a">[18](../Text/ch02b.html#ch02ex_2_9_18)</span>.** The
$\tt INFO1$ and $\tt RLINK$ tables, together with the suggestion for
computing $\tt LTAG$ in the text, give us the equivalent of a binary
tree represented in the usual manner. The idea is to traverse this tree
in postorder, counting degrees as we go:

**P1.** Let $\tt R$, $\tt D$, and $\tt I$ be stacks that are initially
empty; then set ${\tt R}\Leftarrow n+1$, ${\tt D}\Leftarrow 0$,
$j\gets0$, $k\gets0$.

**P2.** If ${\rm top}({\tt R})\gt j+1$, go to P5. (If an $\tt LTAG$
field were present, we could have tested ${\tt LTAG[}j{\tt]}=0$ instead
of ${\rm top}({\tt R})\gt j+1$.)

**P3.** If $\tt I$ is empty, terminate the algorithm; otherwise set
$i\Leftarrow\tt I$, $k\gets k+1$,
${\tt INFO2[}k{\tt]\gets INFO1[}i{\tt]}$,
${\tt DEGREE[}k{\tt]\Leftarrow D}$.

**P4.** If ${\tt RLINK[}i{\tt]}=0$, go to P3; otherwise delete the top
of $\tt R$ (which will equal ${\tt RLINK[}i{\tt]}$).

**P5.** Set ${\rm top}({\tt D})\gets{\rm top}({\tt D})+1$, $j\gets j+1$,
${\tt I}\Leftarrow j$, ${\tt D}\Leftarrow 0$, and if
${\tt RLINK[}j{\tt]}\neq0$ set ${\tt R}\Leftarrow{\tt RLINK[}j{\tt]}$.
Go to P2. <span class="middle">![Image](../Images/box.gif)</span>

**<span
id="ch02ex_2_9_19a">[19](../Text/ch02b.html#ch02ex_2_9_19)</span>.** (a)
This property is equivalent to saying that $\tt SCOPE$ links do not
cross each other.

\(b) The first tree of the forest contains $d_1+1$ elements, and we can
proceed by induction.

\(c) The condition of (a) is preserved when we take minima.

*Notes:* By [exercise 2.3.2–20](../Text/ch02a.html#ch02ex_2_8_20), it
follows that $d_1d_2\ldots d_n$ can also be interpreted in terms of
inversions: If the $k\rm th$ node in postorder is the $p_k\rm th$ node
in preorder, then $d_k$ is the number of elements $\gt k$ that appear to
the left of *k* in $p_1p_2\ldots p_n$.

A similar scheme, in which we list the number of descendants of each
node in *postorder* of the forest, leads to sequences of numbers
$c_1c_2\ldots c_n$ characterized by the properties (i) $0\le c_k\lt k$
and (ii) $k\ge j\ge k-c_k$ implies $j-c_j\ge k-c_k$. Algorithms based on
such sequences have been investigated by J. M. Pallo, *Comp. J.* **29**
(1986), 171–175. Notice that $c_k$ is the size of the left subtree of
the $k\rm th$ node in symmetric order of the corresponding binary tree.
We can also interpret $d_k$ as the size of the *right* subtree of the
$k\rm th$ node in symmetric order of a suitable binary tree, namely the
binary tree that corresponds to the given forest by the dual method of
[exercise 2.3.2–5](../Text/ch02a.html#ch02ex_2_8_5).

The relation $d_k\le d'_k$ for $1\le k\le n$ defines an interesting
lattice ordering of forests and binary trees, first introduced in
another way by D. Tamari [Thèse (Paris, 1951)]; see exercise 6.2.3–32.

<div class="heading">

##### <span id="page_578"></span>Section 2.3.4.1 {#app01lev3sec6}

**<span
id="ch02ex_3_1_1a">[1](../Text/ch02b.html#ch02ex_3_1_1)</span>.**
$(B,A,C,D,B)$, $(B,A,C,D,E,B)$, $(B,D,C,A,B)$, $(B,D,E,B)$, $(B,E,D,B)$,
$(B,E,D,C,A,B)$.

</div>

**<span
id="ch02ex_3_1_2a">[2](../Text/ch02b.html#ch02ex_3_1_2)</span>.** Let
$(V_0,V_1,\ldots,V_n)$ be a walk of smallest possible length from *V* to
$V'$. If now $V_j=V_k$ for some $j\lt k$, then
$(V_0,\ldots,V_j,V_{k+1},\ldots,V_n)$ would be a shorter walk.

**<span
id="ch02ex_3_1_3a">[3](../Text/ch02b.html#ch02ex_3_1_3)</span>.** (The
fundamental path traverses $e_3$ and $e_4$ once, but cycle $C_2$
traverses them $-1$ times, giving a net total of zero.) Traverse the
following edges: $e_1$, $e_2$, $e_6$, $e_7$, $e_9$, $e_{10}$, $e_{11}$,
$e_{12}$, $e_{14}$.

**<span
id="ch02ex_3_1_4a">[4](../Text/ch02b.html#ch02ex_3_1_4)</span>.** If
not, let $G″$ be the subgraph of $G'$ obtained by deleting each edge
$e_j$ for which $E_j=0$. Then $G''$ is a finite graph that has no cycles
and at least one edge, so by the proof of [Theorem
A](../Text/ch02b.html#ch02b_the_a) there is at least one vertex, *V*,
that is adjacent to exactly one other vertex, $V'$. Let $e_j$ be the
edge joining *V* to $V'$; then Kirchhoff’s equation
([1](../Text/ch02b.html#ch02eq-lev3sec1-1)) at vertex *V* is $E_j=0$,
contradicting the definition of $G″$.

**<span
id="ch02ex_3_1_5a">[5](../Text/ch02b.html#ch02ex_3_1_5)</span>.**
$A=1+E_8$, $B=1+E_8-E_2$, $C=1+E_8$, $D=1+E_8-E_5$, $E=1+E_{17}-E_{21}$,
$F=1+E''_{13}+E_{17}-E_{21}$, $G=1+E''_{13}$, $H=E_{17}-E_{21}$,
$J=E_{17}$, $K=E''_{19}+E_{20}$, $L=E_{17}+E''_{19}+E_{20}-E_{21}$,
$P=E_{17}+E_{20}-E_{21}$, $Q=E_{20}$, $R=E_{17}-E_{21}$, $S=E_{25}$.\
 *Note:* In this case it is also possible to solve for
$E_2,E_5,\ldots,E_{25}$ in terms of $A,B,\ldots,S$; hence there are nine
independent solutions, explaining why we eliminated six variables in Eq.
[1.3.3](../Text/ch01b.html#ch01lev2sec14)–([8](../Text/ch01b.html#ch01eq-lev3sec3-8)).

**<span
id="ch02ex_3_1_6a">[6](../Text/ch02b.html#ch02ex_3_1_6)</span>.** (The
following solution is based on the idea that we may print out each edge
that does not make a cycle with the preceding edges.) Use [Algorithm
2.3.3E](../Text/ch02a.html#ch02alg-lev2sec9-E), with each pair
$(a_i,b_i)$ representing $a_i\equiv b_i$ in the notation of that
algorithm. The only change is to print $(a_i,b_i)$ if $j\neq k$ in step
E4.

To show that this algorithm is valid, we must prove that (a) the
algorithm prints out no edges that form a cycle, and (b) if *G* contains
at least one free subtree, the algorithm prints out $n-1$ edges. Define
$j\equiv k$ if there exists a path from $V_j$ to $V_k$ or if $j=k$. This
is clearly an equivalence relation, and moreover $j\equiv k$ if and only
if this relation can be deduced from the equivalences
$a_1\equiv b_1,\ldots,a_m\equiv b_m$. Now (a) holds because the
algorithm prints out no edges that form a cycle with previously printed
edges; (b) is true because ${\tt PARENT[}k{\tt]}=0$ for precisely one
*k* if all vertices are equivalent.

A more efficient algorithm can, however, be based on depth-first search;
see [Algorithm 2.3.5A](../Text/ch02c.html#ch02alg-lev2sec11-A) and
Section 7.4.1.

**<span
id="ch02ex_3_1_7a">[7](../Text/ch02b.html#ch02ex_3_1_7)</span>.**
Fundamental cycles: $C_0=e_0+e_1+e_4+e_9$ (fundamental path is
$e_1+e_4+e_9$); $C_5=e_5+e_3+e_2$; $C_6=e_6-e_2+e_4$; $C_7=e_7-e_4-e_3$;
$C_8=e_8-e_9-e_4-e_3$. Therefore we find $E_1=1$, $E_2=E_5-E_6$,
$E_3=E_5-E_7-E_8$, $E_4=1+E_6-E_7-E_8$, $E_9=1-E_8$.

**<span
id="ch02ex_3_1_8a">[8](../Text/ch02b.html#ch02ex_3_1_8)</span>.** Each
step in the reduction process combines two arrows $e_i$ and $e_j$ that
start at the same box, and it suffices to prove that such steps can be
reversed. Thus we are given the value of $e_i+e_j$ after combination,
and we must assign consistent values to $e_i$ and $e_j$ before the
combination. There are three essentially different situations:

<div class="image">

![Image](../Images/e578_05.gif)

</div>

Here *A*, *B*, and *C* stand for vertices or supervertices, and the
$\alpha\rm\unicode{39}s$ and $\beta\rm\unicode{39}s$ stand for the other
given flows besides $e_i+e_j$; these flows may each be distributed among
several edges, although only one is shown. In Case 1 (\\(e\_i\\) and
$e_j$ lead to the same box), we may choose $e_i$ arbitrarily, then
$e_j\gets (e_i+e_j)-e_i$. In Case 2 (\\(e\_i\\) and $e_j$ lead to
different boxes), we must set $e_i\gets\beta'-\alpha'$,
$e_j\gets\beta''-\alpha''$. In Case 3 (\\(e\_i\\) is a loop but $e_j$ is
not), we must set $e_j\gets\beta'-\alpha'$, $e_i\gets (e_i+e_j)-e_j$. In
each case we have reversed the combination step as desired.

The result of this exercise essentially proves that the number of
fundamental cycles in the reduced flow chart is the minimum number of
vertex flows that must be measured to determine all the others. In the
given example, the reduced flow chart reveals that only three vertex
flows (e.g., *a*, *c*, *d*) need to be measured, while the original
chart of [exercise 7](../Text/ch02b.html#ch02ex_3_1_7) has four
independent edge flows. We save one measurement every time Case 1 occurs
during the reduction.

A similar reduction procedure could be based on combining the arrows
flowing *into* a given box, instead of those flowing out. It can be
shown that this would yield the same reduced flow chart, except that the
supervertices would contain different names.

The construction in this exercise is based on ideas due to Armen
Nahapetian and F. Stevenson. For further comments, see A. Nahapetian,
*Acta Informatica* **3** (1973), 37–41; D. E. Knuth and F. Stevenson,
*BIT* **13** (1973), 313–322.

**<span
id="ch02ex_3_1_9a">[9](../Text/ch02b.html#ch02ex_3_1_9)</span>.** Each
edge from a vertex to itself becomes a “fundamental cycle” all by
itself. If there are $k+1$ edges $e,e',\ldots,e^{(k)}$ between vertices
*V* and $V'$, make *k* fundamental cycles $e'±e,\ldots,e^{(k)}±e$
(choosing + or − according as the edges go in the opposite or the same
direction), and then proceed as if only edge *e* were present.

Actually this situation would be much simpler conceptually if we had
defined a graph in such a way that multiple edges are allowed between
vertices, and edges are allowed from a vertex to itself; paths and
cycles would be defined in terms of edges instead of vertices. Such a
definition is, in fact, made for directed graphs in [Section
2.3.4.2](../Text/ch02b.html#ch02lev3sec2).

**<span
id="ch02ex_3_1_10a">[10](../Text/ch02b.html#ch02ex_3_1_10)</span>.** If
the terminals have all been connected together, the corresponding graph
must be connected in the technical sense. A minimum number of wires will
involve no cycles, so we must have a free tree. By [Theorem
A](../Text/ch02b.html#ch02b_the_a), a free tree contains $n-1$ wires,
and a graph with *n* vertices and $n-1$ edges is a free tree if and only
if it is connected.

**<span
id="ch02ex_3_1_11a">[11](../Text/ch02b.html#ch02ex_3_1_11)</span>.** It
is sufficient to prove that when $n\gt1$ and $c(n-1,n)$ is the minimum
of the $c(i,n)$, there exists at least one minimum cost tree in which
$T_{n-1}$ is wired to $T_n$. (For, any minimum cost tree with $n\gt1$
terminals and with $T_{n-1}$ wired to $T_n$ must also be a minimum cost
tree with $n-1$ terminals if we regard $T_{n-1}$ and $T_n$ as “common,”
using the convention stated in the algorithm.)

To prove the statement above, suppose we have a minimum cost tree in
which $T_{n-1}$ is not wired to $T_n$. If we add the wire
$T_{n-1}\;—\;T_n$ we obtain a cycle, and any of the other wires in that
cycle may be removed; removing the other wire touching $T_n$ gives us
another tree, whose total cost is not greater than the original, and
$T_{n-1}\;—\;T_n$ appears in that tree.

**<span
id="ch02ex_3_1_12a">[12](../Text/ch02b.html#ch02ex_3_1_12)</span>.**
Keep two auxiliary tables, $a(i)$ and $b(i)$, for $1\le i\lt n$,
representing the fact that the cheapest connection from $T_i$ to a
chosen terminal is to $T_{b(i)}$, and its cost is $a(i)$; initially
$a(i)=c(i,n)$ and $b(i)=n$. Then do the following operation $n-1$ times:
Find *i* such that $a(i)=min_{1\le j\lt n}a(j)$; connect $T_i$ to
$T_{b(i)}$; for $1\le j\lt n$ if $c(i,j)\lt a(j)$ set $a(j)\gets c(i,j)$
and $b(j)\gets i$; and set $a(i)\gets\infty$. Here $c(i,j)$ means
$c(j,i)$ when $j\lt i$.

(It is somewhat more efficient to avoid the use of ∞, keeping instead a
oneway linked list of those *j* that have not yet been chosen. With or
without this straightforward improvement, the algorithm takes $O(n^2)$
operations.) See also E. W. Dijkstra, *Proc. Nederl. Akad. Wetensch.*
**A63** (1960), 196–199; D. E. Knuth, *The Stanford GraphBase* (New
York: ACM Press, 1994), 460–497. Significantly better algorithms to find
a minimum-cost spanning tree are discussed in Section 7.5.4.

**<span
id="ch02ex_3_1_13a">[13](../Text/ch02b.html#ch02ex_3_1_13)</span>.** If
there is no path from $V_i$ to $V_j$, for some $i\neq j$, then no
product of the transpositions will move *i* to *j*. So if all
permutations are generated, the graph must be connected. Conversely if
it is connected, remove edges if necessary until we have a free tree.
Then renumber the vertices so that $V_n$ is adjacent to only one other
vertex, namely $V_{n-1}$. (See the proof of [Theorem
A](../Text/ch02b.html#ch02b_the_a).) Now the transpositions other than
$(n-1 n)$ form a free tree with $n-1$ vertices; so by induction if π is
any permutation of $\{1,2,\ldots,n\}$ that leaves *n* fixed, π can be
written as a product of those transpositions. If π moves *n* to *j* then
$\pi(j\;\;n\!\!-\!\!1)(n\!\!-\!\!1\;\;n)=\rho$ fixes *n*; hence
$\pi=\rho(n\!\!-\!\!1\;\;n)(j\;\;n\!\!-\!\!1)$ can be written as a
product of the given transpositions.

<div class="heading">

##### Section 2.3.4.2 {#app01lev3sec7}

**<span
id="ch02ex_3_2_1a">[1](../Text/ch02b.html#ch02ex_3_2_1)</span>.** Let
$(e_1,\ldots,e_n)$ be an oriented walk of smallest possible length from
*V* to $V'$. If now ${\rm init}(e_j)={\rm init}(e_k)$ for $j\lt k$,
$(e_1,\ldots,e_{j-1},e_k,\ldots,e_n)$ would be a shorter walk; a similar
argument applies if ${\rm fin}(e_j)={\rm fin}(e_k)$ for $j\lt k$. Hence
$(e_1,\ldots,e_n)$ is simple.

</div>

**<span
id="ch02ex_3_2_2a">[2](../Text/ch02b.html#ch02ex_3_2_2)</span>.** Those
cycles in which all signs are the same: $C_0$, $C_8$, $C''_{13}$,
$C_{17}$, $C''_{19}$, $C_{20}$.

**<span
id="ch02ex_3_2_3a">[3](../Text/ch02b.html#ch02ex_3_2_3)</span>.** For
example, use three vertices *A*, *B*, *C*, with arcs from *A* to *B* and
*A* to *C*.

**<span
id="ch02ex_3_2_4a">[4](../Text/ch02b.html#ch02ex_3_2_4)</span>.** If
there are no oriented cycles, [Algorithm
2.2.3T](../Text/ch02.html#ch02alg-lev2sec3-T) topologically sorts *G*.
If there is an oriented cycle, topological sorting is clearly
impossible. (Depending on how this exercise is interpreted, oriented
cycles of length 1 could be excluded from consideration.)

**<span
id="ch02ex_3_2_5a">[5](../Text/ch02b.html#ch02ex_3_2_5)</span>.** Let
*k* be the smallest integer such that ${\rm fin}(e_k)={\rm init}(e_j)$
for some $j\le k$. Then $(e_j,\ldots,e_k)$ is an oriented cycle.

**<span
id="ch02ex_3_2_6a">[6](../Text/ch02b.html#ch02ex_3_2_6)</span>.** False
(on a technicality), just because there may be several different arcs
from one vertex to another.

**<span
id="ch02ex_3_2_7a">[7](../Text/ch02b.html#ch02ex_3_2_7)</span>.** True
for finite directed graphs: If we start at any vertex *V* and follow the
only possible oriented path, we never encounter any vertex twice, so we
must eventually reach the vertex *R* (the only vertex with no
successor). For infinite directed graphs the result is obviously false
since we might have vertices *R*, $V_1,V_2,V_3,\ldots$ and arcs from
$V_j$ to $V_{j+1}$ for $j\ge1$.

**<span
id="ch02ex_3_2_9a">[9](../Text/ch02b.html#ch02ex_3_2_9)</span>.** All
arcs point upward.

<div class="image">

![Image](../Images/580fig01.gif)

</div>

**<span
id="ch02ex_3_2_10a">[10](../Text/ch02b.html#ch02ex_3_2_10)</span>.**
**G1.** Set $k\gets P[j]$, $P[j]\gets0$.

**G2.** If $k=0$, stop; otherwise set $m\gets P[k]$, $P[k]\gets j$,
$j\gets k$, $k\gets m$, and repeat step G2. <span
class="middle">![Image](../Images/box.gif)</span>

**<span
id="ch02ex_3_2_11a">[11](../Text/ch02b.html#ch02ex_3_2_11)</span>.**
This algorithm combines [Algorithm
2.3.3E](../Text/ch02a.html#ch02alg-lev2sec9-E) with the method of the
preceding exercise, so that all oriented trees have arcs that correspond
to actual arcs in the directed graph; $S[j]$ is an auxiliary table that
tells whether an arc goes from *j* to $P[j] (S[j]=+1)$ or from $P[j]$ to
$j (S[j]=-1)$. Initially $P[1]=\cdots=P[n]=0$. The following steps may
be used to process each arc $(a,b)$:

**C1.** Set $j\gets a$, $k\gets P[j]$, $P[j]\gets0$, $s\gets S[j]$.

**C2.** If $k=0$, go to C3; otherwise set $m\gets P[k]$, $t\gets S[k]$,
$P[k]\gets j$, $S[k]\gets-s$, $s\gets t$, $j\gets k$, $k\gets m$, and
repeat step C2.

**C3.** (Now *a* appears as the root of its tree.) Set $j\gets b$, and
then if $P[j]\neq0$ repeatedly set $j\gets P[j]$ until $P[j]=0$.

**C4.** If $j=a$, go to C5; otherwise set $P[a]\gets b$, $S[a]\gets+1$,
print $(a,b)$ as an arc belonging to the free subtree, and terminate.

**C5.** Print “$\tt CYCLE$” followed by “$(a,b)$”.

**C6.** If $P[b]=0$ terminate. Otherwise if $S[b]=+1$, print
“$+(b,P[b])$”, else print “$-(P[b],b)$”; set $b\gets P[b]$ and repeat
step C6. <span class="middle">![Image](../Images/box.gif)</span>

*Note:* This algorithm will take at most $O(m log n)$ steps if we
incorporate the suggestion of McIlroy in [answer
2.3.3–10](../Text/ch02b.html#ch02ex_2_9_10). But there is a much better
solution that needs only $O(m)$ steps: Use depth-first search to
construct a “palm tree,” with one fundamental cycle for each “frond” [R.
E. Tarjan, *SICOMP* **1** (1972), 146–150].

**<span
id="ch02ex_3_2_12a">[12](../Text/ch02b.html#ch02ex_3_2_12)</span>.** It
equals the in-degree; the out-degree of each vertex can be only 0 or 1.

**<span
id="ch02ex_3_2_13a">[13](../Text/ch02b.html#ch02ex_3_2_13)</span>.**
Define a sequence of oriented subtrees of *G* as follows: $G_0$ is the
vertex *R* alone. $G_{k+1}$ is $G_k$, plus any vertex *V* of *G* that is
not in $G_k$ but for which there is an arc from *V* to $V'$ where $V'$
*is* in $G_k$, plus one such arc $e[V]$ for each such vertex. It is
immediate by induction that $G_k$ is an oriented tree for all $k\ge0$,
and that if there is an oriented path of length *k* from *V* to *R* in
*G* then *V* is in $G_k$. Therefore $G_\infty$, the set of all *V* and
$e[V]$ in any of the $G_k$, is the desired oriented subtree of *G*.

**<span
id="ch02ex_3_2_14a">[14](../Text/ch02b.html#ch02ex_3_2_14)</span>.**
<span class="top">![Image](../Images/e581_01.gif)</span>

in lexicographic order; the eight possibilities come from the
independent choices of which of $e_{00}$ or <span
class="middle">![Image](../Images/e581_02.gif)</span>, $e_{10}$ or <span
class="middle">![Image](../Images/e581_03.gif)</span>, $e_{20}$ or
$e_{22}$, should precede the other.

**<span
id="ch02ex_3_2_15a">[15](../Text/ch02b.html#ch02ex_3_2_15)</span>.**
True for finite graphs: If it is connected and balanced and has more
than one vertex, it has an Eulerian trail that touches all the vertices.
(But false in general.)

**<span
id="ch02ex_3_2_16a">[16](../Text/ch02b.html#ch02ex_3_2_16)</span>.**
Consider the directed graph *G* with vertices $V_1,\ldots,V_{13}$ and
with an arc from $V_j$ to $V_k$ for each *k* in pile *j*; this graph is
balanced. Winning the game is equivalent to tracing out an Eulerian
trail in *G*, because the game ends when the fourth arc to $V_{13}$ is
encountered (namely, when the fourth king turns up). Now if the game is
won, the stated digraph is an oriented subtree by [Lemma
E](../Text/ch02b.html#ch02b_lem_E). Conversely if the stated digraph is
an oriented tree, the game is won by [Theorem
D](../Text/ch02b.html#ch02b_the_d).

**<span
id="ch02ex_3_2_17a">[17](../Text/ch02b.html#ch02ex_3_2_17)</span>.**
$\frac{1}{13}$. This answer can be obtained, as the author first
obtained it, by laborious enumeration of oriented trees of special types
and the application of generating functions, etc., based on the methods
of [Section 2.3.4.4](../Text/ch02b.html#ch02lev3sec4). But such a simple
answer deserves <span id="page_582"></span>a simple, direct proof, and
indeed there is one [see Tor B. Staver, *Norsk Matematisk Tidsskrift*
**28** (1946), 88–89]. Define an order for turning up *all* cards of the
deck, as follows: Obey the rules of the game until getting stuck, then
“cheat” by turning up the first available card (find the first pile that
is not empty, going clockwise from pile 1) and continue as before, until
eventually all cards have been turned up. The cards *in the order of
turning up* are in completely random order (since the value of a card
need not be specified until after it is turned up). So the problem is
just to calculate the probability that in a randomly shuffled deck the
last card is a king. More generally the probability that *k* cards are
still face down when the game is over is the probability that the last
king in a random shuffle is followed by *k* cards, namely <span
class="middle">![Image](../Images/e582_01.gif)</span>. Hence a person
playing this game without cheating will turn up an average of exactly
42.4 cards per game. *Note:* Similarly, it can be shown that the
probability that the player will have to “cheat” *k* times in the
process described above is exactly given by the Stirling number <span
class="middle">![Image](../Images/e582_02.gif)</span>. (See Eq.
[1.2.10](../Text/ch01a.html#ch01lev2sec10)–([9](../Text/ch01a.html#ch01eq-lev2sec10-9))
and [exercise 1.2.10–7](../Text/ch01a.html#ch01ex_2_10_7); the case of a
more general card deck is considered in [exercise
1.2.10–18](../Text/ch01a.html#ch01ex_2_10_18).)

**<span
id="ch02ex_3_2_18a">[18](../Text/ch02b.html#ch02ex_3_2_18)</span>.** (a)
If there is a cycle $(V_0,V_1,\ldots,V_k)$, where necessarily
$3\le k\le n$, the sum of the *k* rows of *A* corresponding to the *k*
edges of this cycle, with appropriate signs, is a row of zeros; so if
*G* is not a free tree the determinant of $A_0$ is zero.

But if *G* is a free tree we may regard it as an ordered tree with root
$V_0$, and we can rearrange the rows and columns of $A_0$ so that
columns are in preorder and so that the $kth$ row corresponds to the
edge from the $kth$ vertex (column) to its parent. Then the matrix is
triangular with $±1\rm\unicode{39}s$ on the diagonal, so the determinant
is $±1$.

\(b) By the Binet–Cauchy formula ([exercise
1.2.3–46](../Text/ch01.html#ch01ex_2_3_46)) we have

<div class="image">

![Image](../Images/e582_03.gif)

</div>

where $A_{i_1\ldots i_n}$ represents a matrix consisting of rows
$i_1,\ldots,i_n$ of $A_0$ (thus corresponding to a choice of *n* edges
of *G*). The result now follows from (a).

[See S. Okada and R. Onodera, *Bull. Yamagata Univ.* **2** (1952),
89–117.]

**<span
id="ch02ex_3_2_19a">[19](../Text/ch02b.html#ch02ex_3_2_19)</span>.** (a)
The conditions $a_{00}=0$ and $a_{jj}=1$ are just conditions (a), (b) of
the definition of oriented tree. If *G* is not an oriented tree there is
an oriented cycle (by [exercise 7](../Text/ch02b.html#ch02ex_3_2_7)),
and the rows of $A_0$ corresponding to the vertices in this oriented
cycle will sum to a row of zeros; hence $\det A_0=0$. If *G* is an
oriented tree, assign an arbitrary order to the children of each family
and regard *G* as an ordered tree. Now permute rows and columns of $A_0$
until they correspond to preorder of the vertices. Since the same
permutation has been applied to the rows as to the columns, the
determinant is unchanged; and the resulting matrix is triangular with
$+1$ in every diagonal position.

\(b) We may assume that $a_{0j}=0$ for all *j*, since no arc emanating
from $V_0$ can participate in an oriented subtree. We may also assume
that $a_{jj}\gt0$ for all $j\ge1$ since otherwise the whole $jth$ row is
zero and there obviously are no oriented subtrees. Now use induction on
the number of arcs: If $a_{jj}\gt1$ let *e* be some arc leading from
$V_j$; let $B_0$ be a matrix like $A_0$ but with arc *e* deleted, and
let $C_0$ be the matrix like $A_0$ but with all arcs *except e* that
lead from $V_j$ deleted. *Example:* If <span
class="middle">![Image](../Images/e582_04.gif)</span>, $j=1$, and *e* is
an arc from $V_1$ to $V_0$, then <span
class="middle">![Image](../Images/e582_05.gif)</span>, <span
class="middle">![Image](../Images/e582_06.gif)</span>. In general we
have $\det A_0=\det B_0+det C_0$, since the matrices agree in all rows
except row *j*, and $A_0$ is the sum of $B_0$ and $C_0$ in that row.
Moreover, the number of oriented subtrees of *G* is the number of
subtrees that do *not* use *e* (namely, $\det B_0$, by induction) plus
the number that *do* use *e* (namely, $\det C_0$).

*Notes:* The matrix *A* is often called the *Laplacian* of the graph, by
analogy with a similar concept in the theory of partial differential
equations. If we delete any set *S* of rows from the matrix *A*, and the
same set of columns, the determinant of the resulting matrix is the
number of oriented forests whose roots are the vertices
$\{V_k\mid k\in S\}$ and whose arcs belong to the given digraph. The
matrix tree theorem for oriented trees was stated without proof by J. J.
Sylvester in 1857 (see [exercise 28](../Text/ch02b.html#ch02ex_3_2_28)),
then forgotten for many years until it was independently rediscovered by
W. T. Tutte [*Proc. Cambridge Phil. Soc.* **44** (1948), 463–482, §3].
The first published proof in the special case of *undirected* graphs,
when the matrix *A* is symmetric, was given by C. W. Borchardt [*Crelle*
**57** (1860), 111–121]. Several authors have ascribed the theorem to
Kirchhoff, but Kirchhoff proved a quite different (though related)
result.

**<span
id="ch02ex_3_2_20a">[20](../Text/ch02b.html#ch02ex_3_2_20)</span>.**
Using [exercise 18](../Text/ch02b.html#ch02ex_3_2_18) we find
$B=A^T_0A_0$. Or, using [exercise 19](../Text/ch02b.html#ch02ex_3_2_19),
*B* is the matrix $A_0$ for the directed graph $G'$ with two arcs (one
in each direction) in place of each edge of *G*; each free subtree of
*G* corresponds uniquely to an oriented subtree of $G'$ with root $V_0$,
since the directions of the arcs are determined by the choice of root.

**<span
id="ch02ex_3_2_21a">[21](../Text/ch02b.html#ch02ex_3_2_21)</span>.**
Construct the matrices *A* and $A^*$ as in [exercise
19](../Text/ch02b.html#ch02ex_3_2_19). For the example graphs *G* and
$G^*$ in [Figs. 36](../Text/ch02b.html#ch02fig36) and
[37](../Text/ch02b.html#ch02fig37),

<div class="image">

![Image](../Images/e583_02.gif)

</div>

Add the indeterminate λ to every diagonal element of *A* and $A^*$. If
$t(G)$ and $t(G^*)$ are the numbers of oriented subtrees of *G* and
$G^*$, we then have $\det A=\lambda t(G)+O(\lambda^2)$,
$\det A^*=\lambda t(G^*)+O(\lambda^2)$. (The number of oriented subtrees
of a balanced graph is the same for any given root, by [exercise
22](../Text/ch02b.html#ch02ex_3_2_22), but we do not need that fact.)

If we group vertices $V_{jk}$ for equal *k* the matrix $A^*$ can be
partitioned as shown above. Let $B_{kk'}$ be the submatrix of $A^*$
consisting of the rows for $V_{jk}$ and the columns for $V_{j'k'}$, for
all *j* and $j'$ such that $V_{jk}$ and $V_{j'k'}$ are in $G^*$. By
adding the $2nd,\ldots,mth$ columns of each submatrix to the first
column and then subtracting the first row of each submatrix from the
$2nd,\ldots,mth$ rows, the matrix $A^*$ is transformed so that

<div class="image">

![Image](../Images/e583_03.gif)

</div>

The asterisks in the top rows of the transformed submatrices turn out to
be irrelevant, because the determinant of $A^*$ is now seen to be
$(\lambda+m)^{(m-1)n}$ times

<div class="image">

![Image](../Images/e583_04.gif)

</div>

Notice that when $n=1$ and there are *m* arcs from $V_0$ to itself, we
find in particular that exactly $m^{m-1}$ oriented trees are possible on
*m* labeled nodes. This result will be obtained by quite different
methods in [Section 2.3.4.4](../Text/ch02b.html#ch02lev3sec4).

This derivation can be generalized to determine the number of oriented
subtrees of $G^*$ when *G* is an *arbitrary* directed graph; see R.
Dawson and I. J. Good, *Ann. Math. Stat.* **28** (1957), 946–956; D. E.
Knuth, *Journal of Combinatorial Theory* **3** (1967), 309–314. An
alternative, purely combinatorial proof has been given by J. B. Orlin,
*Journal of Combinatorial Theory* **B25** (1978), 187–198.

**<span
id="ch02ex_3_2_22a">[22](../Text/ch02b.html#ch02ex_3_2_22)</span>.** The
total number is $(\sigma_1+\cdots+\sigma_n)$ times the number of
Eulerian trails starting with a given edge $e_1$, where
${\rm init}(e_1)=V_1$. Each such trail determines an oriented subtree
with root $V_1$ by [Lemma E](../Text/ch02b.html#ch02b_lem_E), and for
each of the *T* oriented subtrees there are <span
class="middle">![Image](../Images/584fig01.gif)</span> walks satisfying
the three conditions of [Theorem D](../Text/ch02b.html#ch02b_the_d),
corresponding to the different order in which the arcs
$\{e\mid{\rm init}(e)=V_j,e\neq e[V_j],e\neq e_1\}$ are entered into
*P*. ([Exercise 14](../Text/ch02b.html#ch02ex_3_2_14) provides a simple
example.)

**<span
id="ch02ex_3_2_23a">[23](../Text/ch02b.html#ch02ex_3_2_23)</span>.**
Construct the directed graph $G_k$ with $m^{k-1}$ vertices as in the
hint, and denote by $[x_1,\ldots,x_k]$ the arc mentioned there. For each
function that has maximum period length, we can define a unique
corresponding Eulerian trail, by letting $f(x_1,\ldots,x_k)=x_{k+1}$ if
arc $[x_1,\ldots,x_k]$ is followed by $[x_2,\ldots,x_{k+1}]$. (We regard
Eulerian trails as being the same if one is just a cyclic permutation of
the other.) Now $G_k=G^*_{k-1}$ in the sense of [exercise
21](../Text/ch02b.html#ch02ex_3_2_21), so $G_k$ has
$m^{m^{k-1}-m^{k-2}}$ times as many oriented subtrees as $G_{k-1}$; by
induction $G_k$ has $m^{m^{k-1}-1}$ oriented subtrees, and
$m^{m^{k-1}-k}$ with a given root. Therefore by [exercise
22](../Text/ch02b.html#ch02ex_3_2_22) the number of functions with
maximum period, namely the number of Eulerian trails of $G_k$ starting
with a given arc, is $m^{-k}(m!)^{m^{k-1}}$. [For $m=2$ this result is
due to C. Flye Sainte-Marie, L’*Intermédiaire des Mathématiciens* 1
(1894), 107–110.]

**<span
id="ch02ex_3_2_24a">[24](../Text/ch02b.html#ch02ex_3_2_24)</span>.**
Define a new directed graph having $E_j$ copies of $e_j$, for
$0\le j\le m$. This graph is balanced, hence it contains an Eulerian
trail $(e_0,\ldots)$ by [Theorem G](../Text/ch02b.html#ch02b_the_g). The
desired oriented walk comes by deleting the edge $e_0$ from this
Eulerian trail.

**<span
id="ch02ex_3_2_25a">[25](../Text/ch02b.html#ch02ex_3_2_25)</span>.**
Assign an arbitrary order to all arcs in the sets
$I_j=\{e\mid{\rm init}(e)=V_j\}$ and $F_j=\{e\mid{\rm fin}(e)=V_j\}$.
For each arc *e* in $I_j$, let ${\tt ATAG}(e)=0$ and ${\tt ALINK}(e)=e'$
if $e'$ follows *e* in the ordering of $I_j$; also let ${\tt ATAG(e)}=1$
and ${\tt ALINK}(e)=e'$ if *e* is last in $I_j$ and $e'$ is first in
$F_j$. Let ${\tt ALINK}(e)=\varLambda$ in the latter case if $F_j$ is
empty. Define $\tt BLINK$ and $\tt BTAG$ by the same rules, reversing
the roles of init and fin.

*Examples* (using alphabetic order in each set of arcs):

<div class="image">

![Image](../Images/e584_02.gif)

</div>

*Note:* If in the oriented tree representation we add another arc from
*H* to itself, we get an interesting situation: Either we get the
standard conventions
[2.3.1](../Text/ch02a.html#ch02lev2sec7)–([8](../Text/ch02a.html#ch02eq-lev2sec7-8))
with $\tt LLINK$, $\tt LTAG$, $\tt RLINK$, $\tt RTAG$ *interchanged* in
the list head, or (if the new arc is placed last in the ordering) we get
the standard conventions except ${\tt RTAG}=0$ in the node associated
with the root of the tree.

This exercise is based on an idea communicated to the author by W. C.
Lynch. Can tree traversal algorithms like [Algorithm
2.3.1S](../Text/ch02a.html#ch02alg-lev2sec6-S) be generalized to classes
of digraphs that are not oriented trees, using such a representation?

**<span
id="ch02ex_3_2_27a">[27](../Text/ch02b.html#ch02ex_3_2_27)</span>.** Let
$a_{ij}$ be the sum of $p(e)$ over all arcs *e* from $V_i$ to $V_j$. We
are to prove that $t_j=\sum_ia_{ij}t_i$ for all *j*. Since
$\sum_ia_{ji}=1$, we must prove that $\sum_ia_{ji}t_j=\sum_ia_{ij}t_i$.
But this is not difficult, because both sides of the equation represent
the sum of all products $p(e_1)\ldots p(e_n)$ taken over subgraphs
$\{e_1,\ldots,e_n\}$ of *G* such that ${\rm init}(e_i)=V_i$ and such
that there is a unique oriented cycle contained in $\{e_1,\ldots,e_n\}$,
where this cycle includes $V_j$. Removing any arc of the cycle yields an
oriented tree; the left-hand side of the equation is obtained by
factoring out the arcs that leave $V_j$, while the right-hand side
corresponds to those that enter $V_j$.

In a sense, this exercise is a combination of [exercises
19](../Text/ch02b.html#ch02ex_3_2_19) and
[26](../Text/ch02b.html#ch02ex_3_2_26).

**<span
id="ch02ex_3_2_28a">[28](../Text/ch02b.html#ch02ex_3_2_28)</span>.**
Every term in the expansion is
$a_{1p_1}\ldots a_{mp_m}b_{1q_1}\ldots b_{nq_n}$, where $0\le p_i\le n$
for $1\le i\le m$ and $0\le q_j\le m$ for $1\le j\le n$, times some
integer coefficient. Represent this product as a directed graph on the
vertices $\{0,u_1,\ldots,u_m,v_1,\ldots,v_n\}$, with arcs from $u_i$ to
$v_{pi}$ and from $v_j$ to $u_{qj}$, where $u_0=v_0=0$.

If the digraph contains a cycle, the integer coefficient is zero. For
each cycle corresponds to a factor of the form

![Image](../Images/e585_01.gif)

where the indices $(i_0,i_1,\ldots,i_{k-1})$ are distinct and so are the
indices $(j_0,j_1,\ldots,j_{k-1})$. The sum of all terms containing
$(*)$ as a factor is $(*)$ times the determinant obtained by setting
$a_{i_lj}\gets [j=j_l]$ for $0\le j\le n$ and
$b_{j_li}\gets [i=i_{(l+1)\bmod k}]$ for $0\le i\le m$, for
$0\le l\lt k$, leaving the variables in the other $m+n-2k$ rows
unchanged. This determinant is identically zero, because the sum of rows
$i_0,i_1,\ldots,i_{k-1}$ in the top section equals the sum of rows
$j_0,j_1,\ldots,j_{k-1}$ in the bottom section.

On the other hand, if the directed graph contains no cycles, the integer
coefficient is $+1$. This follows because each factor $a_{ip_i}$ and
$b_{jq_j}$ must have come from the diagonal of the determinant: If any
off-diagonal element $a_{i_0j_0}$ is chosen in row $i_0$ of the top
section, we must choose some off-diagonal $b_{j_0i_1}$ from row $j_0$ of
the bottom section, hence we must choose some off-diagonal $a_{i_1j_1}$
from row $i_1$ of the top section, etc., forcing a cycle.

Thus the coefficient is $+1$ if and only if the corresponding digraph is
an oriented tree with root 0. The number of such terms (hence the number
of such oriented trees) is obtained by setting each $a_{ij}$ and
$b_{ji}$ to 1; for example,

<div class="image">

![Image](../Images/e585_02.gif)

</div>

In general we obtain det<span
class="middle">![Image](../Images/e585_03.gif)</span>.

*Notes:* J. J. Sylvester considered the special case $m=n$ and
$a_{10}=a_{20}=\cdots=a_{m0}=0$ in *Quarterly J. of Pure and Applied
Math.* **1** (1857), 42–56, where he conjectured (correctly) that the
total number of terms is then $n^n(n+1)^{n-1}$. He also stated without
proof that the $(n+1)^{n-1}$ nonzero terms present when
$a_{ij}=\delta_{ij}$ correspond to all connected cycle-free graphs on
$\{0,1,\ldots,n\}$. In that special case, he reduced the determinant to
the form in the matrix tree theorem of [exercise
19](../Text/ch02b.html#ch02ex_3_2_19), e.g.,

<div class="image">

![Image](../Images/e586_01.gif)

</div>

Cayley quoted this result in *Crelle* **52** (1856), 279, ascribing it
to Sylvester; thus it is ironic that the theorem about the number of
such graphs is often attributed to Cayley.

By negating the first *m* rows of the given determinant, then negating
the first *m* columns, we can reduce this exercise to the matrix tree
theorem.

[Matrices having the general form considered in this exercise are
important in iterative methods for the solution of partial differential
equations, and they are said to have “Property *A*.” See, for example,
Louis A. Hageman and David M. Young, *Applied Iterative Methods*
(Academic Press, 1981), Chapter 9.]

<div class="heading">

##### Section 2.3.4.3 {#app01lev3sec8}

**<span
id="ch02ex_3_3_1a">[1](../Text/ch02b.html#ch02ex_3_3_1)</span>.** The
root is the empty sequence; arcs go from $(x_1,\ldots,x_n)$ to
$(x_1,\ldots,x_{n-1})$.

</div>

**<span
id="ch02ex_3_3_2a">[2](../Text/ch02b.html#ch02ex_3_3_2)</span>.** Take
one tetrad type and rotate it $180^\circ$ to get another tetrad type;
these two types clearly tile the plane (without further rotations), by
repeating a $2\times2$ pattern.

**<span
id="ch02ex_3_3_3a">[3](../Text/ch02b.html#ch02ex_3_3_3)</span>.**
Consider the set of tetrad types <span
class="baseline">![Image](../Images/e586_02.gif)</span> for all positive
integers *j*. The right half plane can be tiled in uncountably many
ways; but whatever square is placed in the center of the plane puts a
finite limit on the distance it can be continued to the left.

**<span
id="ch02ex_3_3_4a">[4](../Text/ch02b.html#ch02ex_3_3_4)</span>.**
Systematically enumerate all possible ways to tile an $n\times n$ block,
for $n=1,2,\ldots$, looking for toroidal solutions within these blocks.
If there is no way to tile the plane, the infinity lemma tells us there
is an *n* with no $n\times n$ solutions. If there *is* a way to tile the
plane, the assumption tells us that there is an *n* with an $n\times n$
solution containing a rectangle that yields a toroidal solution. Hence
in either case the algorithm will terminate.

[But the stated assumption is false, as shown in the next exercise; and
in fact there is no algorithm that will determine in a finite number of
steps whether or not there exists a way to tile the plane with a given
set of types. On the other hand, if such a tiling does exist, there is
always a tiling that is *quasitoroidal*, in the sense that each of its
$n\times n$ blocks occurs at least once in every $f(n)\times f(n)$
block, for some function *f*. See B. Durand, *Theoretical Computer
Science* **221** (1999), 61–75.]

**<span
id="ch02ex_3_3_5a">[5](../Text/ch02b.html#ch02ex_3_3_5)</span>.** Start
by noticing that we need classes $\matrix{\alpha&\beta\cr\gamma&\delta}$
replicated in $2\times2$ groups in any solution. Then, step 1:
Considering just the *α* squares, show that the pattern
$\matrix{a&b\cr c&d}$ must be replicated in $2\times2$ groups of *α*
squares. Step $n\gt1$: Determine a pattern that must appear in a
cross-shaped region of height and width $2^n-1$. The middle of the
crosses has the pattern $\matrix{Na&Nb\cr Nc&Nd}$ replicated throughout
the plane.

For example, after step 3 we will know the contents of $7\times7$ blocks
throughout the plane, separated by unit length strips, every eight
units. The $7\times7$ blocks that are of <span
id="page_587"></span>class $Na$ in the center have the form

<div class="image">

![Image](../Images/e587_01.gif)

</div>

The middle column and the middle row is the “cross” just filled in
during step 3; the other four $3\times3$ squares were filled in after
step 2; the squares just to the right and below this $7\times7$ square
are part of a $15\times15$ cross to be filled in at step 4.

For a similar construction that leads to a set of only 35 tetrad types
having nothing but nontoroidal solutions, see R. M. Robinson,
*Inventiones Math.* **12** (1971), 177–209. Robinson also exhibits a set
of *six* squarish shapes that tile the plane only nontoroidally, even
when rotations and reflections are allowed. In 1974, Roger Penrose
discovered a set of only *two* polygons, based on the golden ratio
instead of a square grid, that tile the plane only aperiodically; this
led to a set of only 16 tetrad types with only nontoroidal solutions
[see B. Grünbaum and G. C. Shephard, *Tilings and Patterns* (Freeman,
1987), Chapters 10–11; Martin Gardner, *Penrose Tiles to Trapdoor
Ciphers* (Freeman, 1989), [Chapters
1](../Text/ch01.html#ch01)–[2](../Text/ch02.html#ch02)].

**<span
id="ch02ex_3_3_6a">[6](../Text/ch02b.html#ch02ex_3_3_6)</span>.** Let
*k* and *m* be fixed. Consider an oriented tree whose vertices each
represent, for some *n*, one of the partitions of $\{1,\ldots,n\}$ into
*k* parts, containing no arithmetic progression of length *m*. A node
that partitions $\{1,\ldots,n+1\}$ is a child of one for
$\{1,\ldots,n\}$ if the two partitions agree on $\{1,\ldots,n\}$. If
there were an infinite path to the root we would have a way to divide
*all* integers into *k* sets with no arithmetic progression of length
*m*. Hence, by the infinity lemma and van der Waerden’s theorem, this
tree is finite. (If $k=2$, $m=3$, the tree can be rapidly calculated by
hand, and the least value of *N* is 9. See *Studies in Pure
Mathematics*, ed. by L. Mirsky (Academic Press, 1971), 251–260, for van
der Waerden’s interesting account of how the proof of his theorem was
discovered.)

**<span
id="ch02ex_3_3_7a">[7](../Text/ch02b.html#ch02ex_3_3_7)</span>.** The
positive integers can be partitioned into two sets $S_0$ and $S_1$ such
that neither set contains any infinite *computable* sequence (see
exercise 3.5–32). So in particular there is no infinite arithmetic
progression. [Theorem K](../Text/ch02b.html#ch02theor-k) does not apply
because there is no way to put partial solutions into a tree with finite
degrees at each vertex.

**<span
id="ch02ex_3_3_8a">[8](../Text/ch02b.html#ch02ex_3_3_8)</span>.** Let a
“counterexample sequence” be an infinite sequence of trees that violates
Kruskal’s theorem, if such sequences exist. Assume that the theorem is
false; then let $T_1$ be a tree with the smallest possible number of
nodes such that $T_1$ can be the first tree in a counterexample
sequence; if $T_1,\ldots,T_j$ have been chosen, let $T_{j+1}$ be a tree
with the smallest possible number of nodes such that
$T_1,\ldots,T_j,T_{j+1}$ is the beginning of a counterexample sequence.
This process defines a counterexample sequence $\langle T_n\rangle$.
None of these $T\rm\unicode{39}s$ is just a root. Now, we look at this
sequence very carefully:

\(a) Suppose there is a subsequence $T_{n_1},T_{n_2},\ldots$ for which
$l(T_{n_1}),l(T_{n_2}),\ldots$ is a counterexample sequence. This is
impossible; otherwise
$T_1,\ldots,T_{n_1-1},l(T_{n_1}),l(T_{n_2}),\ldots$ would be a
counterexample sequence, contradicting the definition of $T_{n_1}$.

\(b) Because of (a), there are only finitely many *j* for which $l(T_j)$
cannot be embedded in $l(T_k)$ for any $k\gt j$. Therefore by taking
$n_1$ larger than any such *j* we can find a subsequence for which
$l(T_{n_1})\subseteq l(T_{n_2})\subseteq l(T_{n_3})\subseteq\cdots$.

\(c) Now by the result of [exercise
2.3.2–22](../Text/ch02a.html#ch02ex_2_8_22), $r(T_{n_j})$ cannot be
embedded in $r(T_{n_k})$ for any $k\gt j$, else
$T_{n_j}\subseteq T_{n_k}$. Therefore
$T_1,\ldots,T_{n_1-1},r(T_{n_1}),r(T_{n_2}),\ldots$ is a counterexample
sequence. But this contradicts the definition of $T_{n_1}$.

*Notes:* Kruskal, in *Trans. Amer. Math. Soc.* **95** (1960), 210–225,
actually proved a stronger result, using a weaker notion of embedding.
His theorem does not follow directly from the infinity lemma, although
the results are vaguely similar. Indeed, K<span
class="baseline">![Image](../Images/oprime.gif)</span>nig himself proved
a special case of Kruskal’s theorem, showing that there is no infinite
sequence of pairwise incomparable $n\unicode{45}\rm tuples$ of
nonnegative integers, where comparability means that all components of
one $n\unicode{45}\rm tuple$ are\\le the corresponding components of the
other [*Matematikai és Fizikai Lapok* **39** (1932), 27–29]. For further
developments, see *J. Combinatorial Theory* **A13** (1972), 297–305. See
also N. Dershowitz, *Inf. Proc. Letters* **9** (1979), 212–215, for
applications to termination of algorithms.

<div class="heading">

##### Section 2.3.4.4 {#app01lev3sec9}

**<span
id="ch02ex_3_4_1a">[1](../Text/ch02b.html#ch02ex_3_4_1)</span>.**
$\ln A(z)=\ln z+\sum_{k\ge1}a_k\ln\left(\frac1{1-z^k}\right)=\ln z+\sum_{k,t\ge1}\frac{a_kz^{kt}}t=\ln z+\sum_{t\ge1}\frac{A(z^t)}t$

</div>

**<span
id="ch02ex_3_4_2a">[2](../Text/ch02b.html#ch02ex_3_4_2)</span>.** By
differentiation, and equating the coefficients of $z^n$, we obtain the
identity

<div class="image">

![Image](../Images/e588_02.gif)

</div>

Now interchange the order of summation.

**<span
id="ch02ex_3_4_4a">[4](../Text/ch02b.html#ch02ex_3_4_4)</span>.** (a)
$A(z)$ certainly converges at least for $|z|\lt\frac14$, since $a_n$ is
less than the number of *ordered* trees $b_{n-1}$. Since $A(1)$ is
infinite and all coefficients are positive, there is a positive number
$\alpha\le1$ such that $A(z)$ converges for $|z|\lt\alpha$, and there is
a singularity at $z=\alpha$. Let $\psi(z)=A(z)/z$; since
$\psi(z)\gt e^{z\psi(z)}$, we see that $\psi(z)=m$ implies
$z\lt\ln m/m$, so $\psi(z)$ is bounded and $\lim_{z\to\alpha-}\psi(z)$
exists. Thus $\alpha\lt1$, and by Abel’s limit theorem
$a=\alpha\cdot\exp\left(a+\frac12 A(\alpha^2)+\frac13 A(\alpha^3)+\cdots\right)$.

\(b) $A(z^2),A(z^3),\ldots$ are analytic for $|z|\lt\sqrt\alpha$, and
$\frac12 A(z^2)+\frac13 A(z^3)+\cdots$ converges uniformly in a slightly
smaller disk.

\(c) If $\partial F/\partial w=a-1\neq0$, the implicit function theorem
implies that there is an analytic function $f(z)$ in a neighborhood of
$(\alpha,a/\alpha)$ such that $F(z,f(z))=0$. But this implies
$f(z)=A(z)/z$, contradicting the fact that $A(z)$ is singular at *α*.

\(d) Obvious.

\(e) $\partial F/\partial w=A(z)-1$ and $|A(z)|\lt A(\alpha)=1$, since
the coefficients of $A(z)$ are all positive. Hence, as in (c), $A(z)$ is
regular at all such points.

\(f) Near $(\alpha,1/\alpha)$ we have the identity
$0=\beta(z-\alpha)+(\alpha/2)(w-1/\alpha)^2+\mathrm{higher order terms}$,
where $w=A(z)/z$; so *w* is an analytic function of $\sqrt{z-\alpha}$
here by the implicit function theorem. Consequently there is a region
$|z|\lt\alpha_1$ minus a cut $[\alpha,\alpha_1]$ in which $A(z)$ has the
stated form. (The minus sign is chosen since a plus sign would make the
coefficients ultimately negative.)

\(g) Any function of the stated form has coefficient asymptotically <span
class="middle">![Image](../Images/e588_08.gif)</span>.

Note that

<div class="image">

![Image](../Images/e588_09.gif)

</div>

For further details, and asymptotic values of the number of free trees,
see R. Otter, *Ann. Math.* (2) **49** (1948), 583–599.

**<span
id="ch02ex_3_4_5a">[5](../Text/ch02b.html#ch02ex_3_4_5)</span>.**

<div class="image">

![Image](../Images/e589_01.gif)

</div>

Therefore

<div class="image">

![Image](../Images/e589_02.gif)

</div>

We find $C(z)=z+z^2+2z^3+5z^4+12z^5+33z^6+90z^7+261z^8+766z^9+\cdots$.
When $n\gt1$, the number of series-parallel networks with *n* edges is
$2c_n$ [see P. A. MacMahon, *Proc. London Math. Soc.* **22** (1891),
330–339].

**<span
id="ch02ex_3_4_6a">[6](../Text/ch02b.html#ch02ex_3_4_6)</span>.**
$zG(z)^2=2G(z)-2-zG(z^2)$;
$G(z)=1+z+z^2+2z^3+3z^4+6z^5+11z^6+23z^7+46z^8+98z^9+\cdots$. The
function $F(z)=1-zG(z)$ satisfies the simpler relation
$F(z^2)=2z+F(z)^2$. [J. H. M. Wedderburn, *Annals of Math.* (2) **24**
(1922), 121–140.]

**<span
id="ch02ex_3_4_7a">[7](../Text/ch02b.html#ch02ex_3_4_7)</span>.**
$g_n=ca^nn^{-3/2}(1+O(1/n))$, where $c\approx0.7916031835775$,
$a\approx2.483253536173$.

**<span
id="ch02ex_3_4_8a">[8](../Text/ch02b.html#ch02ex_3_4_8)</span>.**

<div class="image">

![Image](../Images/589fig01.gif)

</div>

**<span
id="ch02ex_3_4_9a">[9](../Text/ch02b.html#ch02ex_3_4_9)</span>.** If
there are two centroids, by considering a path from one to the other we
find that there can’t be intermediate points, so any two centroids are
adjacent. A tree cannot contain three mutually adjacent vertices, so
there are at most two.

**<span
id="ch02ex_3_4_10a">[10](../Text/ch02b.html#ch02ex_3_4_10)</span>.** If
*X* and *Y* are adjacent, let $s(X,Y)$ be the number of vertices in the
*Y* subtree of *X*. Then $s(X,Y)+s(Y,X)=n$. The argument in the text
shows that if *Y* is a centroid, $weight(X)=s(X,Y)$. Therefore if both
*X* and *Y* are centroids, $weight(X)=weight(Y)=n/2$.

In terms of this notation, the argument in the text goes on to show that
if $s(X,Y)\ge s(Y,X)$, there is a centroid in the *Y* subtree of *X*. So
if two free trees with *m* vertices are joined by an edge between *X*
and *Y*, we obtain a free tree in which $s(X,Y)=m=s(Y,X)$, and there
must be two centroids (namely *X* and *Y*).

[It is a nice programming exercise to compute $s(X,Y)$ for all adjacent
*X* and *Y* in $O(n)$ steps; from this information we can quickly find
the centroid(s). An efficient algorithm for centroid location was first
given by A. J. Goldman, *Transportation Sci.* **5** (1971), 212–221.]

**<span
id="ch02ex_3_4_11a">[11](../Text/ch02b.html#ch02ex_3_4_11)</span>.**
$zT(z)^t=T(z)-1$; thus $z+T(z)^{-t}=T(z)^{1-t}$. By Eq.
[1.2.9](../Text/ch01a.html#ch01lev2sec9)–([21](../Text/ch01a.html#ch01eq-lev2sec9-21)),
$T(z)=\sum_nA_n(1,-t)z^n$, so the number of $t\unicode{45}\rm ary$ trees
is

<div class="image">

![Image](../Images/e589_04.gif)

</div>

**<span
id="ch02ex_3_4_12a">[12](../Text/ch02b.html#ch02ex_3_4_12)</span>.**
Consider the directed graph that has one arc from $V_i$ to $V_j$ for all
$i\neq j$. The matrix $A_0$ of [exercise
2.3.4.2–19](../Text/ch02b.html#ch02ex_3_2_19) is a combinatorial
$(n-1)\times(n-1)$ matrix with $n-1$ on the diagonal and $-1$ off the
diagonal. So its determinant is

$(n+(n-1)(-1))n^{n-2}=n^{n-2}$,

the number of oriented trees with a given root. ([Exercise
2.3.4.2–20](../Text/ch02b.html#ch02ex_3_4_20) could also be used.)

**<span
id="ch02ex_3_4_13a">[13](../Text/ch02b.html#ch02ex_3_4_13)</span>.**

<div class="image">

![Image](../Images/590fig01.gif)

</div>

**<span
id="ch02ex_3_4_14a">[14](../Text/ch02b.html#ch02ex_3_4_14)</span>.**
True, since the root will not become a leaf until all other branches
have been removed.

**<span
id="ch02ex_3_4_15a">[15](../Text/ch02b.html#ch02ex_3_4_15)</span>.** In
the canonical representation, $V_1,V_2,\ldots,V_{n-1},f(V_{n-1})$ is a
topological sort of the oriented tree considered as a directed graph,
but this order would not in general be output by [Algorithm
2.2.3T](../Text/ch02.html#ch02alg-lev2sec3-T). [Algorithm
2.2.3T](../Text/ch02.html#ch02alg-lev2sec3-T) can be changed so that it
determines the values of $V_1,V_2,\ldots,V_{n-1}$ if the “insert into
queue” operation of step T6 is replaced by a procedure that adjusts
links so that the entries of the list appear in ascending order from
front to rear; then the queue becomes a priority queue.

(However, a general priority queue isn’t needed to find the canonical
representation; we only need to sweep through the vertices from 1 to
*n*, looking for leaves, while pruning off paths from new leaves less
than the sweep pointer; see the following exercise.)

**<span
id="ch02ex_3_4_16a">[16](../Text/ch02b.html#ch02ex_3_4_16)</span>.**
**D1.** Set ${\tt C[}1{\tt]}\gets\cdots\gets{\tt C[}n{\tt]}\gets0$, then
set ${\tt C[}f(V_j){\tt]\gets C[}f(V_j){\tt]}+1$ for $1\le j\lt n$.
(Thus vertex *k* is a leaf if and only if ${\tt C[}k{\tt]}=0$.) Set
$k\gets0$ and $j\gets1$.

**D2.** Increase *k* one or more times until ${\tt C[}k{\tt]}=0$, then
set $l\gets k$.

**D3.** Set ${\tt PARENT[}l{\tt]}\gets f(V_j)$, $l\gets f(V_j)$,
${\tt C[}l{\tt]\gets C[}l{\tt]}-1$, and $j\gets j+1$.

**D4.** If $j=n$, set ${\tt PARENT[}l{\tt]}\gets0$ and terminate the
algorithm.

**D5.** If ${\tt C[}l{\tt]}=0$ and $l\lt k$, go to D3; otherwise go back
to D2. <span class="middle">![Image](../Images/box.gif)</span>

**<span
id="ch02ex_3_4_17a">[17](../Text/ch02b.html#ch02ex_3_4_17)</span>.**
There must be exactly one cycle $x_1,x_2,\ldots,x_k$ where
$f(x_j)=x_{j+1}$ and $f(x_k)=x_1$. We will enumerate all *f* having a
cycle of length *k* such that the iterates of each *x* ultimately come
into this cycle. Define the canonical representation
$f(V_1),f(V_2),\ldots,f(V_{m-k})$ as in the text; now $f(V_{m-k})$ is in
the cycle, so we continue to get a “canonical representation” by writing
down the rest of the cycle $f(f(V_{m-k}))$, $f(f(f(V_{m-k})))$, etc. For
example, the function with $m=13$ whose graph is shown here leads to the
representation 3, 1, 8, 8, 1, 12, 12, 2, 3, 4, 5, 1. We obtain a
sequence of $m-1$ numbers in which the last *k* are distinct.
Conversely, from any such sequence we can reverse the construction
(assuming that *k* is known); hence there are precisely
$m^{\underline{k}}m^{m-k-1}$ such functions having a
$k\unicode{45}\rm cycle$. (For related results, see exercise 3.1–14. The
formula $m^{m-1}Q(m)$ was first obtained by L. Katz, *Annals of Math.
Statistics* **26** (1955), 512–517.)

<div class="image">

![Image](../Images/590fig02.gif)

</div>

**<span
id="ch02ex_3_4_18a">[18](../Text/ch02b.html#ch02ex_3_4_18)</span>.** To
reconstruct the tree from a sequence $s_1,s_2,\ldots,s_{n-1}$, begin
with $s_1$ as the root and successively attach arcs to the tree that
point to $s_1,s_2,\ldots$; if vertex $s_k$ has appeared earlier, leave
the initial vertex of the arc leading to $s_{k-1}$ nameless, otherwise
give this vertex the name $s_k$. After all $n-1$ arcs have been placed,
give names to all vertices that remain nameless by using the numbers
that have not yet appeared, assigning names in increasing order to
nameless vertices in the order of their creation.

For example, from 3, 1, 4, 1, 5, 9, 2, 6, 5 we would construct the tree
shown on the right. There is no simple connection between this method
and the one in the text. Several more representations are possible; see
the article by E. H. Neville, *Proc. Cambridge Phil. Soc.* **49**
(1953), 381–385.

<div class="image">

![Image](../Images/591fig01.gif)

</div>

**<span
id="ch02ex_3_4_19a">[19](../Text/ch02b.html#ch02ex_3_4_19)</span>.** The
canonical representation will have precisely $n-k$ different values, so
we enumerate the sequences of $n-1$ numbers with this property. The
answer is <span class="middle">![Image](../Images/e591_01.gif)</span>.

**<span
id="ch02ex_3_4_20a">[20](../Text/ch02b.html#ch02ex_3_4_20)</span>.**
Consider the canonical representation of such trees. We are asking how
many terms of $(x_1+\cdots+x_n)^{n-1}$ have $k_0$ exponents zero, $k_1$
exponents one, etc. This is plainly the coefficient of such a term times
the number of such terms, namely

<div class="image">

![Image](../Images/e591_02.gif)

</div>

**<span
id="ch02ex_3_4_21a">[21](../Text/ch02b.html#ch02ex_3_4_21)</span>.**
There are none with $2m$ vertices; if there are $n=2m+1$ vertices, the
answer is obtained from [exercise 20](../Text/ch02b.html#ch02ex_3_4_20)
with $k_0=m+1,k_2=m$, namely <span
class="middle">![Image](../Images/e591_03.gif)</span>.

**<span
id="ch02ex_3_4_22a">[22](../Text/ch02b.html#ch02ex_3_4_22)</span>.**
Exactly $n^{n-2}$; for if *X* is a particular vertex, the free trees are
in one-to-one correspondence with oriented trees having root *X*.

**<span
id="ch02ex_3_4_23a">[23](../Text/ch02b.html#ch02ex_3_4_23)</span>.** It
is possible to put the labels on every unlabeled, ordered tree in $n!$
ways, and each of these labeled, ordered trees is distinct. So the total
number is $n!b_{n-1}=(2n-2)!/(n-1)!$.

**<span
id="ch02ex_3_4_24a">[24](../Text/ch02b.html#ch02ex_3_4_24)</span>.**
There are as many with one given root as with another, so the answer in
general is $1/n$ times the answer in [exercise
23](../Text/ch02b.html#ch02ex_3_4_23); and in this particular case the
answer is 30.

**<span
id="ch02ex_3_4_25a">[25](../Text/ch02b.html#ch02ex_3_4_25)</span>.** For
$0\le q\lt n$, $r(n,q)=(n-q)n^{q-1}$. (The special case $s=1$ in Eq.
([24](../Text/ch02b.html#ch02eq-lev3sec4-24)).)

**<span
id="ch02ex_3_4_26a">[26](../Text/ch02b.html#ch02ex_3_4_26)</span>.**
$(k=7)$

<div class="image">

![Image](../Images/591fig02.gif)

</div>

**<span
id="ch02ex_3_4_27a">[27](../Text/ch02b.html#ch02ex_3_4_27)</span>.**
Given a function *g* from $\{1,2,\ldots,r\}$ to $\{1,2,\ldots,q\}$ such
that adding arcs from $V_k$ to $U_{g(k)}$ introduces no oriented cycles,
construct a sequence $a_1,\ldots,a_r$ as follows: Call vertex $V_k$
“free” if there is no oriented path from $V_j$ to $V_k$ for any
$j\neq k$. Since there are no oriented cycles, there must be at least
one free vertex. Let $b_1$ be the smallest integer for which $V_{b_1}$
is free; and assuming that $b_1,\ldots,b_t$ have been chosen, let
$b_{t+1}$ be the smallest integer different from $b_1,\ldots,b_t$ for
which $V_{b_{t+1}}$ is free in the graph obtained by deleting the arcs
from $V_{b_k}$ to $U_{g(b_k)}$ for $1\le k\le t$. This rule defines a
permutation $b_1b_2\ldots b_r$ of the integers $\{1,2,\ldots,r\}$. Let
$a_k=g(b_k)$ for $1\le k\le r$; this defines a sequence such that
$1\le a_k\le q$ for $1\le k\lt r$, and $1\le a_r\le p$.

Conversely if such a sequence $a_1,\ldots,a_r$ is given, call a vertex
$V_k$ “free” if there is no *j* for which $a_j\gt p$ and $f(a_j)=k$.
Since $a_r\le p$ there are at most $r-1$ non-free vertices. Let $b_1$ be
the smallest integer for which $V_{b_1}$ is free; and assuming that
$b_1,\ldots,b_t$ have been chosen, let $b_{t+1}$ be the smallest integer
different from $b_1,\ldots,b_t$ for which $V_{b_{t+1}}$ is free with
respect to the sequence $a_{t+1},\ldots,a_r$. This rule defines a
permutation $b_1b_2\ldots b_r$ of the integers $\{1,2,\ldots,r\}$. Let
$g(b_k)=a_k$ for $1\le k\le r$; this defines a function such that adding
arcs from $V_k$ to $U_{g(k)}$ introduces no oriented cycles.

**<span
id="ch02ex_3_4_28a">[28](../Text/ch02b.html#ch02ex_3_4_28)</span>.** Let
*f* be any of the $n^{m-1}$ functions from $\{2,\ldots,m\}$ to
$\{1,2,\ldots,n\}$, and consider the directed graph with vertices
$U_1,\ldots,U_m,V_1,\ldots,V_n$ and arcs from $U_k$ to $V_{f(k)}$ for
$1\lt k\le m$. Apply [exercise 27](../Text/ch02b.html#ch02ex_3_4_27)
with $p=1$, $q=m$, $r=n$, to show that there are $m^{n-1}$ ways to add
further arcs from the $V\unicode{39}\rm s$ to the $U\unicode{39}\rm s$
to obtain an oriented tree with root $U_1$. Since there is a one-to-one
correspondence between the desired set of free trees and the set of
oriented trees with root $U_1$, the answer is $n^{m-1}m^{n-1}$. [This
construction can be extensively generalized; see D. E. Knuth, *Canadian
J. Math.* **20** (1968), 1077–1086.]

**<span
id="ch02ex_3_4_29a">[29](../Text/ch02b.html#ch02ex_3_4_29)</span>.** If
$y=x^t$, then $(tz)y=\ln y$, and we see that it is sufficient to prove
the identity for $t=1$. Now if $zx=\ln x$ we know by [exercise
25](../Text/ch02b.html#ch02ex_3_4_25) that $x^m=\sum_kE_k(m,1)z^k$ for
nonnegative integers *m*. Hence

<div class="image">

![Image](../Images/e592_01.gif)

</div>

[Exercise 4.7–22 derives considerably more general results.]

**<span
id="ch02ex_3_4_30a">[30](../Text/ch02b.html#ch02ex_3_4_30)</span>.**
Each graph described defines a set $C_x\subseteq\{1,\ldots,n\}$, where
*j* is in $C_x$ if and only if there is a path from $t_j$ to $r_i$ for
some $i\le x$. For a given $C_x$ each graph described is composed of two
independent parts: one of the
$x(x+\epsilon_1z_1+\cdots+\epsilon_nz_n)^{\epsilon_1+\cdots+\epsilon_n-1}$
graphs on the vertices $r_i,s_{jk},t_j$ for $i\le x$ and
$j\epsilon C_x$, where $\epsilon_j=[j\epsilon C_x]$, plus one of the
$y(y+(1-\epsilon_1)z_1+\cdots+(1-\epsilon_n)z_n)^{(1-\epsilon_1)+\cdots+(1-\epsilon_n)-1}$
graphs on the other vertices.

**<span
id="ch02ex_3_4_31a">[31](../Text/ch02b.html#ch02ex_3_4_31)</span>.**
$G(z)=z+G(z)^2+G(z)^3+G(z)^4+\cdots=z+G(z)^2/(1-G(z))$. Hence
$G(z)=\frac14\left(1+z-\sqrt{1-6z+z^2}\right)=z+z^2+3z^3+11z^4+45z^5+\cdots$.
[*Notes:* Another problem equivalent to this one was posed and solved by
E. Schröder, *Zeitschrift für Mathematik und Physik* **15** (1870),
361–376, who determined the number of ways to insert nonoverlapping
diagonals in a convex $(n+1)\unicode{45}\rm gon$. These numbers for
$n\gt1$ are just half the values obtained in [exercise
2.2.1–11](../Text/ch02.html#ch02ex_2_1_11), since Pratt’s grammar allows
the root node of the associated parse tree to have degree one. The
asymptotic value is calculated in [exercise
2.2.1–12](../Text/ch02.html#ch02ex_2_1_12). Curiously, the value
$[z^{10}] G(z)=103049$ seems to have been calculated already by
Hipparchus in the second century B.C., as the <span
id="page_593"></span>number of “affirmative compound propositions that
can be made from only ten simple propositions”; see R. P. Stanley, *AMM*
**104** (1997), 344–350; F. Acerbi, *Archive for History of Exact
Sciences* **57** (2003), 465–502.]

**<span
id="ch02ex_3_4_32a">[32](../Text/ch02b.html#ch02ex_3_4_32)</span>.**
Zero if $n_0\neq1+n_2+2n_3+3n_4+\cdots$ (see [exercise
2.3–21](../Text/ch02a.html#ch02ex_1_3_21)), otherwise

$(n_0+n_1+\cdots+n_m-1)!/n_0!n_1!\ldots n_m!$.

To prove this result we recall that an unlabeled tree with
$n=n_0+n_1+\cdots+n_m$ nodes is characterized by the sequence
$d_1d_2\ldots d_n$ of the degrees of the nodes in postorder ([Section
2.3.3](../Text/ch02a.html#ch02lev2sec9)). Furthermore such a sequence of
degrees corresponds to a tree if and only if $\sum_{j=1}^k(1-d_j)\gt0$
for $0\lt k\le n$. (This important property of Polish postfix notation
is readily proved by induction; see [Algorithm
2.3.3F](../Text/ch02a.html#ch02alg-lev2sec9-F) with *f* a function that
creates a tree, like the $\tt TREE$ function of [Section
2.3.2](../Text/ch02a.html#ch02lev2sec8).) In particular, $d_1$ must be
0. The answer to our problem is therefore the number of sequences
$d_2\ldots d_n$ with $n_j$ occurrences of *j* for $j\gt0$, namely the
multinomial coefficient

<div class="image">

![Image](../Images/e593_02.gif)

</div>

minus the number of such sequences $d_2\ldots d_n$ for which
$\sum_{j=2}^k(1-d_j)\lt0$ for some $k\ge2$.

We may enumerate the latter sequences as follows: Let *t* be minimal
such that $\sum_{j=2}^t(1-d_j)\lt0$; then $\sum_{j=2}^t(1-d_j)=-s$ where
$1\le s\lt d_t$, and we may form the subsequence
$d'_2\ldots d'_n=d_{t-1}\ldots d_20d_{t+1}\ldots d_n$, which has $n_j$
occurrences of *j* for $j\neq d_t$, $n_j-1$ occurrences of *j* for
$j=d_t$. Now $\sum_{j=2}^k(1-d'_j)$ is equal to $d_t$ when $k=n$, and
equal to $d_t-s$ when $k=t$; when $k\lt t$, it is

<div class="image">

![Image](../Images/e593_08.gif)

</div>

It follows that, given *s* and any sequence $d'_2\ldots d'_n$, the
construction can be reversed; hence the number of sequences
$d_2\ldots d_n$ that have a given value of $d_t$ and *s* is the
multinomial coefficient

<div class="image">

![Image](../Images/e593_10.gif)

</div>

The number of sequences $d_2\ldots d_n$ that correspond to trees is
therefore obtained by summing over the possible values of $d_t$ and *s*:

<div class="image">

![Image](../Images/e593_11.gif)

</div>

and the latter sum is 1.

An even simpler proof of this result has been given by G. N. Raney
(*Transactions of the American Math. Society* **94** (1960), 441–451).
If $d_1d_2\ldots d_n$ is any sequence with $n_j$ appearances of *j*,
there is precisely one cyclic rearrangement
$d_k\ldots d_nd_1\ldots d_{k-1}$ that corresponds to a tree, namely the
rearrangement where *k* is maximal such that $\sum_{j=1}^{k-1}(1-d_j)$
is minimal. [This argument in the case of binary trees was apparently
first discovered by C. S. Peirce in an unpublished manuscript; see his
*New Elements of Mathematics* **4** (The Hague: Mouton, 1976), 303–304.
It was discovered in the case of $t\unicode{45}\rm ary$ trees by
Dvoretzky and Motzkin, *Duke Math. J.* **14** (1947), 305–313.]

Still another proof, by G. Bergman, inductively replaces $d_kd_{k+1}$ by
$(d_k+d_{k+1}-1)$ if $d_k\gt0$ [*Algebra Universalis* **8** (1978),
129–130].

The methods above can be generalized to show that the number of
(ordered, unlabeled) forests having *f* trees and $n_j$ nodes of degree
*j* is $(n-1)!f/n_0!n_1!\ldots n_m!$, provided that the condition
$n_0=f+n_2+2n_3+\cdots$ is satisfied.

**<span
id="ch02ex_3_4_33a">[33](../Text/ch02b.html#ch02ex_3_4_33)</span>.**
Consider the number of trees with $n_1$ nodes labeled 1, $n_2$ nodes
labeled 2, $\ldots$, and such that each node labeled *j* has degree
$e_j$. Let this number be $c(n_1,n_2,\ldots)$, with the specified
degrees $e_1,e_2,\ldots$ regarded as fixed. The generating function
<span class="middle">![Image](../Images/e594_01a.gif)</span> satisfies
the identity $G=z_1G^{e_1}+\cdots+z_rG^{e_r}$, since $z_jG^{e_j}$
enumerates the trees whose root is labeled *j*. And by the result of the
previous exercise,

<div class="image">

![Image](../Images/e594_01.gif)

</div>

More generally, since $G^f$ enumerates the number of ordered forests
having such labels, we have for integer $f\gt0$

<div class="image">

![Image](../Images/e594_02.gif)

</div>

These formulas are meaningful when $r=\infty$, and they are essentially
equivalent to Lagrange’s inversion formula.

<div class="heading">

##### Section 2.3.4.5 {#app01lev3sec10}

**<span
id="ch02ex_3_5_1a">[1](../Text/ch02b.html#ch02ex_3_5_1)</span>.** There
are <span class="middle">![Image](../Images/e594_03.gif)</span> in all,
since the nodes numbered 8, 9, 10, 11, 12 may be attached in any of
eight positions below 4, 5, 6, and 7.

</div>

**<span
id="ch02ex_3_5_2a">[2](../Text/ch02b.html#ch02ex_3_5_2)</span>.**

<div class="image">

![Image](../Images/e594_04.gif)

</div>

**<span
id="ch02ex_3_5_3a">[3](../Text/ch02b.html#ch02ex_3_5_3)</span>.** By
induction on *m*, the condition is necessary. Conversely if <span
class="middle">![Image](../Images/e594_05.gif)</span>, we want to
construct an extended binary tree with path lengths $l_1,\ldots,l_m$.
When $m=1$, we have $l_1=0$ and the construction is trivial. Otherwise
we may assume that the $l\rm\unicode{39}s$ are ordered so that
$l_1=l_2=\cdots=l_q\gt l_{q+1}\ge l_{q+2}\ge\cdots\ge l_m\gt0$ for some
*q* with $1\le q\le m$. Now <span
class="middle">![Image](../Images/e594_06.gif)</span> integer, hence *q*
is even. By induction on *m* there is a tree with path lengths
$l_1-1,l_3,l_4,\ldots,l_m$; take such a tree and replace one of the
external nodes at level $l_1-1$ by an internal node whose children are
at level $l_1=l_2$.

**<span
id="ch02ex_3_5_4a">[4](../Text/ch02b.html#ch02ex_3_5_4)</span>.** First,
find a tree by Huffman’s method. If $w_j\lt w_{j+1}$, then
$l_j\ge l_{j+1}$, since the tree is optimal. The construction in the
answer to [exercise 3](../Text/ch02b.html#ch02ex_3_5_3) now gives us
another tree with these same path lengths and with the weights in the
proper sequence. For example, the tree
([11](../Text/ch02b.html#ch02eq-lev3sec5-11)) becomes

<div class="image">

![Image](../Images/595fig01.gif)

</div>

*Reference: CACM* **7** (1964), 166–169.

**<span
id="ch02ex_3_5_5a">[5](../Text/ch02b.html#ch02ex_3_5_5)</span>.** (a)
$b_{np}=\sum\limits_{\begin{gather}{k+l=n-1\\r+s+n-1=p}\end{gather}}b_{kr}b_{ls}$.
Hence $zB(w,wz)^2=B(w,z)-1$.

\(b) Take the partial derivative with respect to *w*:

$2zB(w,wz)(B_w(w,wz)+zB_z(w,wz))=B_w(w,z)$.

Therefore if $H(z)=B_w(1,z)=\sum_nh_nz^n$, we find
$H(z)=2zB(z)(H(z)+zB'(z))$; and the known formula for $B(z)$ implies

<div class="image">

![Image](../Images/e595_02.gif)

</div>

The average value is *h~n~/b~n~*. (c) Asymptotically, this comes to
<span class="middle">![Image](../Images/e595_03.gif)</span>.

For the solution to similar problems, see John Riordan, *IBM J. Res. and
Devel.* **4** (1960), 473–478; A. Rényi and G. Szekeres, *J. Australian
Math. Soc.* **7** (1967), 497–507; John Riordan and N. J. A. Sloane, *J.
Australian Math. Soc.* **10** (1969), 278–282; and [exercise
2.3.1–11](../Text/ch02a.html#ch02ex_2_7_11).

**<span
id="ch02ex_3_5_6a">[6](../Text/ch02b.html#ch02ex_3_5_6)</span>.**
$n+s-1=tn$.

**<span
id="ch02ex_3_5_7a">[7](../Text/ch02b.html#ch02ex_3_5_7)</span>.**
$E=(t-1)I+tn$.

**<span
id="ch02ex_3_5_8a">[8](../Text/ch02b.html#ch02ex_3_5_8)</span>.**
Summation by parts gives <span
class="middle">![Image](../Images/e595_04.gif)</span>, where the sum on
the right is over values of *k* such that $0\le k\le n$ and
$(t-1)k+1=t^j$ for some *j*. The latter sum may be rewritten <span
class="middle">![Image](../Images/e595_05.gif)</span>.

**<span
id="ch02ex_3_5_9a">[9](../Text/ch02b.html#ch02ex_3_5_9)</span>.**
Induction on the size of the tree.

**<span
id="ch02ex_3_5_10a">[10](../Text/ch02b.html#ch02ex_3_5_10)</span>.** By
adding extra *zero* weights, if necessary, we may assume that
$m\bmod(t-1)=1$. To obtain a $t\unicode{45}\rm ary$ tree with minimum
weighted path length, combine the smallest *t* values at each step and
replace them by their sum. The proof is essentially the same as the
binary case. The desired ternary tree is shown.

<div class="image">

![Image](../Images/595fig02.gif)

</div>

F. K. Hwang has observed [*SIAM J. Appl. Math.* **37** (1979), 124–127]
that a similar procedure is valid for minimum weighted path length trees
having any prescribed multiset of degrees: Combine the smallest *t*
weights at each step, where *t* is as small as possible.

**<span
id="ch02ex_3_5_11a">[11](../Text/ch02b.html#ch02ex_3_5_11)</span>.** The
“Dewey” notation is the binary representation of the node number.

**<span
id="ch02ex_3_5_12a">[12](../Text/ch02b.html#ch02ex_3_5_12)</span>.** By
[exercise 9](../Text/ch02b.html#ch02ex_3_5_9), it is the internal path
length divided by *n*, plus 1. (This result holds for general trees as
well as binary trees.)

**<span
id="ch02ex_3_5_13a">[13](../Text/ch02b.html#ch02ex_3_5_13)</span>.**
[See J. van Leeuwen, *Proc. 3rd International Colloq. Automata,
Languages and Programming* (Edinburgh University Press, 1976), 382–410.]

**H1.** [Initialize.] Set $A[m-1+i]\gets w_i$ for $1\le i\le m$. Then
set $A[2m]\gets\infty$, $x\gets m$, $i\gets m+1$, $j\gets m-1$,
$k\gets m$. (During this algorithm $A[i]\le\cdots\le A[2m-1]$ is the
queue of unused external weights; $A[k]\ge\cdots\ge A[j]$ is the queue
of unused internal weights, empty if $j\lt k$; the current left and
right pointers are *x* and *y*.)

**H2.** [Find right pointer.] If $j\lt k$ or $A[i]\le A[j]$, set
$y\gets i$ and $i\gets i+1$; otherwise set $y\gets j$ and $j\gets j-1$.

**H3.** [Create internal node.] Set $k\gets k-1$, $L[k]\gets x$,
$R[k]\gets y$, $A[k]\gets A[x]+A[y]$.

**H4.** [Done?] Terminate the algorithm if $k=1$.

**H5.** [Find left pointer.] (At this point $j\ge k$ and the queues
contain a total of *k* unused weights. If $A[y]\lt0$ we have $j=k$,
$i=y+1$, and $A[i]\gt A[j]$.) If $A[i]\le A[j]$, set $x\gets i$ and
$i\gets i+1$; otherwise set $x\gets j$ and $j\gets j-1$. Return to step
H2. <span class="middle">![Image](../Images/box.gif)</span>

**<span
id="ch02ex_3_5_14a">[14](../Text/ch02b.html#ch02ex_3_5_14)</span>.** The
proof for $k=m-1$ applies with little change. [See *SIAM J. Appl. Math.*
**21** (1971), 518.]

**<span
id="ch02ex_3_5_15a">[15](../Text/ch02b.html#ch02ex_3_5_15)</span>.** Use
the combined-weight functions (a) $1+\max(w_1,w_2)$ and (b) $xw_1+xw_2$,
respectively, instead of $w_1+w_2$ in
([9](../Text/ch02b.html#ch02eq-lev3sec5-9)). [Part (a) is due to M. C.
Golumbic, *IEEE Trans.* **C-25** (1976), 1164–1167; part (b) to T. C.
Hu, D. Kleitman, and J. K. Tamaki, *SIAM J. Appl. Math.* **37** (1979),
246–256. Huffman’s problem is the limiting case of (b) as $x\to1$, since
$\sum (1+\epsilon)^{l_j}w_j=\sum w_j+\epsilon\sum w_jl_j+O(\epsilon^2)$.]

D. Stott Parker, Jr., has pointed out that a Huffman-like algorithm will
also find the minimum of $w_1x^{l_1}+\cdots+w_mx^{l_m}$ when
$0\lt x\lt1$, if the two *maximum* weights are combined at each step as
in part (b). In particular, the minimum of
$w_12^{-l_1}+\cdots+w_m2^{-l_m}$, when $w_1\le\cdots\le w_m$, is
$w_1/ 2+\cdots+w_{m-1}/ 2^{m-1}+w_m/ 2^{m-1}$. See D. E. Knuth, *J.
Comb. Theory* **A32** (1982), 216–224, for further generalizations.

**<span
id="ch02ex_3_5_16a">[16](../Text/ch02b.html#ch02ex_3_5_16)</span>.** Let
$l_{m+1}=l'_{m+1}=0$. Then

<div class="image">

![Image](../Images/e596_02.gif)

</div>

since <span class="middle">![Image](../Images/e596_03.gif)</span> as in
[exercise 4](../Text/ch02b.html#ch02ex_3_5_4). The same proof holds for
many other kinds of optimum trees, including those of [exercise
10](../Text/ch02b.html#ch02ex_3_5_10).

**<span
id="ch02ex_3_5_17a">[17](../Text/ch02b.html#ch02ex_3_5_17)</span>.** (a)
This is [exercise 14](../Text/ch02b.html#ch02ex_3_5_14). (b) We can
extend $f(n)$ to a concave function $f(x)$, so the stated inequality
holds. Now $F(m)$ is the minimum of <span
class="middle">![Image](../Images/e596_04.gif)</span>, where the $s_j$
are internal node weights of an extended binary tree on the weights
$1,1,\ldots,1$. Huffman’s algorithm, which constructs the complete
binary tree with $m-1$ internal nodes in this case, yields the optimum
tree. The choice $k=2^{\lceil{lg(n/3)}\rceil}$ defines a binary tree
with the same internal weights, so it yields the minimum in the
recurrence, for each *n*. [*SIAM J. Appl. Math.* **31** (1976),
368–378.] We can evaluate $F(n)$ in $O(log n)$ steps; see exercises
5.2.3–20 and 5.2.3–21. If $f(n)$ is convex instead of concave, so that
$\varDelta^2 f(n)\ge0$, the solution to the recurrence is obtained when
$k=\lfloor{n/2}\rfloor$.

<div class="heading">

##### <span id="page_597"></span>Section 2.3.4.6 {#app01lev3sec11}

**<span
id="ch02ex_3_6_1a">[1](../Text/ch02b.html#ch02ex_3_6_1)</span>.** Choose
one edge of the polygon and call it the base. Given a triangulation, let
the triangle on the base correspond to the root of a binary tree, and
let the other two sides of that triangle define bases of left and right
subpolygons, which correspond to left and right subtrees in the same
way. We proceed recursively until reaching “2-sided” polygons, which
correspond to empty binary trees.

</div>

Stating this correspondence another way, we can label the non-base edges
of a triangulated polygon with the integers $0,\ldots,n$; and when two
adjacent sides of a triangle are labeled *α* and *β* in clockwise order,
we can label the third side $(\alpha\beta)$. The label of the base then
characterizes the binary tree and the triangulation. For example,

<div class="image">

![Image](../Images/597fig01.gif)

</div>

corresponds to the binary tree shown in
[2.3.1](../Text/ch02a.html#ch02lev2sec7)–([1](../Text/ch02a.html#ch02eq-lev2sec7-1)).
[See H. G. Forder, *Mathematical Gazette* **45** (1961), 199–201.]

**<span
id="ch02ex_3_6_2a">[2](../Text/ch02b.html#ch02ex_3_6_2)</span>.** (a)
Take a base edge as in [exercise 1](../Text/ch02b.html#ch02ex_3_6_1),
and give it *d* descendants if that edge is part of a
$(d+1)\unicode{45}\rm gon$ in the dissected $r\unicode{45}\rm gon$. The
other *d* edges are then bases for subtrees. This defines a
correspondence between Kirkman’s problem and all ordered trees with
$r-1$ leaves and $k+1$ nonleaves, having no nodes of degree 1. (When
$k=r-3$ we have the situation of [exercise
1](../Text/ch02b.html#ch02ex_3_6_1).)

\(b) There are <span
class="middle">![Image](../Images/e597_01.gif)</span> sequences
$d_1d_2\ldots d_{r+k}$ of nonnegative integers such that $r-1$ of the
$d\unicode{39}\rm s$ are 0, none of them are 1, and the sum is $r+k-1$.
Exactly one of the cyclic permutations
$d_1d_2\ldots d_{r+k},d_2\ldots d_{r+k}d_1,\ldots,d_{r+k}d_1\ldots d_{r+k-1}$
satisfies the additional property that <span
class="middle">![Image](../Images/e597_02.gif)</span> for
$1\le q\le r+k$.

[Kirkman gave evidence for his conjecture in *Philos. Trans.* **147**
(1857), 217–272, §22. Cayley proved it in *Proc. London Math. Soc.*
**22** (1891), 237–262, without noticing the connection to trees.]

**<span
id="ch02ex_3_6_3a">[3](../Text/ch02b.html#ch02ex_3_6_3)</span>.** (a)
Let the vertices be $\{1,2,\ldots,n\}$. Draw an $\tt RLINK$ from *i* to
*j* if *i* and *j* are consecutive elements of the same part and
$i\lt j$; draw an $\tt LLINK$ from *j* to $j+1$ if $j+1$ is the smallest
of its part. Then there are $k-1$ nonnull $\tt LLINK\rm{s}$, $n-k$
nonnull $\tt RLINK\rm{s}$, and we have a binary tree whose nodes are
$12\ldots n$ in preorder. Using the natural correspondence of [Section
2.3.2](../Text/ch02a.html#ch02lev2sec8), this rule defines a one-to-one
correspondence between “partitions of an
$n\unicode{45}\rm gon\unicode{39}s$ vertices into *k* noncrossing parts”
and “forests with *n* vertices and $n-k+1$ leaves.” Interchanging
$\tt LLINK$ with $\tt RLINK$ also gives “forests with *n* vertices and
*k* leaves.”

\(b) A forest with *n* vertices and *k* leaves also corresponds to a
sequence of nested parentheses, containing *n* left parentheses, *n*
right parentheses, and *k* occurrences of “()”. We can enumerate such
sequences as follows:

Say that a string of 0s and 1s is an $(m,n,k)$ string if there are *m*
0s, *n* 1s, and *k* occurrences of “01”. Then $0010101001110$ is a
$(7,6,4)$ string. The number of $(m,n,k)$ strings is <span
class="middle">![Image](../Images/e598_01.gif)</span>, because we are
free to choose which 0s and 1s will form the 01 pairs.

Let $S(\alpha)$ be the number of 0s in *α* minus the number of 1s. We
say that a string σ is *good* if $S(\alpha)\ge0$ whenever *α* is a
prefix of σ (in other words, if $\sigma=\alpha\beta$ implies that
$S(\alpha)\ge0$); otherwise σ is *bad*. The following alternative to the
“reflection principle” of [exercise
2.2.1–4](../Text/ch02.html#ch02ex_2_1_4) establishes a one-to-one
correspondence between bad $(n,n,k)$ strings and arbitrary $(n-1,n+1,k)$
strings:

Any bad $(n,n,k)$ string σ can be written uniquely in the form
$\sigma=\alpha0\beta$, where <span
class="middle">![Image](../Images/e598_02.gif)</span> and *β* are good.
(Here <span class="middle">![Image](../Images/e598_02.gif)</span> is the
string obtained from *α* by reversing it and complementing all the
bits.) Then $\sigma'=\alpha1\beta$ is an $(n-1,n+1,k)$ string.
Conversely, every $(n-1,n+1,k)$ string can be written uniquely in the
form $\alpha1\beta$ where <span
class="middle">![Image](../Images/e598_02.gif)</span> and *β* are good,
and $\alpha0\beta$ is then a bad $(n,n,k)$ string.

Thus the number of forests with *n* vertices and *k* leaves is <span
class="middle">![Image](../Images/e598_03.gif)</span>, a so-called
*Narayana number* [T. V. Narayana, *Comptes Rendus Acad. Sci.* **240**
(Paris, 1955), 1188–1189].

*Notes:* G. Kreweras, *Discrete Math.* **1** (1972), 333–350, enumerated
noncrossing partitions in a different way. The partial ordering of
partitions by refinement leads to an interesting partial ordering of
forests, different from the one discussed in [exercise
2](../Text/ch02b.html#ch02ex_3_6_2).3.3– 19; see Y. Poupard, *Cahiers du
Bureau Univ. de Recherche Opér.* **16** (1971), Chapter 8; *Discrete
Math.* **2** (1972), 279–288; P. Edelman, *Discrete Math.* **31**
(1980), 171–180, **40** (1982), 171–179; N. Dershowitz and S. Zaks,
*Discrete Math.* **64** (1986), 215–218.

A third way to define a natural lattice ordering of forests was
introduced by R. Stanley in *Fibonacci Quarterly* **13** (1975),
215–232: Suppose we represent a forest by a string σ of 0s and 1s
representing left and right parentheses as above; then
$\sigma\le\sigma'$ if and only if $S(\sigma_k)\le S(\sigma'_k)$ for all
*k*, where $\sigma_k$ denotes the first *k* bits of σ. Stanley’s lattice
is *distributive*, unlike the other two.

**<span
id="ch02ex_3_6_4a">[4](../Text/ch02b.html#ch02ex_3_6_4)</span>.** Let
$m=n+2$; by [exercise 1](../Text/ch02b.html#ch02ex_3_6_1), we want a
correspondence between triangulated $m\unicode{45}\rm gons$ and
$(m-1)\unicode{45}\rm rowed$ friezes. First let’s look more closely at
the previous correspondence, by giving a “top-down” labeling to the
edges of a triangulation instead of the “bottom-up” one considered
earlier: Assign the empty label $\epsilon$ to the base, then recursively
give the labels $\alpha L$ and $\alpha R$ to the opposite edges of a
triangle whose base is labeled *α*. For example, the previous diagram
becomes

<div class="image">

![Image](../Images/598fig01.gif)

</div>

under these new conventions. If the base edge in this example is called
10, while the other edges are 0 to 9 as before, we can write $0=10LLL$,
$1=10LLR$, $2=10LR$, <span id="page_599"></span>$3=10RLL$, etc. Any of
the other edges can also be chosen as the base; thus, if 0 is chosen we
have $1=0L$, $2=0RL$, $3=0RRLLL$, etc. It is not difficult to verify
that if $u=v\alpha$ we have $v=u\alpha^T$, where $\alpha^T$ is obtained
by reading *α* from right to left and interchanging *L* with *R*. For
example, $10=0RRR=1LRR=2LR=3RRL$, etc. If *u*, *υ*, and *w* are edges of
the polygon with $w=u\alpha L\gamma$ and $w=v\beta R\gamma$, then
$u=v\beta L\alpha^T$ and $v=u\alpha R\beta^T$.

Given a triangulation of a polygon whose edges are numbered
$0,1,\ldots,m-1$, we define $(u,v)$ for any pair of distinct edges *u*
and *υ* as follows: Let $u=v\alpha$, and interpret *α* as a $2\times2$
matrix by letting <span
class="middle">![Image](../Images/e599_01.gif)</span> and <span
class="middle">![Image](../Images/e599_02.gif)</span>. Then $(u,v)$ is
defined to be the element in the upper left corner of *α*. Notice that
$\alpha^T$ is the transpose of the matrix *α*, since $R=L^T$; hence we
have $(v,u)=(u,v)$. Notice also that $(u,v)=1$ if and only if $u_-$ and
$v_-$ are joined by an edge of the triangulation, where $u_-$ denotes
the vertex between edges *u* and $u-1$.

Let $(u,u)=0$ for all polygon edges *u*. We can now prove that
$v=u\alpha$ implies

<div class="image">

![Image](../Images/e599_03.gif)

</div>

where $u+1$ and $v+1$ are the clockwise successors of *u* and *υ*. The
proof is by induction on *m*: Eq. $(*)$ is trivial when $m=2$, since the
two parallel edges *u* and *υ* are then related by $u=v\epsilon$, and
$\alpha=\epsilon$ is the identity matrix. If any triangulation is
augmented by extending some edge *υ* with a triangle $v\;v'\;v''$, then
$v=u\alpha$ implies $v'=u\alpha L$ and $v''=u\alpha R$; hence $(u,v')$
and $(u,v'')$ in the extended polygon are respectively equal to $(u,v)$
and $(u,v)+(u,v+1)$ in the original one. It follows that

<div class="image">

![Image](../Images/e599_04.gif)

</div>

and $(*)$ remains true in the extended polygon.

The frieze pattern corresponding to the given triangulation is now
defined to be the periodic sequence

<div class="image">

![Image](../Images/e599_05.gif)

</div>

and so on until $m-1$ rows have been defined; the final row begins with
$(\lceil{m/2}\rceil+1,\lceil{m/2}\rceil)$ when $m\gt3$. Condition $(*)$
proves that this pattern is a frieze, namely that

<div class="image">

![Image](../Images/e599_06.gif)

</div>

because $\det L=\det R=1$ implies $\det\alpha=1$. Our example
triangulation yields

1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   . . .\

  1   2   4   2   1   5   1   3   1   4   3   1   2   4   2   1   5   1   3   1   4     . . .\

2   1   7   7   1   4   4   2   2   3   11   2   1   7   7   1   4   4   2   2   3   . . .\

  1   3   12  3   3   3   7   1   5   8    7   1   3  12   3   3   3   7   1   5   8    . . .\

3   2   5   5   8   2   5   3   2   13   5   3   2   5   5   8   2   5   3   2   13   . . .\

  5   3   2   13  5   3   2   5   5    8   2   5   3   2   13  5   3   2   5   5   8   . . .\

3   7   1   5   8   7   1   3   12   3   3   3   7   1   5   8   7   1   3   12  3   . . .\

  4   2   2   3   11   2   1   7   7   1   4   4   2   2   3   11  2   1   7   7   1    . . .\

5   1   3   1   4    3   1   2   4   2   1   5   1   3   1   4   3   1   2   4   2   . . .\

  1   1   1   1   1    1   1   1   1   1   1   1   1   1   1   1   1   1   1   1   1    . . .

The relation $(u,v)=1$ defines the edges of the triangulation, hence
different triangulations yield different friezes. To complete the proof
of one-to-one correspondence, we must show that every
$(m-1)\unicode{45}\rm rowed$ frieze pattern of positive integers is
obtained in this way from some triangulation.

Given any frieze of $m-1$ rows, extend it by putting a new row 0 at the
top and a new row *m* at the bottom, both consisting entirely of zeros.
Now let the elements of row 0 be called $(0,0)$, $(1,1)$, $(2,2)$, etc.,
and for all nonnegative integers $u\lt v\le u+m$ let $(u,v)$ be the
element in the diagonal southeast of $(u,u)$ and in the diagonal
southwest of $(v,v)$. By assumption, condition $(**)$ holds for all
$u\lt v\lt u+m$. We can in fact extend $(**)$ to the considerably more
general relation

<div class="image">

![Image](../Images/e600_01.gif)

</div>

For if $(***)$ is false, let $(t,u,v,w)$ be a counterexample with the
smallest value of $(w-t)m+u-t+w-v$. Clearly $t\neq u$ and $v\neq w$.
*Case 1:* $t+1\lt u$. Then $(***)$ holds for $(t,t+1,v,w)$,
$(t,t+1,u,v)$, and $(t+1,u,v,w)$, so we find
$((t,u)(v,w)+(t,w)(u,v))(t+1,v)=(t,v)(u,w)(t+1,v); this implies (t+1,v)=0$,
a contradiction. *Case 2:* $v+1\lt w$. Then $(***)$ holds for
$(t,u,w-1,w)$, $(u,v,w-1,w)$, and $(t,u,v,w-1)$; we obtain a similar
contradiction $(u,w-1)=0$. *Case 3:* $u=t+1$ and $w=v+1$. In this case
$(***)$ reduces to $(**)$.

Now we set $u=t+1$ and $w=t+m$ in $(***)$, obtaining $(t,v)=(v,t+m)$ for
$t\le v\le t+m$, because $(t+1,t+m)=1$ and $(t,t+m)=0$. We conclude that
the entries of any $(m-1)\unicode{45}\rm rowed$ frieze are periodic:
$(u,v)=(v,u+m)=(u+m,v+m)=(v+m,u+2m)=\cdots$.

Every frieze pattern of positive integers contains a 1 in row 2. For if
we set $t=0$, $v=u+1$, and $w=u+2$ in $(***)$ we get
$(0,u+1)(u,u+2)=(0,u)+(0,u+2)$, hence $(0,u+2)-(0,u+1)\ge (0,u+1)-(0,u)$
if and only if $(u,u+2)\ge2$. This cannot hold for all *u* in the range
$0\le u\le m-2$, because $(0,1)-(0,0)=1$ and $(0,m)-(0,m-1)=-1$.

Finally, if $m\gt3$ we cannot have two consecutive 1s in row 2, because
$(u,u+2)=(u+1,u+3)=1$ implies $(u,u+3)=0$. Therefore we can reduce the
frieze to another one with *m* reduced by 1, as illustrated here for 7
rows reduced to 6:

<div class="image">

![Image](../Images/e600_02.gif)

</div>

The reduced frieze corresponds to a triangulation, by induction, and the
unreduced frieze corresponds to attaching one more triangle. [*Math.
Gazette* **57** (1974), 87–94, 175–183; Conway and Guy, *The Book of
Numbers* (New York: Copernicus, 1996), 74–76, 96–97, 101–102.]

*Notes:* This proof demonstrates that the function $(u,v)$, which we
defined on any triangulation via $2\times2$ matrices, satisfies $(***)$
whenever $(t,u,v,w)$ are edges of the polygon in clockwise order. We can
express each $(u,v)$ as a polynomial in the numbers $a_j=(j-1,j+1)$;
these polynomials are essentially identical to the “continuants”
discussed in Section 4.5.3, except for the signs of individual terms. In
fact, $(j,k)=i^{1-k+j}K_{k-j-1}(ia_{j+1},ia_{j+2},\ldots,ia_{k-1})$.
Thus $(***)$ is equivalent to Euler’s identity <span
id="page_601"></span>for continuants in the answer to exercise 4.5.3–32.
The matrices *L* and *R* have the interesting property that any
$2\times2$ matrix of nonnegative integers with determinant 1 can be
expressed uniquely as a product of $L\unicode{39}\rm s$ and
$R\unicode{39}\rm s$.

Many other interesting relationships are present; for example, the
numbers in row 2 of an integer frieze count the number of triangles
touching each vertex of the corresponding triangulated polygon. The
total number of occurrences of $(u,v)=1$ in the basic region
$0\le u\lt v-1\lt m-1$ and $(u,v)\neq (0,m-1)$ is the number of
diagonals (chords) of the triangulation, namely $m-3=n-1$. The total
number of 2s is also $n-1$, because $(u,v)=2$ if and only if $u_-$ and
$v_-$ are opposing vertices of the two triangles adjacent to a chord.

Another interpretation of $(u,v)$ was found by D. Broline, D. W. Crowe,
and I. M. Isaacs [*Geometriæ Dedicata* **3** (1974), 171–176]: It is the
number of ways to match the $v-u-1$ vertices between edges *u* and $v-1$
with distinct triangles adjacent to those vertices.

<div class="heading">

#### Section 2.3.5 {#app01lev2sec26}

**<span
id="ch02ex_2_11_1a">[1](../Text/ch02c.html#ch02ex_2_11_1)</span>.** A
List structure is a directed graph in which the arcs leaving each vertex
are ordered, and where some of the vertices that have out-degree 0 are
designated “atoms.” Furthermore there is a vertex *S* such that there is
an oriented path from *S* to *V* for all vertices $V\neq S$. (With
directions of arcs reversed, *S* would be a “root.”)

</div>

**<span
id="ch02ex_2_11_2a">[2](../Text/ch02c.html#ch02ex_2_11_2)</span>.** Not
in the same way, since thread links in the usual representation lead
back to “$\tt PARENT$,” which is not unique for sub-Lists. The
representation discussed in [exercise
2.3.4.2–25](../Text/ch02b.html#ch02ex_3_2_25), or some similar method,
could perhaps be used (but this idea has not yet been exploited at the
time of writing).

**<span
id="ch02ex_2_11_3a">[3](../Text/ch02c.html#ch02ex_2_11_3)</span>.** As
mentioned in the text, we prove also that ${\tt P}=\tt P0$ upon
termination. If only $\tt P0$ is to be marked, the algorithm certainly
operates correctly. If $n\gt1$ nodes are to be marked, we must have
${\tt ATOM(P0)}=0$. Step E4 then sets ${\tt ALINK(P0)}\gets\varLambda$
and executes the algorithm with $\tt P0$ replaced by $\tt ALINK(P0)$ and
$\tt T$ replaced by $\tt P0$. By induction (note that since
$\tt MARK(P0)$ is now 1, all links to $\tt P0$ are equivalent to *Λ* by
steps E4 and E5), we see that ultimately we will mark all nodes on paths
that start with $\tt ALINK(P0)$ and do not pass through $\tt P0$; and we
will then get to step E6 with ${\tt T}=\tt P0$ and
${\tt P}=\tt ALINK(P0)$. Now since ${\tt ATOM(T)}=1$, step E6 restores
$\tt ALINK(P0)$ and $\tt ATOM(P0)$ and we reach step E5. Step E5 sets
${\tt BLINK(P0)}\gets\varLambda$, etc., and a similar argument shows
that we will ultimately mark all nodes on paths that start with
$\tt BLINK(P0)$ and do not pass through $\tt P0$ or nodes reachable from
$\tt ALINK(P0)$. Then we will get to E6 with ${\tt T}=\tt P0$,
${\tt P}=\tt BLINK(P0)$, and finally we get to E6 with
${\tt T}=\varLambda$, ${\tt P}=\tt P0$.

**<span
id="ch02ex_2_11_4a">[4](../Text/ch02c.html#ch02ex_2_11_4)</span>.** The
program that follows incorporates the suggested improvements in the
speed of processing atoms that appear in the text after the statement of
[Algorithm E](../Text/ch02c.html#ch02alg-lev2sec11-E).

In steps E4 and E5 of the algorithm, we want to test if
${\tt MARK(Q)}=0$. If ${\tt NODE(Q)}=+0$, this is an unusual case that
can be handled properly by setting it to $-0$ and treating it as if it
were originally $-0$, since it has $\tt ALINK$ and $\tt BLINK$ both *Λ*.
This simplification is not reflected in the timing calculations below.

$\rm rI1\equiv\tt P$, $\rm rI2\equiv\tt T$, $\rm rI3\equiv\tt Q$, and
$rX\equiv-1$ (for setting $\tt MARK\rm{s}$).

<div class="image">

![Image](../Images/601pro01.gif)

</div>

<div id="page_602" class="image">

![Image](../Images/601pro01a.gif)

</div>

By Kirchhoff’s law, $t_1+t_2+1=n$. The total time is
$(34n+4t_1+3a-5b-8)u$, where *n* is the number of nonatomic nodes
marked, *a* is the number of atoms marked, *b* is the number of *Λ*
links encountered in marked nonatomic nodes, and $t_1$ is the number of
times we went down an $\tt ALINK$ $(0\le t_1\lt n)$.

**<span
id="ch02ex_2_11_5a">[5](../Text/ch02c.html#ch02ex_2_11_5)</span>.** (The
following is the fastest known marking algorithm for a one-level
memory.)

**S1.** Set ${\tt MARK(P0)}\gets1$. If $\tt ATOM(P0)=1$, the algorithm
terminates; otherwise set $\tt S\gets0$, $\tt R\gets P0$,
${\tt T}\gets\varLambda$.

**S2.** Set $\tt P\gets BLINK(R)$. If ${\tt P}=\varLambda$ or
$\tt MARK(P)=1$, go to S3. Otherwise set $\tt MARK(P)\gets1$. Now if
$\tt ATOM(P)=1$, go to S3; otherwise if ${\tt S}\lt\tt N$ set
${\tt S\gets S}+1$, $\tt STACK[S]\gets P$, and go to S3; otherwise go to
S5.

**S3.** Set $\tt P\gets ALINK(R)$. If ${\tt P}=\varLambda$ or
${\tt MARK(P)}=1$, go to S4. Otherwise set ${\tt MARK(P)}\gets1$. Now if
${\tt ATOM(P)}=1$, go to S4; otherwise set $\tt R\gets P$ and return to
S2.

**S4.** If ${\tt S}=0$, terminate the algorithm; otherwise set
$\tt R\gets STACK[S]$, ${\tt S\gets S}-1$, and go to S2.

**S5.** Set $\tt Q\gets ALINK(P)$. If ${\tt Q}=\varLambda$ or
${\tt MARK(Q)}=1$, go to S6. Otherwise set ${\tt MARK(Q)}\gets1$. Now if
${\tt ATOM(Q)}=1$, go to S6; otherwise set ${\tt ATOM(P)}\gets1$,
$\tt ALINK(P)\gets T$, $\tt T\gets P$, $\tt P\gets Q$, go to S5.

**S6.** Set $\tt Q\gets BLINK(P)$. If ${\tt Q}=\varLambda$ or
${\tt MARK(Q)}=1$, go to S7; otherwise set ${\tt MARK(Q)}\gets1$. Now if
${\tt ATOM(Q)}=1$, go to S7; otherwise set $\tt BLINK(P)\gets T$,
$\tt T\gets P$, $\tt P\gets Q$, go to S5.

**S7.** If ${\tt T}=\varLambda$, go to S3. Otherwise set $\tt Q\gets T$.
If ${\tt ATOM(Q)}=1$, set ${\tt ATOM(Q)}\gets0$, $\tt T\gets ALINK(Q)$,
$\tt ALINK(Q)\gets P$, $\tt P\gets Q$, and return to S6. If
${\tt ATOM(Q)}=0$, set $\tt T\gets BLINK(Q)$, $\tt BLINK(Q)\gets P$,
$\tt P\gets Q$, and return to S7. <span
class="middle">![Image](../Images/box.gif)</span>

*Reference: CACM* **10** (1967), 501–506.

**<span
id="ch02ex_2_11_6a">[6](../Text/ch02c.html#ch02ex_2_11_6)</span>.** From
the second phase of garbage collection (or perhaps also the initial
phase, if all mark bits are set to zero at that time).

**<span
id="ch02ex_2_11_7a">[7](../Text/ch02c.html#ch02ex_2_11_7)</span>.**
Delete steps E2 and E3, and delete “${\tt ATOM(P)}\gets1$” in E4. Set
${\tt MARK(P)}\gets1$ in step E5 and use “${\tt MARK(Q)}=0$”,
“${\tt MARK(Q)}=1$” in step E6 in place of the present
“${\tt ATOM(Q)}=1$”, “${\tt ATOM(Q)}=0$” respectively. The idea is to
set the $\tt MARK$ bit only after the left subtree has been marked. This
algorithm works even if the tree has overlapping (shared) subtrees, but
it does not work for all recursive List structures such as those with
${\tt NODE(ALINK(Q))}$ an ancestor of $\tt NODE(Q)$. (Note that
$\tt ALINK$ of a marked node is never changed.)

**<span
id="ch02ex_2_11_8a">[8](../Text/ch02c.html#ch02ex_2_11_8)</span>.**
*Solution 1:* Analogous to [Algorithm
E](../Text/ch02c.html#ch02alg-lev2sec11-E), but simpler.

**F1.** Set ${\tt T}\gets\varLambda$, $\tt P\gets P0$.

**F2.** Set ${\tt MARK(P)}\gets1$, and set ${\tt P\gets P}+\tt SIZE(P)$.

**F3.** If ${\tt MARK(P)}=1$, go to F5.

**F4.** Set $\tt Q\gets LINK(P)$. If ${\tt Q}\neq\varLambda$ and
${\tt MARK(Q)}=0$, set $\tt LINK(P)\gets T$, $\tt T\gets P$,
$\tt P\gets Q$ and go to F2. Otherwise set ${\tt P\gets P}-1$ and return
to F3.

**F5.** If ${\tt T}=\varLambda$, stop. Otherwise set $\tt Q\gets T$,
$\tt T\gets LINK(Q)$, $\tt LINK(Q)\gets P$, ${\tt P\gets Q}-1$, and
return to F3. <span class="middle">![Image](../Images/box.gif)</span>

A similar algorithm, which sometimes decreases the storage overhead and
which avoids all pointers into the middle of nodes, has been suggested
by Lars-Erik Thorelli, *BIT* **12** (1972), 555–568.

*Solution 2:* Analogous to [Algorithm
D](../Text/ch02c.html#ch02alg-lev2sec11-D). For this solution, we assume
that the $\tt SIZE$ field is large enough to contain a link address.
Such an assumption is probably not justified by the statement of the
problem, but it lets us use a slightly faster method than the first
solution when it is applicable.

**G1.** Set ${\tt T}\gets\varLambda$, ${\tt MARK(P0)}\gets1$,
${\tt P\gets P0}+\tt SIZE(P0)$.

**G2.** If ${\tt MARK(P)}=1$, go to G5.

**G3.** Set $\tt Q\gets LINK(P)$, ${\tt P\gets P}-1$.

**G4.** If ${\tt Q}\neq\varLambda$ and ${\tt MARK(Q)}=0$, set
${\tt MARK(Q)}\gets1$, $\tt S\gets SIZE(Q)$, $\tt SIZE(Q)\gets T$,
${\tt T\gets Q}+\tt S$. Go back to G2.

**G5.** If ${\tt T}=\varLambda$, stop. Otherwise set $\tt P\gets T$ and
find the first value of ${\tt Q}={\tt P},{\tt P}-1,{\tt P}-2,\ldots$ for
which ${\tt MARK(Q)}=1$; set $\tt T\gets SIZE(Q)$ and
${\tt SIZE(Q)\gets P}-\tt Q$. Go back to G2. <span
class="middle">![Image](../Images/box.gif)</span>

**<span
id="ch02ex_2_11_9a">[9](../Text/ch02c.html#ch02ex_2_11_9)</span>. H1.**
Set ${\tt L}\gets0$, ${\tt K\gets M}+1$, ${\tt MARK(0)}\gets1$,
${\tt MARK(M}+1{\tt)}\gets0$.

**H2.** Increase $\tt L$ by one, and if ${\tt MARK(L)}=$ 1 repeat this
step.

**H3.** Decrease $\tt K$ by one, and if ${\tt MARK(K)}=0$ repeat this
step.

**H4.** If ${\tt L}\gt\tt K$, go to step H5; otherwise set
${\tt NODE(L)\gets NODE(K)}$, $\tt ALINK(K)\gets L$,
${\tt MARK(K)}\gets0$, and return to H2.

**H5.** For ${\tt L}=1,2,\ldots,\tt K$ do the following: Set
${\tt MARK(L)}\gets0$. If ${\tt ATOM(L)}=0$ and $\tt ALINK(L)\gt K$, set
$\tt ALINK(L)\gets ALINK(ALINK(L))$. If ${\tt ATOM(L)}=0$ and
$\tt BLINK(L)\gt K$, set $\tt BLINK(L)\gets ALINK(BLINK(L))$. <span
class="middle">![Image](../Images/box.gif)</span>

See also [exercise 2.5–33](../Text/ch02c.html#ch02ex_1_5_33).

**<span
id="ch02ex_2_11_10a">[10](../Text/ch02c.html#ch02ex_2_11_10)</span>.
Z1.** [Initialize.] Set $\tt F\gets P0$, $\tt R\Leftarrow AVAIL$,
$\tt NODE(R)\gets NODE(F)$, $\tt REF(F)\gets R$. (Here $\tt F$ and
$\tt R$ are pointers for a queue set up in the $\tt REF$ fields of all
header nodes encountered.)

**Z2.** [Begin new List.] Set $\tt P\gets F$, $\tt Q\gets REF(P)$.

**Z3.** [Advance to right.] Set $\tt P\gets RLINK(P)$. If
${\tt P}=\varLambda$, go to Z6.

**Z4.** [Copy one node.] Set $\tt Q1\Leftarrow AVAIL$,
$\tt RLINK(Q)\gets Q1$, $\tt Q\gets Q1$, $\tt NODE(Q)\gets NODE(P)$.

**Z5.** [Translate sub-List link.] If ${\tt T(P)}=1$, set
$\tt P1\gets REF(P)$, and if ${\tt REF(P1)}=\varLambda$ set
$\tt REF(R)\gets P1$, $\tt R\Leftarrow AVAIL$, $\tt REF(P1)\gets R$,
$\tt NODE(R)\gets NODE(P1)$, $\tt REF(Q)\gets R$. If ${\tt T(P)}=1$ and
$\tt REF(P1)\neq\varLambda$, set $\tt REF(Q)\gets REF(P1)$. Go to Z3.

**Z6.** [Move to next List.] Set $\tt RLINK(Q)\gets\varLambda$. If
$\tt REF(F)\neq R$, set $\tt F\gets REF(REF(F))$ and return to Z2.
Otherwise set $\tt REF(R)\gets\varLambda$, $\tt P\gets P0$.

**Z7.** [Final cleanup.] Set $\tt Q\gets REF(P)$. If
$\tt Q\neq\varLambda$, set $\tt REF(P)\gets\varLambda$ and
$\tt P\gets Q$ and repeat step Z7. <span
class="middle">![Image](../Images/box.gif)</span>

Of course, this use of the $\tt REF$ fields makes it impossible to do
garbage collection with [Algorithm
D](../Text/ch02c.html#ch02alg-lev2sec11-D); moreover, [Algorithm
D](../Text/ch02c.html#ch02alg-lev2sec11-D) is ruled out by the fact that
the Lists aren’t well-formed during the copying.

Several elegant List-moving and List-copying algorithms that make
substantially weaker assumptions about List representation have been
devised. See D. W. Clark, *CACM* **19** (1976), 352–354; J. M. Robson,
*CACM* **20** (1977), 431–433.

**<span
id="ch02ex_2_11_11a">[11](../Text/ch02c.html#ch02ex_2_11_11)</span>.**
Here is a pencil-and-paper method that can be written out more formally
to answer the problem: First attach a unique name (e.g., a capital
letter) to each List in the given set; in the example we might have
$A=(a\colon C,b,a\colon F)$, $F=(b\colon D)$,
$B=(a\colon F,b,a\colon E)$, $C=(b\colon G)$, $G=(a\colon C)$,
$D=(a\colon F)$, $E=(b\colon G)$. Now make a list of pairs of List names
that must be proved equal. Successively add pairs to this list until
either a contradiction is found because we have a pair that disagree on
the first level (then the originally given Lists are unequal), or until
the list of pairs does not imply any further pairs (then the originally
given Lists are equal). In the example, this list of pairs would
originally contain only the given pair, *AB*; then it gets the further
pairs *CF*, *EF* (by matching *A* and *B*), *DG* (from *CF*); and then
we have a self-consistent set.

To prove the validity of this method, observe that (i) if it returns the
answer “unequal”, the given Lists are unequal; (ii) if the given Lists
are unequal, it returns the answer “unequal”; (iii) it always
terminates.

**<span
id="ch02ex_2_11_12a">[12](../Text/ch02c.html#ch02ex_2_11_12)</span>.**
When the $\tt AVAIL$ list contains *N* nodes, where *N* is a specified
constant to be chosen as discussed below, initiate another coroutine
that shares computer time with the main routine and does the following:
(a) Marks all *N* nodes on the $\tt AVAIL$ list; (b) marks all other
nodes that are accessible to the program; (c) links all unmarked nodes
together to prepare a new $\tt AVAIL$ list for use when the current
$\tt AVAIL$ list is empty, and (d) resets the mark bits in all nodes.
One must choose *N* and the ratio of time sharing so that operations
(a), (b), (c), and (d) are guaranteed to be complete before *N* nodes
are taken from the $\tt AVAIL$ list, yet the main routine is running
sufficiently fast. It is necessary to use some care in step (b) to make
sure that all nodes “accessible to the program” are included, as the
program continues to run; details are omitted here. If the list formed
in (c) has fewer than *N* nodes, it may be necessary to stop eventually
because memory space might become exhausted. [For further information,
see Guy L. Steele Jr., *CACM* **18** (1975), 495–508; P. Wadler, *CACM*
**19** (1976), 491–500; E. W. Dijkstra, L. Lamport, A. J. Martin, C. S.
Scholten, and E. F. M. Steffens, *CACM* **21** (1978), 966–975; H. G.
Baker, Jr., *CACM* **21** (1978), 280–294.]

<div class="heading">

### Section 2.4 {#app01lev1sec5}

**<span
id="ch02ex_1_4_1a">[1](../Text/ch02c.html#ch02ex_1_4_1)</span>.**
Preorder.

</div>

**<span
id="ch02ex_1_4_2a">[2](../Text/ch02c.html#ch02ex_1_4_2)</span>.** It is
essentially proportional to the number of Data Table entries created.

**<span
id="ch02ex_1_4_3a">[3](../Text/ch02c.html#ch02ex_1_4_3)</span>.** Change
step A5 to:

**A5'.** [Remove top level.] Remove the top stack entry; and if the new
level number at the top of the stack is $\ge\tt L$, let
$({\tt L1},{\tt P1})$ be the new entry at the top of the stack and
repeat this step. Otherwise set $\tt SIB(P1)\gets Q$ and then let
$({\tt L1},{\tt P1})$ be the new entry at the top of the stack.

**<span
id="ch02ex_1_4_4a">[4](../Text/ch02c.html#ch02ex_1_4_4)</span>.**
(Solution by David S. Wise.) Rule (c) is violated if and only if there
is a data item whose *complete qualification*
$A_0{\tt OF}\ldots{\tt OF}A_n$ is also a COBOL reference to some other
data item. Since the parent $A_1{\tt OF}\ldots{\tt OF}A_n$ must also
satisfy rule (c), we may assume that this other data item is a
descendant of the same parent. Therefore [Algorithm
A](../Text/ch02c.html#ch02alg-lev1sec5-A) would be extended to check, as
each new data item is added to the Data Table, whether its parent is an
ancestor of any other item of the same name, or if the parent of any
other item of the same name is in the stack. (When the parent is *Λ*, it
is everybody’s ancestor and always on the stack.)

On the other hand, if we leave [Algorithm
A](../Text/ch02c.html#ch02alg-lev1sec5-A) as it stands, the COBOL
programmer will get an error message from [Algorithm
B](../Text/ch02c.html#ch02alg-lev1sec5-B) when trying to use an illegal
item. Only $\tt MOVE\;CORRESPONDING$ can make use of such items without
error.

**<span
id="ch02ex_1_4_5a">[5](../Text/ch02c.html#ch02ex_1_4_5)</span>.** Make
these changes:

<div class="image">

![Image](../Images/605pro01.gif)

</div>

**<span
id="ch02ex_1_4_6a">[6](../Text/ch02c.html#ch02ex_1_4_6)</span>.** A
simple modification of [Algorithm
B](../Text/ch02c.html#ch02alg-lev1sec5-B) makes it search only for
complete references (if $k=n$ and ${\tt PARENT(S)}\neq\varLambda$ in
step B3, or if ${\tt NAME(S)}\neq P_k$ in step B6, set
$\tt P\gets PREV(P)$ and go to B2). The idea is to run through this
modified [Algorithm B](../Text/ch02c.html#ch02alg-lev1sec5-B) first;
then, if $\tt Q$ is *still* *Λ*, to perform the unmodified algorithm.

**<span
id="ch02ex_1_4_7a">[7](../Text/ch02c.html#ch02ex_1_4_7)</span>.**
`MOVE MONTH OF DATE OF SALES TO MONTH OF DATE OF PURCHASES. MOVE DAY OF DATE OF SALES TO DAY OF DATE OF PURCHASES. MOVE YEAR OF DATE OF SALES TO YEAR OF DATE OF PURCHASES. MOVE ITEM OF TRANSACTION OF SALES TO ITEM OF TRANSACTION OF PURCHASES. MOVE QUANTITY OF TRANSACTION OF SALES TO QUANTITY OF TRANSACTION OF PURCHASES. MOVE PRICE OF TRANSACTION OF SALES TO PRICE OF TRANSACTION OF PURCHASES`.
`MOVE TAX OF TRANSACTION OF SALES TO TAX OF TRANSACTION OF PURCHASES`.

**<span
id="ch02ex_1_4_8a">[8](../Text/ch02c.html#ch02ex_1_4_8)</span>.** If and
only if *α* or *β* is an elementary item. (It may be of interest to note
that the author failed to handle this case properly in his first draft
of [Algorithm C](../Text/ch02c.html#ch02alg-lev1sec5-C), and it actually
made the algorithm more complicated.)

**<span
id="ch02ex_1_4_9a">[9](../Text/ch02c.html#ch02ex_1_4_9)</span>.**
“$\tt MOVE\;CORRESPONDING\;\alpha\;TO\;\beta$”, if neither *α* nor *β*
is elementary, is equivalent to the set of statements
“${\tt MOVE\;CORRESPONDING}\;A\;{\tt OF\;\alpha\;TO}\;A\;\tt OF\;\beta$”
taken over all names *A* common to groups *α* and *β*. (This is a more
elegant way to state the definition than the more traditional and more
cumbersome definition of “$\tt MOVE\;CORRESPONDING$” given in the text.)
We may verify that [Algorithm C](../Text/ch02c.html#ch02alg-lev1sec5-C)
satisfies this definition, using an inductive proof that steps C2
through C5 will ultimately terminate with ${\tt P}=\tt P0$ and
${\tt Q}=\tt Q0$. Further details of the proof are filled in as we have
done many times before in a “tree induction” (see, for example, the
proof of [Algorithm 2.3.1T](../Text/ch02a.html#ch02alg-lev2sec7-T)).

**<span
id="ch02ex_1_4_10a">[10](../Text/ch02c.html#ch02ex_1_4_10)</span>.** (a)
Set ${\tt S1\gets LINK}(P_k)$. Then repeatedly set
${\tt S1\gets PREV(S1)}$ zero or more times until either
${\tt S1}=\varLambda({\tt NAME(S)}\neq P_k)$ or
${\tt S1}={\tt S}({\tt NAME(S)}=P_k)$. (b) Set $\tt P1\gets P$ and then
set ${\tt P1\gets PREV(P1)}$ zero or more times until
${\tt PREV(P1)}=\varLambda$; do a similar operation with variables
$\tt Q1$ and $\tt Q$; then test if ${\tt P1}=\tt Q1$. Alternatively, if
the Data Table entries are ordered so that ${\tt PREV(P)}\lt\tt P$ for
all $\tt P$, a faster test can be made in an obvious way depending on
whether ${\tt P}\gt\tt Q$ or not, following the $\tt PREV$ links of the
larger to see if the smaller is encountered.

**<span
id="ch02ex_1_4_11a">[11](../Text/ch02c.html#ch02ex_1_4_11)</span>.** A
minuscule improvement in the speed of step C4 would be achieved by
adding a new link field ${\tt SIB1(P)}\equiv{\tt CHILD(PARENT(P))}$.
More significantly, we could modify the $\tt CHILD$ and $\tt SIB$ links
so that ${\tt NAME(SIB(P))}\gt\tt NAME(P)$; this would speed up the
search in step C3 considerably because it would require only one pass
over each family to find the matching members. This change would
therefore remove the only “search” present in [Algorithm
C](../Text/ch02c.html#ch02alg-lev1sec5-C). [Algorithms
A](../Text/ch02c.html#ch02alg-lev1sec5-A) and
[C](../Text/ch02c.html#ch02alg-lev1sec5-C) are readily modified for this
interpretation, and the reader may find it an interesting exercise.
(However, if we consider the relative frequency of
$\tt MOVE\;CORRESPONDING$ statements and the usual size of family
groups, the resulting speedup will not be terribly significant in the
translation of actual COBOL programs.)

**<span
id="ch02ex_1_4_12a">[12](../Text/ch02c.html#ch02ex_1_4_12)</span>.**
Leave steps B1, B2, B3 unchanged; change the other steps thus:

**B4'.** Set $k\gets k+1$, ${\tt R\gets LINK(}P_k\tt)$.

**B5'.** If ${\tt R}=\varLambda$, set $\tt P\gets PREV(P)$ and go to B2'
(we haven’t found a match). If $R\lt{\tt S}\le\tt SCOPE(R)$, set
$\tt S\gets R$ and go to B3'. Otherwise set $\tt R\gets PREV(R)$ and
repeat step B5'. <span class="middle">![Image](../Images/box.gif)</span>

This algorithm does *not* adapt to the PL/I convention of [exercise
6](../Text/ch02c.html#ch02ex_1_4_6).

**<span
id="ch02ex_1_4_13a">[13](../Text/ch02c.html#ch02ex_1_4_13)</span>.** Use
the same algorithm, minus the operations that set $\tt NAME$,
$\tt PARENT$, $\tt CHILD$, and $\tt SIB$. Whenever removing the top
stack entry in step A5, set ${\tt SCOPE(P1)\gets Q}-1$. When the input
is exhausted in step A2, simply set ${\tt L}\gets0$ and continue, then
terminate the algorithm if ${\tt L}=0$ in step A7.

**<span
id="ch02ex_1_4_14a">[14](../Text/ch02c.html#ch02ex_1_4_14)</span>.** The
following algorithm, using an auxiliary stack, has steps numbered to
show a direct correspondence with the text’s algorithm.

**C1'.** Set $\tt P\gets P0$, $\tt Q\gets Q0$, and set the stack
contents empty.

**C2'.** If ${\tt SCOPE(P)}=\tt P$ or ${\tt SCOPE(Q)}=\tt Q$, output
$({\tt P},{\tt Q})$ as one of the desired pairs and go to C5'. Otherwise
put $({\tt P},{\tt Q})$ on the stack and set ${\tt P\gets P}+1$,
${\tt Q\gets Q}+1$.

**C3'.** Determine if $\tt P$ and $\tt Q$ point to entries with the same
name (see [exercise 10](../Text/ch02c.html#ch02ex_1_4_10)(b)). If so, go
to C2'. If not, let $({\tt P1},{\tt Q1})$ be the entry at the top of the
stack; if ${\tt SCOPE(Q)}\lt\tt SCOPE(Q1)$, set
${\tt Q\gets SCOPE(Q)}+1$ and repeat step C3'.

**C4'.** Let $({\tt P1},{\tt Q1})$ be the entry at the top of the stack.
If ${\tt SCOPE(P)}\lt\tt SCOPE(P1)$, set ${\tt P\gets SCOPE(P)}+1$,
${\tt Q\gets Q1}+1$, and go back to C3'. If
${\tt SCOPE(P)}=\tt SCOPE(P1)$, set $\tt P\gets P1$, $\tt Q\gets Q1$ and
remove the top entry of the stack.

**C5'.** If the stack is empty, the algorithm terminates. Otherwise go
to C4'. <span class="middle">![Image](../Images/box.gif)</span>

<div class="heading">

### Section 2.5 {#app01lev1sec6}

**<span
id="ch02ex_1_5_1a">[1](../Text/ch02c.html#ch02ex_1_5_1)</span>.** In
such fortuitous circumstances, a stack-like operation may be used as
follows: Let the memory pool area be locations 0 through ${\tt M}-1$,
and let $\tt AVAIL$ point to the lowest free location. To reserve
$\tt N$ words, report failure if ${\tt AVAIL}+{\tt N}\ge\tt M$,
otherwise set ${\tt AVAIL\gets AVAIL}+\tt N$. To free these $\tt N$
words, just set ${\tt AVAIL\gets AVAIL}-\tt N$.

</div>

Similarly, cyclic queue-like operation is appropriate for a
first-in-first-out discipline.

**<span
id="ch02ex_1_5_2a">[2](../Text/ch02c.html#ch02ex_1_5_2)</span>.** The
amount of storage space for an item of length *l* is
$k\lceil{l/(k-b)}\rceil$, which has the average value
$kL/(k-b)+(1-\alpha)k$, where *α* is assumed to be $1/2$, independent of
*k*. This expression is a minimum (for real values of *k*) when
$k=b+\sqrt{2bL}$. So choose *k* to be the integer just above or just
below this value, whichever gives the lowest value of
$kL/(k-b)+\left(\frac12\right)k$. For example, if $b=1$ and $L=10$, we
would choose $k\approx1+\sqrt{20}=5\;\rm or\;6$; both are equally good.
For much greater detail about this problem, see *JACM* **12** (1965),
53–70.

**<span
id="ch02ex_1_5_4a">[4](../Text/ch02c.html#ch02ex_1_5_4)</span>.**
$\rm rI1\equiv\tt Q$, $\rm rI2\equiv\tt P$.

<div class="image">

![Image](../Images/607pro01.gif)

</div>

**<span
id="ch02ex_1_5_5a">[5](../Text/ch02c.html#ch02ex_1_5_5)</span>.**
Probably not. The unavailable storage area just before location $\tt P$
will subsequently become available, and its length will be increased by
the amount $\tt K$; an increase of 99 would not be negligible.

**<span
id="ch02ex_1_5_6a">[6](../Text/ch02c.html#ch02ex_1_5_6)</span>.** The
idea is to try to search in different parts of the $\tt AVAIL$ list each
time. We can use a “roving pointer,” called $\tt ROVER$ for example,
which is treated as follows: In step A1, set $\tt Q\gets ROVER$. After
step A4, set ${\tt ROVER\gets LINK(Q)}$ if
${\tt LINK(Q)}\neq\varLambda$, otherwise set
${\tt ROVER\gets LOC(AVAIL)}$. In step A2, when ${\tt P}=\varLambda$ the
first time during a particular execution of [Algorithm
A](../Text/ch02c.html#ch02alg-lev1sec5-A), set ${\tt Q\gets LOC(AVAIL)}$
and repeat step A2. When ${\tt P}=\varLambda$ the *second* time, the
algorithm terminates unsuccessfully. In this way $\tt ROVER$ will tend
to <span id="page_608"></span>point to a random spot in the $\tt AVAIL$
list, and the sizes will be more balanced. At the beginning of the
program, set ${\tt ROVER\gets LOC(AVAIL)}$; it is *also* necessary to
set $\tt ROVER$ to $\tt LOC(AVAIL)$ everywhere else in the program where
the block whose address equals the current setting of $\tt ROVER$ is
taken out of the $\tt AVAIL$ list. (Sometimes, however, it is useful to
have small blocks at the beginning, as in the strict first-fit method;
for example, we might want to keep a sequential stack at the high end of
memory. In such cases we can reduce the search time by using trees as
suggested in exercise 6.2.3–30.)

**<span
id="ch02ex_1_5_7a">[7](../Text/ch02c.html#ch02ex_1_5_7)</span>.** 2000,
1000 with requests of sizes 800, 1300. [An example where worst-fit
succeeds, while best-fit fails, has been constructed by R. J. Weiland.]

**<span
id="ch02ex_1_5_8a">[8](../Text/ch02c.html#ch02ex_1_5_8)</span>.** In
step $A1''$, also set ${\tt M}\gets\infty$, ${\tt R}\gets\varLambda$. In
step $A2''$, if ${\tt P}=\varLambda$ go to $A6''$. In step $A3''$, go to
$A5''$ instead of to $A4''$. Add new steps as follows:

**A5''.** [Better fit?] If ${\tt M}\gt\tt SIZE(P)$, set $\tt R\gets Q$
and $\tt M\gets SIZE(P)$. Then set $\tt Q\gets P$ and return to $A2''$.

**A6''.** [Any found?] If ${\tt R}=\varLambda$, the algorithm terminates
unsuccessfully. Otherwise set $\tt Q\gets R$, $\tt P\gets LINK(Q)$, and
go to $A4''$. <span class="middle">![Image](../Images/box.gif)</span>

**<span
id="ch02ex_1_5_9a">[9](../Text/ch02c.html#ch02ex_1_5_9)</span>.**
Obviously if we are so lucky as to find ${\tt SIZE(P)}=\tt N$, we have a
best fit and it is not necessary to search farther. (When there are only
very few different block sizes, this occurs rather often.) If a
“boundary tag” method like [Algorithm
C](../Text/ch02c.html#ch02alg-lev1sec5-C) is being used, it is possible
to maintain the $\tt AVAIL$ list in sorted order by size; so the length
of search could be cut down to half the length of the list or less, on
the average. But the best solution is to make the $\tt AVAIL$ list into
a balanced tree structure as described in Section 6.2.3, if it is
expected to be long.

**<span
id="ch02ex_1_5_10a">[10](../Text/ch02c.html#ch02ex_1_5_10)</span>.**
Make the following changes:

Step B2, for “$\tt P\gt P0$” read “$\tt P\ge P0$”.

At the beginning of step B3, insert “If ${\tt P0}+\tt N\gt P$ and
$\tt P\neq\varLambda$, set
${\tt N}\gets\max({\tt N,P}+{\tt SIZE(P)-P0})$, $\tt P\gets LINK(P)$,
and repeat step B3.”

Step B4, for “${\tt Q}+{\tt SIZE(Q)}=\tt P0$”, read
“${\tt Q}+{\tt SIZE(Q)}\ge\tt P0$”; and for
“${\tt SIZE(Q)\gets SIZE(Q)}+\tt N$” read
“$\tt SIZE(Q)\gets\max(SIZE(Q),P0+N-Q)$”.

**<span
id="ch02ex_1_5_11a">[11](../Text/ch02c.html#ch02ex_1_5_11)</span>.** If
$\tt P0$ is greater than $\tt ROVER$, we can set $\tt Q\gets ROVER$
instead of ${\tt Q\gets LOC(AVAIL)}$ in step B1. If there are *n*
entries in the $\tt AVAIL$ list, the average number of iterations of
step B2 is $(2n+3)(n+2)/(6n+6)=\frac13 n+\frac56+O\left(\frac1n\right)$.
For example if $n=2$ we get 9 equally probable situations, where
$\tt P1$ and $\tt P2$ point to the two existing available blocks:

<div class="image">

![Image](../Images/e608_02.gif)

</div>

This chart shows the number of iterations needed in each case. The
average is

<div class="image">

![Image](../Images/e608_03.gif)

</div>

**<span
id="ch02ex_1_5_12a">[12](../Text/ch02c.html#ch02ex_1_5_12)</span>**.
**A1\*.** Set $\tt P\gets ROVER$, ${\tt F}\gets0$.

**A2\*.** If ${\tt P}=\tt LOC(AVAIL)$ and ${\tt F}=0$, set
$\tt P\gets AVAIL$, ${\tt F}\gets1$, and repeat step $A2*$. If
${\tt P}=\tt LOC(AVAIL)$ and ${\tt F}\neq0$, the algorithm terminates
unsuccessfully.

**A3\*.** If ${\tt SIZE(P)}\ge\tt N$, go to A4\*; otherwise set
$\tt P\gets LINK(P)$ and return to A2\*.

**A4\*.** Set ${\tt ROVER\gets LINK(P)}$, ${\tt K\gets SIZE(P)}-\tt N$.
If ${\tt K}\lt c$ (where *c* is a constant $\ge2$), set
${\tt LINK(LINK(P+1))\gets ROVER}$,
${\tt LINK(ROVER+1)\gets LINK(P+1)}$, $\tt L\gets P$; otherwise set
${\tt L\gets P}+\tt K$, ${\tt SIZE(P)\gets SIZE(L-1)\gets K}$,
${\tt TAG(L-1)}\gets “-”$, $\tt SIZE(L)\gets N$. Finally set
${\tt TAG(L)\gets TAG(L}+{\tt SIZE(L)-1)}\gets “+”$. <span
class="middle">![Image](../Images/box.gif)</span>

**<span
id="ch02ex_1_5_13a">[13](../Text/ch02c.html#ch02ex_1_5_13)</span>.**
$\rm rI1\equiv\tt P$, $rX\equiv\tt F$, $\rm rI2\equiv\tt L$.

<div class="image">

![Image](../Images/609pro01.gif)

</div>

<div class="image">

![Image](../Images/609pro01a.gif)

</div>

**<span
id="ch02ex_1_5_14a">[14](../Text/ch02c.html#ch02ex_1_5_14)</span>.** (a)
This field is needed to locate the beginning of the block, in step C2.
It could be replaced (perhaps to advantage) by a link to the first word
of the block. See also [exercise 19](../Text/ch02c.html#ch02ex_1_5_19).
(b) This field is needed because we sometimes need to reserve more than
$\tt N$ words (for example if ${\tt K}=1$), and the amount reserved must
be known when the block is subsequently freed.

**<span
id="ch02ex_1_5_15a">[15](../Text/ch02c.html#ch02ex_1_5_15)</span>, <span
id="ch02ex_1_5_16a">[16](../Text/ch02c.html#ch02ex_1_5_16)</span>.**
$\rm rI1\equiv\tt P0$, $\rm rI2\equiv\tt P1$, $\rm rI3\equiv\tt F$,
$\rm rI4\equiv\rm B$, $\rm rI6\equiv\tt-N$.

<div class="image">

![Image](../Images/610pro01.gif)

</div>

<div class="image">

![Image](../Images/610pro01a.gif)

</div>

**<span
id="ch02ex_1_5_17a">[17](../Text/ch02c.html#ch02ex_1_5_17)</span>.**
Both $\tt LINK$ fields equal to $\tt LOC(AVAIL)$.

**<span
id="ch02ex_1_5_18a">[18](../Text/ch02c.html#ch02ex_1_5_18)</span>.**
[Algorithm A](../Text/ch02c.html#ch02alg-lev1sec5-A) reserves the upper
end of a large block. When storage is completely available, the
first-fit method actually begins by reserving the high-order locations,
but once these become available again they are not re-reserved since a
fit is usually found already in the lower locations; thus the initial
large block at the lower end of memory quickly disappears with
first-fit. A large block rarely is the best fit, however, so the
best-fit method leaves a large block at the beginning of memory.

**<span
id="ch02ex_1_5_19a">[19](../Text/ch02c.html#ch02ex_1_5_19)</span>.** Use
the algorithm of [exercise 12](../Text/ch02c.html#ch02ex_1_5_12), except
delete the references to $\tt SIZE(L-1)$, $\tt TAG(L-1)$, and
${\tt TAG(L+SIZE(L)-1)}$ from step A4\*; also insert the following new
step between steps A2\* and A3\*:

**A2.5\*.** Set ${\tt P1\gets P}+\tt SIZE(P)$. If ${\tt TAG(P1)}=“+”$,
proceed to step A3. Otherwise set ${\tt P2\gets LINK(P1)}$,
${\tt LINK(P2+1)\gets LINK(P1+1)}$,
${\tt LINK(LINK(P1}+1{\tt))\gets P2}$,
${\tt SIZE(P)\gets SIZE(P)}+\tt SIZE(P1)$. If ${\tt ROVER}=\tt P1$, set
$\tt ROVER\gets P2$. Repeat step A2.5\*.

Clearly the situation of (*[2](../Text/ch02c.html#ch02eq-lev1sec5-2)*),
(*[3](../Text/ch02c.html#ch02eq-lev1sec5-3)*),
(*[4](../Text/ch02c.html#ch02eq-lev1sec5-4)*) can’t occur here; the only
real effect on storage allocation is that the search here will tend to
be longer than in [exercise 12](../Text/ch02c.html#ch02ex_1_5_12), and
sometimes $\tt K$ will be less than *c* although there is really another
available block preceding this one that we do not know about.

(An alternative is to take the collapsing out of the inner loop A3\*,
and to do the collapsing only in step A4\* before the final allocation
or in the inner loop when the algorithm would otherwise have terminated
unsuccessfully. This alternative requires a simulation study to see if
it is an improvement or not.)

[This method, with a few refinements, has proved to be quite
satisfactory in the implementations of $\rm\TeX$ and $\tt METAFONT$. See
*$\TeX$: The Program* (Addison–Wesley, 1986), §125.]

**<span
id="ch02ex_1_5_20a">[20](../Text/ch02c.html#ch02ex_1_5_20)</span>.**
When a buddy is found to be available, during the collapsing loop, we
want to remove that block from its ${\tt AVAIL[}k{\tt]}$ list, but we do
not know which links to update unless (i) we do a possibly long search,
or (ii) the list is doubly linked.

**<span
id="ch02ex_1_5_21a">[21](../Text/ch02c.html#ch02ex_1_5_21)</span>.** If
$n=2^k\alpha$, where $1\le\alpha\le2$, $a_n$ is
$2^{2k+1}\left(\alpha-\frac23\right)+\frac13$, and $b_n$ is
$2^{2k-1}\alpha^2+2^{k-1}\alpha$. The ratio $a_n/b_n$ for large *n* is
essentially ${4\left(\alpha-\frac23\right)}/\alpha^2$, which takes its
minimum value $\frac43$ when $\alpha=1\;\rm and\;2$, and its maximum
value $\frac32$ when $\alpha=1\frac13$. So $a_n/b_n$ approaches no
limit; it oscillates between these two extremes. The averaging methods
of Section 4.2.4 do, however, yield an average ratio of
$4(\ln2)^{-1}\int_1^2\left(\alpha-\frac23\right)d\alpha/\alpha^3=(\ln2)^{-1}\approx1.44$.

**<span
id="ch02ex_1_5_22a">[22](../Text/ch02c.html#ch02ex_1_5_22)</span>.**
This idea requires a $\tt TAG$ field in several words of the
$11\unicode{45}\rm word\;block$, not only in the first word. It is a
workable idea, if those extra $\tt TAG$ bits can be spared, and it would
appear to be especially suitable for use in computer hardware.

**<span
id="ch02ex_1_5_23a">[23](../Text/ch02c.html#ch02ex_1_5_23)</span>.**
011011110100; 011011100000.

**<span
id="ch02ex_1_5_24a">[24](../Text/ch02c.html#ch02ex_1_5_24)</span>.**
This would introduce a bug in the program; we may get to step S1 when
${\tt TAG(}0{\tt)}=1$, since S2 may return to S1. To make it work, add
“${\tt TAG(L)}\gets0$” after “$\tt L\gets P$” in step S2. (It is easier
to assume instead that ${\tt TAG(}2^m{\tt)}=0$.)

**<span
id="ch02ex_1_5_25a">[25](../Text/ch02c.html#ch02ex_1_5_25)</span>.** The
idea is absolutely correct. (Criticism need not be negative.) The list
heads ${\tt AVAIL[}k{\tt]}$ may be eliminated for $n\lt k\le m$; the
algorithms of the text may be used if “*m*” is changed to “*n*” in steps
R1, S1. The initial conditions
(*[13](../Text/ch02c.html#ch02eq-lev1sec5-13)*) and
(*[14](../Text/ch02c.html#ch02eq-lev1sec5-14)*) should be changed to
indicate $2^{m-n}$ blocks of size $2^n$ instead of one block of size
$2^m$.

**<span
id="ch02ex_1_5_26a">[26](../Text/ch02c.html#ch02ex_1_5_26)</span>.**
Using the binary representation of $\tt M$, we can easily modify the
initial conditions (*[13](../Text/ch02c.html#ch02eq-lev1sec5-13)*),
(*[14](../Text/ch02c.html#ch02eq-lev1sec5-14)*) so that all memory
locations are divided into blocks whose size is a power of two, with
blocks in decreasing order of size. In [Algorithm
S](../Text/ch02c.html#ch02alg-lev1sec5-S), $\tt TAG(P)$ should be
regarded as 0 whenever ${\tt P}\ge{\tt M}-2^k$.

**<span
id="ch02ex_1_5_27a">[27](../Text/ch02c.html#ch02ex_1_5_27)</span>.**
${\rm rI1}\equiv k$, ${\rm rI2}\equiv j$, ${\rm rI3}\equiv j-k$,
$\rm rI4\equiv\tt L$, ${\tt LOC(AVAIL[}j{\tt])}={\tt AVAIL}+j$; assume
that there is an auxiliary table ${\tt TWO[}j{\tt]}=2^j$, stored in
location ${\tt TWO}+j$, for $0\le j\le m$. Assume further that “+” and
“−” represent tags of 0 and 1, and that
${\tt TAG(LOC(AVAIL[}j{\tt]))}=“-”$; but
${\tt TAG(LOC(AVAIL[}m+1{\tt]))}=“+”$ is a sentinel.

<div class="image">

![Image](../Images/611pro01.gif)

</div>

<div id="page_612" class="image">

![Image](../Images/611pro01a.gif)

</div>

**<span
id="ch02ex_1_5_28a">[28](../Text/ch02c.html#ch02ex_1_5_28)</span>.**
${\rm rI1}\equiv k$, $\rm rI5\equiv\tt P$, $\rm rI4\equiv\tt L$; assume
${\tt TAG(}2^m{\tt)}=“+”$.

<div class="image">

![Image](../Images/612pro01.gif)

</div>

**<span
id="ch02ex_1_5_29a">[29](../Text/ch02c.html#ch02ex_1_5_29)</span>.**
Yes, but only at the expense of some searching, or (better) an
additional table of $\tt TAG$ bits packed somehow. (It is tempting to
suggest that buddies not be joined together during [Algorithm
S](../Text/ch02c.html#ch02alg-lev1sec5-S), but only in [Algorithm
R](../Text/ch02c.html#ch02alg-lev1sec5-R) if there is no block large
enough to meet the request; but that would probably lead to a badly
fragmented memory.)

**<span
id="ch02ex_1_5_31a">[31](../Text/ch02c.html#ch02ex_1_5_31)</span>.** See
David L. Russell, *SICOMP* **6** (1977), 607–621.

**<span
id="ch02ex_1_5_32a">[32](../Text/ch02c.html#ch02ex_1_5_32)</span>.**
Steven Crain points out that the method always frees all blocks and
starts afresh before 16667 units of time have elapsed; hence the stated
limit certainly exists. *Proof:* Let $u_n=n+t_n$, so that
$g_n=\left\lfloor\frac54\min(10000,f(u_{n-1}-n),f(u_{n-2}-n),\ldots,f(u_0-n))\right\rfloor$.
Let $x_0=0$ and $x_1=u_0$, and $x_{k+1}=\max(u_0\ldots,u_{x_{k-1}})$ for
$k\ge1$. If $x_k\gt x_{k-1}$ then

<div class="image">

![Image](../Images/e613_02.gif)

</div>

therefore <span class="middle">![Image](../Images/e613_03.gif)</span>,
and we must have $x_k=x_{k-1}$ before reaching time
$12500+\lfloor{12500/4}\rfloor+\lfloor{12500/4^2}\rfloor+\cdots$.

**<span
id="ch02ex_1_5_33a">[33](../Text/ch02c.html#ch02ex_1_5_33)</span>. G1.**
[Clear $\tt LINK\rm{s}$.] Set ${\tt P}\gets1$, and repeat the operation
${\tt LINK(P)}\gets\varLambda$, ${\tt P\gets P}+\tt SIZE(P)$ until
${\tt P}=\tt AVAIL$. (This merely sets the $\tt LINK$ field in the first
word of each node to *Λ*; we may assume in most cases that this step is
unnecessary, since $\tt LINK(P)$ is set to *Λ* in step G9 below and it
can be set to *Λ* by the storage allocator.)

**G2.** [Initialize marking phase.] Set $\tt TOP\gets USE$,
${\tt LINK(TOP)\gets AVAIL}$, $\tt LINK(AVAIL)\gets\varLambda$. (\\(\\tt
TOP\\) points to the top of a stack as in [Algorithm
2.3.5D](../Text/ch02c.html#ch02alg-lev2sec11-D).)

**G3.** [Pop up stack.] Set $\tt P\gets TOP$,
${\tt TOP\gets LINK(TOP)}$. If ${\tt TOP}=\varLambda$, go to G5.

**G4.** [Put new links on stack.] For $1\le k\le\tt T(P)$, do the
following operations: Set ${\tt Q\gets LINK(P}+k\tt)$; then if
${\tt Q}\neq\varLambda$ and ${\tt LINK(Q)}=\varLambda$, set
${\tt LINK(Q)\gets TOP}$, $\tt TOP\gets Q$. Then go back to G3.

**G5.** [Initialize next phase.] (Now ${\tt P}=\tt AVAIL$, and the
marking phase has been completed so that the first word of each
accessible node has a nonnull $\tt LINK$. Our next goal is to combine
adjacent inaccessible nodes, for speed in later steps, and to assign new
addresses to the accessible nodes.) Set ${\tt Q}\gets1$,
$\tt LINK(AVAIL)\gets Q$, ${\tt SIZE(AVAIL)}\gets0$, ${\tt P}\gets1$.
(Location $\tt AVAIL$ is being used as a sentinel to signify the end of
a loop in subsequent phases.)

**G6.** [Assign new addresses.] If ${\tt LINK(P)}=\varLambda$, go to G7.
Otherwise if ${\tt SIZE(P)}=0$, go to G8. Otherwise set
$\tt LINK(P)\gets Q$, ${\tt Q\gets Q}+\tt SIZE(P)$,
${\tt P\gets P}+\tt SIZE(P)$, and repeat this step.

**G7.** [Collapse available areas.] If
${\tt LINK(P}+{\tt SIZE(P))}=\varLambda$, increase $\tt SIZE(P)$ by
${\tt SIZE(P}+\tt SIZE(P))$ and repeat this step. Otherwise set
${\tt P\gets P}+\tt SIZE(P)$ and return to G6.

**G8.** [Translate all links.] (Now the $\tt LINK$ field in the first
word of each accessible node contains the address to which the node will
be moved.) Set ${\tt USE\gets LINK(USE)}$, and $\tt AVAIL\gets Q$. Then
set ${\tt P}\gets1$, and repeat the following operation until
${\tt SIZE(P)}=0$: If ${\tt LINK(P)}\neq\varLambda$, set
${\tt LINK(Q)\gets LINK(LINK(Q))}$ for all $\tt Q$ such that
${\tt P}\lt{\tt Q}\le{\tt P}+\tt T(P)$ and
${\tt LINK(Q)}\neq\varLambda$; then regardless of the value of
$\tt LINK(P)$, set ${\tt P\gets P}+\tt SIZE(P)$.

**G9.** [Move.] Set ${\tt P}\gets1$, and repeat the following operation
until ${\tt SIZE(P)}=0$: Set $\tt Q\gets LINK(P)$, and if
${\tt Q}\neq\varLambda$ set ${\tt LINK(P)}\gets\varLambda$ and
$\tt NODE(Q)\gets NODE(P)$; then whether ${\tt Q}=\varLambda$ or not,
set ${\tt P\gets P}+\tt SIZE(P)$. (The operation
${\tt NODE(Q)\gets NODE(P)}$ implies the movement of $\tt SIZE(P)$
words; we always have ${\tt Q}\le\tt P$, so it is safe to move the words
in order from smallest location to largest.) <span
class="middle">![Image](../Images/box.gif)</span>

[This method is called the “LISP 2 garbage collector.” An interesting
alternative, which does not require the $\tt LINK$ field at the
beginning of a node, can be based on the idea of linking together all
pointers that point to each node — see Lars-Erik Thorelli, *BIT* **16**
(1976), 426–441; R. B. K. Dewar and A. P. McCann, *Software Practice &
Exp.* **7** (1977), 95–113; F. Lockwood Morris, *CACM* **21** (1978),
662–665, **22** (1979), 571; H. B. M. Jonkers, *Inf. Proc. Letters*
**9** (1979), 26–30; J. J. Martin, *CACM* **25** (1982), 571–581; F.
Lockwood Morris, *Inf. Proc. Letters* **15** (1982), 139–142, **16**
(1983), 215. Other methods have been published by B. K. Haddon and W. M.
Waite, *Comp. J.* **10** (1967), 162–165; B. Wegbreit, *Comp. J.* **15**
(1972), 204–208; D. A. Zave, *Inf. Proc. Letters* **3** (1975), 167–169.
Cohen and Nicolau have analyzed four of these approaches in *ACM Trans.
Prog. Languages and Systems* **5** (1983), 532–553.]

**<span
id="ch02ex_1_5_34a">[34](../Text/ch02c.html#ch02ex_1_5_34)</span>.** Let
${\tt TOP}\equiv\rm rI1$, ${\tt Q}\equiv\rm rI2$,
${\tt P}\equiv\rm rI3$, $k\equiv\rm rI4$, ${\tt SIZE(P)}\equiv\rm rI5$.
Assume further that $\varLambda=0$, and ${\tt LINK(}0{\tt)}\neq0$ to
simplify step G4. Step G1 is omitted.

<div class="image">

![Image](../Images/614pro01.gif)

</div>

<div class="image">

![Image](../Images/614pro01_a.gif)

</div>

<div id="page_615" class="image">

![Image](../Images/614pro01a.gif)

</div>

<div class="image">

![Image](../Images/614pro01b.gif)

</div>

In line 66 we are assuming that the size of each node is sufficiently
small that it can be moved with a single $\tt MOVE$ instruction; this
seems a fair assumption for most cases when this kind of garbage
collection is applicable.

The total running time for this program is $(44a+17b+2w+25c+8d+47)u$,
where *a* is the number of accessible nodes, *b* is the number of link
fields therein, *c* is the number of inaccessible nodes that are *not*
preceded by an inaccessible node, *d* is the number of inaccessible
nodes that *are* preceded by an inaccessible node, and *w* is the total
number of words in the accessible nodes. If the memory contains *n*
nodes, with $\rho n$ of them <span id="page_616"></span>inaccessible,
then we may estimate $a=(1-\rho)n$, $c=(1-\rho)\rho n$, $d=\rho^2 n$.
Example: five-word nodes (on the average), with two link fields per node
(on the average), and a memory of 1000 nodes. Then when $\rho=0.2$, it
takes $374u$ per available node recovered; when $\rho=0.5$, it takes
$104u$; and when $\rho=0.8$, it takes only $33u$.

**<span
id="ch02ex_1_5_36a">[36](../Text/ch02c.html#ch02ex_1_5_36)</span>.** A
single customer will be able to sit in one of the sixteen seats
$1,3,4,6,\ldots,23$. If a pair enters, there must be room for them;
otherwise there are at least two people in seats $(1,2,3)$, at least two
in $(4,5,6),\ldots$, at least two in $(19,20,21)$, and at least one in
22 or 23, so at least fifteen people are already seated.

**<span
id="ch02ex_1_5_37a">[37](../Text/ch02c.html#ch02ex_1_5_37)</span>.**
First sixteen single males enter, and she seats them. There are 17 gaps
of empty seats between the occupied seats, counting one gap at each end,
with a gap of length zero assumed between adjacent occupied seats. The
total number of empty seats, namely the sum of all seventeen gaps, is 6.
Suppose *x* of the gaps are of odd length; then $6-x$ spaces are
available to seat pairs. (Note that $6-x$ is even and $\ge0$.) Now each
of the customers 1, 3, 5, 7, 9, 11, 13, 15, from left to right, who has
an even gap on both sides, finishes his lunch and walks out. Each odd
gap prevents at most one of these eight diners from leaving, hence at
least $8-x$ people leave. There *still* are only $6-x$ spaces available
to seat pairs. But now $(8-x)/2$ pairs enter.

**<span
id="ch02ex_1_5_38a">[38](../Text/ch02c.html#ch02ex_1_5_38)</span>.** The
arguments generalize readily; $N(n,2)=\lfloor{(3n-1)/2}\rfloor$ for
$n\ge1$. [When the hostess uses a first-fit strategy instead of an
optimal one, Robson has proved that the necessary and sufficient number
of seats is $\lfloor{(5n-2)/3}\rfloor$.]

**<span
id="ch02ex_1_5_39a">[39](../Text/ch02c.html#ch02ex_1_5_39)</span>.**
Divide memory into three independent regions of sizes $N(n_1,m)$,
$N(n_2,m)$, and $N(2m-2,m)$. To process a request for space, put each
block into the first region for which the stated capacity is not
exceeded, using the relevant optimum strategy for that region. This
cannot fail, for if we were unable to fill a request for *x* locations
we must have at least $(n_1-x+1)+(n_2-x+1)+(2m-x-1)\gt n_1+n_2-x$
locations already occupied.

Now if $f(n)=N(n,m)+N(2m-2,m)$, we have the subadditive law
$f(n_1+n_2)\le f(n_1)+f(n_2)$. Hence $\lim f(n)/n$ exists. (*Proof:*
$f(a+bc)\le f(a)+bf(c)$; hence
$\limsup_{n\to\infty}f(n)/n=max_{0\le a\lt c}\limsup_{b\to\infty}f(a+bc)/(a+bc)\le f(c)/c$
for all *c*; hence
$\limsup_{n\to\infty}f(n)/n\le\liminf_{n\to\infty}f(n)/n$). Therefore
$\lim N(n,m)/n$ exists.

[From [exercise 38](../Text/ch02c.html#ch02ex_1_5_38) we know that
$N(2)=\frac32$. The value $N(m)$ is not known for any $m\gt2$. It is not
difficult to show that the multiplicative factor for just two block
sizes, 1 and *b*, is $2-1/b$; hence $N(3)\ge1\frac23$. Robson’s methods
imply that $N(3)\le1\frac{11}{12}$, and $2\le N(4)\le2\frac16$.]

**<span
id="ch02ex_1_5_40a">[40](../Text/ch02c.html#ch02ex_1_5_40)</span>.**
Robson has proved that $N(2^r)\le1+r$, by using the following strategy:
Allocate to each block of size *k*, where $2^m\le k\lt2^{m+1}$, the
first available block of *k* locations starting at a multiple of $2^m$.

Let $N(\{b_1,b_2,\ldots,b_n\})$ denote the multiplicative factor when
all block sizes are constrained to lie in the set
$\{b_1,b_2,\ldots,b_n\}$, so that $N(n)=N(\{1,2,\ldots,n\})$. Robson and
S. Krogdahl have discovered that
$N(\{b_1,b_2,\ldots,b_n\})=n-(b_1/b_2+\cdots+b_{n-1}/b_n)$ whenever
$b_i$ is a multiple of $b_{i-1}$ for $1\lt i\le n$; indeed, Robson has
established the *exact* formula
$N(2^rm,\{1,2,4,\ldots,2^r\})=2^rm(1+\frac12r)-2^r+1$. Thus in
particular, $N(n)\ge1+\frac12\lfloor\lg n\lfloor$. He also has derived
the upper bound $N(n)\le1.1825\ln n+O(1)$, and he conjectures
tentatively that $N(n)=H_n$. This conjecture would follow if
$N(\{b_1,b_2,\ldots,b_n\})$ were equal to
$n-(b_1/b_2+\cdots+b_{n-1}/b_n)$ in general, but this is unfortunately
not the case since Robson has proved that $N(\{3,4\})\ge1\frac4{15}$.
(See *Inf. Proc. Letters* **2** (1973), 96–97; *JACM* **21** (1974),
491–499.)

**<span
id="ch02ex_1_5_41a">[41](../Text/ch02c.html#ch02ex_1_5_41)</span>.**
Consider maintaining the blocks of size $2^k$: The requests for sizes
$1,2,4,\ldots,2^{k-1}$ will periodically call for a new block of size
$2^k$ to be split, or a block of that size will be returned. We can
prove by induction on *k* that the total storage consumed by such split
blocks never exceeds $kn$; for after every request to split a block of
size $2^{k+1}$, we are using at most $kn$ locations in split
$2^k\unicode{45}\rm blocks$ and at most *n* locations in unsplit ones.

This argument can be strengthened to show that $a_rn$ cells suffice,
where $a_0=1$ and $a_k=1+a_{k-1}(1-2^{-k})$; we have

<div class="image">

![Image](../Images/e617_01.gif)

</div>

Conversely for $r\le5$ it can be shown that a buddy system sometimes
*requires* as many as $a_rn$ cells, if the mechanism of steps R1 and R2
is modified to choose the worst possible available
$2^j\unicode{45}\rm block$ to split instead of the first such block.

Robson’s proof that $N(2^r)\le1+r$ (see [exercise
40](../Text/ch02c.html#ch02ex_1_5_40)) is easily modified to show that
such a “leftmost” strategy will never need more than
$\left(1+\frac12r\right)n$ cells to allocate space for blocks of sizes
$1,2,4,\ldots,2^r$, since blocks of size $2^k$ will never be placed in
locations $\ge\left(1+\frac12k\right)$. Although his algorithm seems
very much like the buddy system, it turns out that no buddy system will
be this good, even if we modify steps R1 and R2 to choose the best
possible available $2^j\unicode{45}\rm block$ to split. For example,
consider the following sequence of “snapshots” of the memory, for $n=16$
and $r=3$:

<div class="image">

![Image](../Images/e617_04.gif)

</div>

Here 0 denotes an available location and *k* denotes the beginning of a
$k\unicode{45}\rm block$. In a similar way there is a sequence of
operations, whenever *n* is a multiple of 16, that forces
$\frac{3}{16}n$ blocks of size 8 to be $\frac18$ full, and another
$\frac{1}{16}n$ to be $\frac12$ full. If *n* is a multiple of 128, a
subsequent request for $\frac{9}{128}n$ blocks of size 8 will require
more than $2.5n$ memory cells. (The buddy system allows unwanted 1s to
creep into $\frac{3}{16}n$ of the $8\unicode{45}\rm blocks$, since there
are no other available 2s to be split at a crucial time; the “leftmost”
algorithm keeps all 1s confined.)

**<span
id="ch02ex_1_5_42a">[42](../Text/ch02c.html#ch02ex_1_5_42)</span>.** We
can assume that $m\ge6$. The main idea is to establish the occupancy
pattern $R_{m-2}(F_{m-3}R_1)^k$ at the beginning of the memory, for
$k=0,1,\ldots$, where $R_j$ and $F_j$ denote reserved and free blocks of
size *j*. The transition from *k* to $k+1$ begins with

<div class="image">

![Image](../Images/e617_08.gif)

</div>

then the commutation sequence
$F_{m-3}R_1F_mR_{m-5}R_1\to F_{m-3}R_1R_{m-2}R_2R_{m-5}R_1\to F_{2m-4}R_2R_{m-5}R_1\to R_mR_{m-5}R_1R_2R_{m-5}R_1\to F_mR_{m-5}R_1F_{m-3}R_1$
is used *k* times until we get
$F_mR_{m-5}R_1(F_{m-3}R_1)^k\to F_{2m-5}R_1(F_{m-3}R_1)^k\to R_{m-2}(F_{m-3}R_1)^{k+1}$.
Finally, when *k* gets large enough, there is an endgame that forces
overflow unless the memory size is at least $(n-4m+11)(m-2)$; details
appear in *Comp. J.* **20** (1977), <span id="page_618"></span>242–244.
[Notice that the worst conceivable worst case, which begins with the
pattern $F_{m-1}R_1F_{m-1}R_1F_{m-1}R_1\ldots$, is only slightly worse
than this; the next-fit strategy of [exercise
6](../Text/ch02c.html#ch02ex_1_5_6) can produce this pessimal pattern.]

**<span
id="ch02ex_1_5_43a">[43](../Text/ch02c.html#ch02ex_1_5_43)</span>.** We
will show that if $D_1,D_2,\ldots$ is any sequence of numbers such that
$D_1/m+D_2/(m+1)+\cdots+D_m/(2m-1)\ge1$ for all $m\ge1$, and if
$C_m=D_1/1+D_2/2+\cdots+D_m/m$, then $N_{FF}(n,m)\le nC_m$. In
particular, since

<div class="image">

![Image](../Images/e618_01.gif)

</div>

the constant sequence $D_m=1/\ln2$ satisfies the necessary conditions.
The proof is by induction on *m*. Let $N_j=nC_j$ for $j\ge1$, and
suppose that some request for a block of size *m* cannot be allocated in
the leftmost $N_m$ cells of memory. Then $m\gt1$. For $0\le j\lt m$, we
let $N'_j$ denote the rightmost position allocated to blocks of sizes
$\le j$, or 0 if all reserved blocks are larger than *j*; by induction
we have $N'_j\le N_j$. Furthermore we let $N'_m$ be the rightmost
occupied position $\le N_m$, so that $N'_m\ge N_m-m+1$. Then the
interval $(N'_{j-1}..N'_j]$ contains at least
$\lceil j(N'_j-N'_{j-1})/(m+j-1)\rceil$ occupied cells, since its free
blocks are of size $\lt m$ and its reserved blocks are of size $\ge j$.
It follows that $n-m\ge$ number of occupied cells
$\ge$$\sum_{j=1}^mj(N'_j-N'_{j-1})/(m+j-1)=mN'_m/(2m-1)-(m-1)$$\sum_{j=1}^{m-1}N'_j/(m+j)(m+j-1)\gt$$mN_m/(2m-1)-m-(m-1)$$\sum_{j=1}^{m-1}N_j(1/(m+j-1)-1/(m+j))=$$\sum_{j=1}^mnD_j/(m+j-1)-m\ge n-m$,
a contradiction.

[This proof establishes slightly more than was asked. If we define the
$D\rm\unicode{39}s$ by $D_1/m+\cdots+D_m/(2m-1)=1$, then the sequence
$C_1,C_2,\ldots$ is $1,\frac74,\frac{161}{72},\frac{7483}{2880},\ldots$;
and the result can be improved further, even in the case $m=2$, as in
[exercise 38](../Text/ch02c.html#ch02ex_1_5_38).]

**<span
id="ch02ex_1_5_44a">[44](../Text/ch02c.html#ch02ex_1_5_44)</span>.**
$\left\lceil F^{-1}(1/N)\right\rceil,\left\lceil F^{-1}(2/N)\right\rceil,\ldots,\left\lceil F^{-1}(N/N)\right\rceil$.
