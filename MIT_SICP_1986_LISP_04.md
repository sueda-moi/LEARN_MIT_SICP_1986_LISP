```lisp
(cons x y)
```

  * constructs a pair whose first part is x and whose second part is y

```lisp
(car p)
```

  * selects the first part of the pair p

```lisp
(cdr p)
```

  * selects the second part of the pair p



```lisp
(define (make-rat n d)
    (let ((g (gcd n d)))
         (cons (/ n g)
               (/ d g))))
```



: defining +RAT without data abstraction

```lisp
(define (+rat x y)
    (cons (+ (* (car x) (cdr y))
             (* (car y) (cdr x)))
          (* (cdr x) (cdr y))))
```

