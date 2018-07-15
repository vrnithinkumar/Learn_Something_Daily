# Notation
Type theory studies things called `types`(represented by **T**), which can be thought of as sets. The analog of elements of a set are called `terms`(represented by **t**).
- `t : A` to indicate that t is a term of type A.
- `A : Type` to indicate A is of type.

The set of all terms is often denoted by `τ`. It is not same as `T`.

A `judgement` is a string of symbols that may or may not be provable from the rules of type theory. A judgement always contains the turnstile symbol `⊢`, separating context from the conclusion. `P⊢Q` reads like from P we can conclude Q.
- `⊢ 0:N`  -> 0 belong to N with nothing given
- `x : N, y : N ⊢ x + y : N` -> given x and y of type N x+y is of same type N

t_1 → t_2, which should be read as t_1 evaluates to t_2. This is also known as a `judgement`. The → represents a single evaluation step. If you see t_1  →* t_2 then this means by repeated application of single-step evaluations, t_1 eventually evaluates to t_2.

### Evaluation rules
![Alternate image text](https://s0.wp.com/latex.php?latex=%5Cdisplaystyle+%5Cfrac%7Bt_1%5C++%5Crightarrow+t%27_%7B1%7D%7D%7B%5Cmathrm%7Bif%7D%5C++t_1%5C++%5Cmathrm%7Bthen%7D%5C++t_2%5C++%5Cmathrm%7Belse%7D%5C++t_3+%5Crightarrow+%5Cmathrm%7Bif%7D%5C++t%27_1%5C++%5Cmathrm%7Bthen%7D%5C++t_2%5C++%5Cmathrm%7Belse%7D%5C++t_3%7D&bg=ffffff&fg=333333&s=0) 

This can be interpreted as *'Given the things **above the line**, then we can conclude the thing **below the line.**'*

### Lambda abstraction 
λx.t with type we can represent as ![Alternate image text](https://s0.wp.com/latex.php?latex=%5Clambda+x%3A%5Cmathrm%7BT_1%7D+.+t_2&bg=ffffff&fg=333333&s=0)
We can abstract the info of given parameter of type will return a value of different type as  "![Alternate image text](https://s0.wp.com/latex.php?latex=%5Cmathrm%7BT_1%7D%5C+%5Crightarrow%5C+%5Cmathrm%7BT_2%7D&bg=ffffff&fg=333333&s=0)".

### Typing context or typing environment)
It is some context of environment for keeping track of all free terms/variable and their type. It is a mapping between variable names to types.

- `Γ ⊢ t : T` From the typing context `Γ` it concluds that term `t` has type `T`. 
- `Γ , x : T` Typing context `Γ` is extended with the new information about `x` has type `T`. 

### *Example*
![Alternate image text](https://s0.wp.com/latex.php?latex=%5Cdisplaystyle+%5Cfrac%7B%5CGamma%2C+x+%3A+%5Cmathrm%7BT_1%7D+%5Cvdash+t_2+%3A+%5Cmathrm%7BT_2%7D%7D%7B%5CGamma+%5Cvdash+%5Clambda+x%3A%5Cmathrm%7BT-1%7D.t_2+%3A+%5Cmathrm%7BT_1%7D+%5Crightarrow+%5Cmathrm%7BT_2%7D%7D&bg=ffffff&fg=333333&s=0)

It can be read as “If from a typing context `Γ` with x bound to T1 it follows that t2 has type T2, then in the same typing context `Γ` the expression ![Alternate image text](https://s0.wp.com/latex.php?latex=%5Clambda+x%3A%5Cmathrm%7BT_1%7D.t_2&bg=ffffff&fg=333333&s=0) has the type ![Alternate image text](https://s0.wp.com/latex.php?latex=%5Cmathrm%7BT_1%7D+%5Crightarrow+%5Cmathrm%7BT_2%7D&bg=ffffff&fg=333333&s=0).
## Symbols
###  &#8866; (Turnstile)
Read as "yields", "proves", "satisfies" or "entails"
[More details](https://en.wikipedia.org/wiki/Turnstile_(symbol))
### Γ (Gamma)
### Σ (Sigma)
### τ (Tau)

## Reference
1. [Greek alphabet](https://en.wikipedia.org/wiki/Greek_alphabet#Letters)
2. [A practitioner’s guide to reading programming languages papers](https://blog.acolyer.org/2018/01/26/a-practitioners-guide-to-reading-programming-languages-papers/)
3. [An Introduction to Type Theory](https://pdfs.semanticscholar.org/presentation/7552/f96072bbeeeca9ba5719eb364d5fd54939b2.pdf)
