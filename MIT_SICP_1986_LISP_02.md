### PEANO ARITHMETIC

#### TWO WAYS TO ADD WHOLE NUMBERS

1. ITERATION(迭代计算)

*  COMPLEXITY(复杂度)：
* * TIME = O(X)                    
  * SPACE = O(1) 

```lisp
(define (+ X Y )
        (if (= x 0)
            y
            (+ (-1+ x) (1+ y))))


(+ 3 4)
(+ 2 5)
(+ 1 6)
(+ 0 7)
7
```

2. LINEAR RECURSION(线性递归计算)

*  COMPLEXITY(复杂度)：
* * TIME = O(X)                    
  * SPACE = O(X) 

``` lisp
(define (+ x y)
    (if (= x 0)
        y
        (1+ (+ (-1+ x) y))))

(+ 3 4)
(1+ (+ 2 4))
(1+ (1+ (+ (1 4))))
(1+ (1+ (1+ (+ (0 4)))))
(1+ (1+ (1+ 4))))
(1+ (1+ 5))
(1+ 6)
7
```



### FIBONACCI NUMBERS

* time complexity = O(FIB(X))

* * ##### recursion tree ~~ 

```lisp
(define (fib n)
    (if (< n 2)
        n
        (+ (fib (- n 1))
           (fib (- n 2)))))


```

example : fib 5

​								fib5

​							/          \

​					fib4	            fib3

​		        /           \           /        \

​	        fib3          fib2   fib2        fib1

​		/           \

​    fib2           fib1

   /   \            /       \     

fib1  fib0     fib0     



### TOWERS OF HANOI 汉诺塔

I HAVE A BUNCH OF DISKS, I HAVE A BUNCH OF SPIKES,

AND IT'S RUMORED THAT SOMEWHERE IN THE ORIENT THERE IS A 64-HIGH TOWER,

AND THE JOB OF VARIOUS MONKS OF SOMETHING IS TO MOVE THESE SPIKES IN SOME COMPLICATED PATTERN

 SO EVENTUALLY THESE DISKS FORM ONE SPIKES TO OTHER

THEY CLAIM THAT THE UNIVERSE ENDS WHEN THIS IS DONE.

``` lisp
(define (move N from to spike)
    (cond ((= n 0) "done")
        (else
         (move (-1+ n) from spike to)
         (print-move from to)
         (move (-1+ n) spike to from))))
```























