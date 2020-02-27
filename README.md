# Zen kernel improvements

## CPU

- Tweaked CFS scheduler for lower latency. [7de2596b35ac1dbf55fb384f3d668a7315635c0b](https://github.com/zen-kernel/zen-kernel/commit/7de2596b35ac1dbf55fb384f3d668a7315635c0b)
  - Scheduling latency:   6    ->   4    ms
  - Minimal granularity:   0.75 ->   0.4  ms
  - Wakeup granularity:   1    ->   0.5  ms
  - CPU migration cost:   0.5  ->   0.25 ms
  - Bandwidth slice size:   5    ->   3    ms
  - Number of threads running:   8    ->   10

## RAM

- LZ4 compression algorithm for zswap instead of LZO. [90f3ec26286144951705914bec821254ce9e4b11](https://github.com/zen-kernel/zen-kernel/commit/90f3ec26286144951705914bec821254ce9e4b11) 

## IO

- [BFQ](https://www.kernel.org/doc/html/latest/block/bfq-iosched.html) (budget fair queueing) as default scheduler for multiqueue block devices. [07b36ce250f292fc4590cbadb4c5797c54f528b5](https://github.com/zen-kernel/zen-kernel/commit/07b36ce250f292fc4590cbadb4c5797c54f528b5)
