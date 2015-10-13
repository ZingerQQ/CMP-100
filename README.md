# Tasuketsu
;piecesProduced: timeOfWork: number numberOfWorkers: number -> number
; takes an hour of the day between 6am and 6pm, in twenty-four hour format, along with the number of workers and computes the total number of pieces produced during that hour.

(check-expect (piecesProduced 15 10) 350)
(check-expect (piecesProduced 7  10) 300)
(check-expect (piecesProduced 11 10) 400)

         
(define (piecesProduced timeOfWork numberOfWorkers)
  (cond
   [(and (<= timeOfWork 10) (>= timeOfWork 6))  (* numberOfWorkers 30)]
   [(and (<= timeOfWork 14) (> timeOfWork 10)) (* numberOfWorkers 40)]
   [(and (<= timeOfWork 18) (> timeOfWork 14)) (* numberOfWorkers 35)]
   [else (error "invalid work time")]
   ))

(piecesProduced 0 10)


;newPrice: originalPrice: number weeksPassed: number -> number
;takes the initial price of an item and the number of weeks since the item was dated and produces the selling price of the item.

(check-expect (newPrice 1000 2))
