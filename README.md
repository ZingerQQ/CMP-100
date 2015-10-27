# Tasuketsu
;intervalSumHELPER: number number number -> number
;Computes the sum of the numbers in the given numbers interval

(check-expect (intervalSum 0 10) 55)
(check-expect (intervalSum -5 5) 0 )

(define (intervalSumHELPER firstValue secondValue accumulatingAnswer)
 (cond
  [(> firstValue secondValue) accumulatingAnswer]
  [else (intervalSumHELPER (+ firstValue 1) secondValue (+ firstValue accumulatingAnswer))]
 )
)

(define (intervalSum firstValue secondValue)
 (cond
  [(= firstValue secondValue) (error "No Interval")]
  [else (intervalSumHELPER firstValue secondValue 0)]
 )
)  
