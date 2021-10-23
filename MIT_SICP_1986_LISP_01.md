

## 1. BEGIN

### 1.1. 

```lisp
(DEFINE (SOS X Y)
        (+ (SQ X) (SQ Y)))
(DEFINE (SQ X)
        (* X X))
(SOS 3 4)  
```

output :25

#### 1.1.1. KINDS OF EXPRESSIONS

* 1.1.1.1. NUMBERS

* 1.1.1.2. SYMBOLS

* 1.1.1.3. λ-EXPRESSIONS

* 1.1.1.4. DEFINITIONS

* 1.1.1.5. CONDITIONALS

* 1.1.1.6. COMBINATIONS

### 1.2. substitution model 

* simplest model that we have for understanding how procedures work and how processes work

to understand process and how we control them then we have to have a mapping from mechanisms of this procedure into the way in which these processes behave.

get

formal or semi-formal mechanical model  = 正式或半正式的机械的模型

#### 1.2.2 SUBSTITUTION RULE

to **evaluate** an application

* **evaluate** the operator to get procedure

* **evaluate** the operands to get arguments

* apply the procedure to the arguments
  * copy the body of the procedure
    * substituting the arguments supplied for the formal parameters of the procedure
  * evaluate the resulting new body

**THE KEY TO UNDERSTANDING COMPLICATED THINGS IS TO KNOW WHAT NOT TO LOOK AT AND WHAT NOT COMPUTE AND WHAT NOT TO THINK.**



### CONDITIONALS

to evaluate an IF expression 

 * EVALUATE the predicate expression
     * IF it yields TRUE
       	* evaluate the consequent expression
    * otherwise
       * evaluate the alternative expression

```
(IF <predicate>  // 判断表达式 
	<consequent> // 结果表达式
	<alternative>// 选择表达式
)
```

```lisp
(DEFINE (+ X Y)
        (IF (= X 0)
            Y
            (+ (-1+ X) (1+ Y))))
```

```lisp
(+ 3 4)
(if (= 3 0) 4 (+ (-1+ 3) (1+ 4)))
(+ (-1+ 3) (1+ 4))
(+ (-1+ 3) 5)
(+ 2 5)
(if (= 2 0) 5 (+ (-1+ 2) (1+ 5)))
(+ (-1+ 2) (1+ 5))
(+ (-1+ 2) 6)
(+ 1 6)
(if (= 1 0) 6 (+ (-1+ 1) (1+ 6)))
(+ (-1+ 1) (1+ 6))
(+ (-1+ 1) 7)
(+ 0 7)
(if (= 0 0) 7 (+ (-1+ 0) (1+ 7)))
7
// 过程大概就是双方数字的底层运算要一直换算到0
```



(题外话：windows - lisp的安装环境好难，点进官网都找不到网上搜索的资源里说到的exe安装包，好不容易在目录里翻了翻找到了windows的zip包，解压出来根本用不了。2010年之后再无更新的官网。虽然说lisp很酷，但是果然如果缺乏商业和市场的助推力，一个语言的维护环境会大打折扣。)













