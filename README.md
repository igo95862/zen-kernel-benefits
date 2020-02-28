# Zen kernel improvements

## CPU

- Tweaked CFS scheduler for lower latency. [7de2596b35ac1dbf55fb384f3d668a7315635c0b](https://github.com/zen-kernel/zen-kernel/commit/7de2596b35ac1dbf55fb384f3d668a7315635c0b)
  - Scheduling latency:   6    ->   4    ms
  - Minimal granularity:   0.75 ->   0.4  ms
  - Wakeup granularity:   1    ->   0.5  ms
  - CPU migration cost:   0.5  ->   0.25 ms
  - Bandwidth slice size:   5    ->   3    ms
  - Number of threads running:   8    ->   10
  
- Forced [interrupt request](https://en.wikipedia.org/wiki/Interrupt_request_(PC_architecture)) threading by default. [e9a38f81725b3024defed48f6f3efbbd622c2746](https://github.com/zen-kernel/zen-kernel/commit/e9a38f81725b3024defed48f6f3efbbd622c2746)

- Tweaked on-demand scheduler. [070b844e9e5485b8c14c85ae48747157893df148](https://github.com/zen-kernel/zen-kernel/commit/070b844e9e5485b8c14c85ae48747157893df148)
  - Samping down factor: 1 -> 5

### MuQSS
MuQSS is not enabled by default. Can be enabled with CONFIG_SCHED_MUQSS variable.

- Disable yielding as it caused performance issues. [ac994d428ce6eaa4c05a2b4a2083a32fcc55c682](https://github.com/zen-kernel/zen-kernel/commit/ac994d428ce6eaa4c05a2b4a2083a32fcc55c682)
- Reduced the cpu percentage that isochronous processes (SCHED_ISO) can use. [ec2c919523eb93f34178b8df17d3351990d31907](https://github.com/zen-kernel/zen-kernel/commit/ec2c919523eb93f34178b8df17d3351990d31907)
  - Isochronous processes allowed time: 70% -> 25%
- Round robin time reduced. [07224ba0c5d52ac05a08c28705f2578468e7a5be](https://github.com/zen-kernel/zen-kernel/commit/07224ba0c5d52ac05a08c28705f2578468e7a5be)
  - Round robin interval: 6 ms -> 2 ms

- Tweaked on-demand scheduler. [070b844e9e5485b8c14c85ae48747157893df148](https://github.com/zen-kernel/zen-kernel/commit/070b844e9e5485b8c14c85ae48747157893df148)
  - Samping down factor: 1 -> 5
  - Frequency up threshold: 95 -> 45
  - Micro frequency up threshold: 80 -> 40
  
- MuQSS tweeks documentation updated. [add8f00727055356b90337313a23a3992e547d8d](https://github.com/zen-kernel/zen-kernel/commit/add8f00727055356b90337313a23a3992e547d8d)

## RAM

- LZ4 compression algorithm for zswap instead of LZO. [90f3ec26286144951705914bec821254ce9e4b11](https://github.com/zen-kernel/zen-kernel/commit/90f3ec26286144951705914bec821254ce9e4b11) 

- [zswap](https://wiki.archlinux.org/index.php/Zswap) enabled by default. [7444df2ac4e2c4b47cfc5c6b1b64f54eb09e3800](https://github.com/zen-kernel/zen-kernel/commit/7444df2ac4e2c4b47cfc5c6b1b64f54eb09e3800)

- [z3fold](https://www.kernel.org/doc/html/latest/vm/z3fold.html) is now default compression allocator with stronger compression. [4eab5c9ea4fd3e6595b664a429869f4611fad7d4](https://github.com/zen-kernel/zen-kernel/commit/4eab5c9ea4fd3e6595b664a429869f4611fad7d4)

## IO

- [BFQ](https://www.kernel.org/doc/html/latest/block/bfq-iosched.html) (budget fair queueing) as default scheduler for multiqueue block devices. [07b36ce250f292fc4590cbadb4c5797c54f528b5](https://github.com/zen-kernel/zen-kernel/commit/07b36ce250f292fc4590cbadb4c5797c54f528b5)

## Drivers

- Virtual (SCSI) Host Bus Adapter (VHBA) driver added. Allows to emulate CD/DVD devices. [ae2bd58fe11e9963d350cfd031da934231435e24](https://github.com/zen-kernel/zen-kernel/commit/ae2bd58fe11e9963d350cfd031da934231435e24)

## Misc

- Allowed O3 level of optimizations outside of [ARC](https://en.wikipedia.org/wiki/ARC_(processor)) architecture. [8e4c45742cfca87c0cc44e7969ab8826be9139be](https://github.com/zen-kernel/zen-kernel/commit/8e4c45742cfca87c0cc44e7969ab8826be9139be)

## Uncategorized

