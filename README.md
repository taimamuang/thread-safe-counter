# thread-safe-counter

"MY OS environment is WSL 2"

<the performance measurement result>
mutex is faster than semaphore
- mutex
real    0m0.077s
user    0m0.068s
sys     0m0.059s
-semaphore
real    0m0.091s
user    0m0.092s
sys     0m0.065s

<my analysis>
mutex Blocks the calling thread and puts it to waiting queue. So, it does not waste the CPU time.
On the contrary, spin lock Loops continually checking the lock variable, wasting CPU time.
I think there are similar aspects between spin lock and semaphore.
