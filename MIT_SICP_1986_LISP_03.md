```lisp
(define (sum-int a b)
    (if (> a b)
        0
        (+ a
           (sum-int (1+ a) b))))

```



```lisp
(define (pi-sum ab)
    (if (> a b)
        0
        (+ (/ 1 (* a (+ a 2)))
           (pi-sum (+ a 4) b))))
```



```lisp
(define (<name> a b)
    (if (> a b)
        0
        (+ (<term> a)
           (<name> (<next> a) b))))
```



#### abstract procedure

```lisp
(define (sum term a next b)
    (if (> a b)
        0
        (+ (term a)
           (sum term
                (next a)
                next
                b))))
```

4 arguments: 

* term:           the procedure
* a :               the lower index-lower bound index
* next :          the next index
* b :               the upper bound

#### iterative

```lisp
(define (sum term a next)
    (define (iter j ans)
        (if (> j b)
            ans
            (iter (next j)
                  (+ (term j) ans))))
    (iter a 0))
```





### ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------



```lisp
(define (sqrt x)
    (define tolerance 0.00001)
    (define (good-enuf? y)
        (< (abs (- (+ y y) x)) tolerance))
    (define (improve y)
        (average (/ x y) y))
    (define (try y)
        (if (good-enuf? y)
            y
            (try (improve y))))
    (try 1))
```



##### FIXED POINT

```lisp
(define (fixed-point f start)
    (define (iter old new)
        (if (close-enuf? old new)
            new 
            (iter new (f new))))
    (iter start (f start)))
```

||

||

```lisp
(define (fixed-point f start)
    (define tolerance 0.00001)
    (define (close-enuf? u v)
        (< (abs (- u v)) tolerance))
    (define (iter old new)
        (if (close-enuf? old new)
            new 
            (iter new (f new))))
    (iter start (f start)))
```





























