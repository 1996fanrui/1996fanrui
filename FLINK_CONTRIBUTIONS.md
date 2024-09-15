## My contributions to Flink 😄

In short, I contributed to a series of Flink optimizations and bugfixes that made `Unaligned Checkpoint`, 
`Watermark Alignment`， `FlameGraph` and `Large Operator` production-ready. 

In addition, I also contributed some FLIPs, such as:

- [FLIP-334](https://cwiki.apache.org/confluence/x/x4qzDw): Decoupling Autoscaler with Kubernetes Operator and build the [Autoscaler Standalone](https://nightlies.apache.org/flink/flink-kubernetes-operator-docs-release-1.7/docs/custom-resource/autoscaler/#autoscaler-standalone).
- [FLIP-364](https://cwiki.apache.org/confluence/x/uJqzDw): A series of improvements related to `Restart Strategy`.
- [FLIP-370](https://cwiki.apache.org/confluence/x/U56zDw): Support Balanced Tasks Scheduling (Cooperation).
- [FLIP-390](https://cwiki.apache.org/confluence/x/4guZE): Support System out and err to be redirected to LOG or discarded.

> Disclaimer: These features of Flink were not completed by me alone, but I was deeply involved in 
> the development of these features. The FLIPs and JIRAs mentioned below were developed by me.

### Checkpoint & State Backend 🤔

- _**Make `Unaligned Checkpoint` production-ready:**_
  - Support overdraft buffer. [FLIP-227](https://cwiki.apache.org/confluence/x/vBChD)
  - Timeout aligned to unaligned checkpoint barrier in the output buffers. [FLINK-27251](https://issues.apache.org/jira/browse/FLINK-27251)
  - Merge small ChannelState file for Unaligned Checkpoint. [FLINK-26803](https://issues.apache.org/jira/browse/FLINK-26803)
  - A series of improvements and bugfixes for Unaligned Checkpoint. [FLINK-28474](https://issues.apache.org/jira/browse/FLINK-28474), [FLINK-29730](https://issues.apache.org/jira/browse/FLINK-29730), [FLINK-31588](https://issues.apache.org/jira/browse/FLINK-31588), [FLINK-31959](https://issues.apache.org/jira/browse/FLINK-31959), [FLINK-32049](https://issues.apache.org/jira/browse/FLINK-32049)
- Fix the bug that the shared files will remain forever after the rocksdb incremental checkpoint exception. [FLINK-30461](https://issues.apache.org/jira/browse/FLINK-30461), [FLINK-30916](https://issues.apache.org/jira/browse/FLINK-30916)
- The tolerable-failed-checkpoints logic is invalid when checkpoint trigger failed.  [FLINK-26049](https://issues.apache.org/jira/browse/FLINK-26049)

### Autoscaler 👯

- Expanding the scope of Autoscaler
  - Decoupling Autoscaler with Kubernetes Operator. [FLIP-334](https://cwiki.apache.org/confluence/x/x4qzDw)
  - Build the [Autoscaler Standalone](https://nightlies.apache.org/flink/flink-kubernetes-operator-docs-release-1.7/docs/custom-resource/autoscaler/#autoscaler-standalone), it runs as a separate process. [FLINK-33099](https://issues.apache.org/jira/browse/FLINK-33099)
  - A series of improvements related to Autoscaler Standalone. [FLINK-33452](https://issues.apache.org/jira/browse/FLINK-33452)
- A series of improvements related to Autoscaler strategy
  - Avoid the frequent rescale [FLINK-36018](https://issues.apache.org/jira/browse/FLINK-36018)
  - Avoid the parallelism adjustment when the upstream shuffle type doesn't have keyBy [FLINK-34504](https://issues.apache.org/jira/browse/FLINK-34504)

### Scheduler 📫

- A series of improvements related to `Restart Strategy`. [FLIP-364](https://cwiki.apache.org/confluence/x/uJqzDw)
- Support Balanced Tasks Scheduling (Cooperation). [FLIP-370](https://cwiki.apache.org/confluence/x/U56zDw)
    - It's useful for TaskManager resource balancing.

### Stability 😄

- _**Make `Watermark Alignment` production-ready:**_
    - Performance improvement: Improve the watermark aggregation performance. [FLINK-32524](https://issues.apache.org/jira/browse/FLINK-32524)
    - A series of bugfixes for watermark alignment. [FLINK-32548](https://issues.apache.org/jira/browse/FLINK-32548)
- _**Make `Large Operator` production-ready.**_ [FLINK-33315](https://issues.apache.org/jira/browse/FLINK-33315)
    - Optimize the memory and CPU usage of large operators, greatly reducing the risk and probability of TaskManager OOM.
- Shuffle: Reuse tpc connections between taskmanagers. [FLINK-22643](https://issues.apache.org/jira/browse/FLINK-22643)
  - Fix the bug after enable TCP connection reuse across multiple jobs. [FLINK-28695](https://issues.apache.org/jira/browse/FLINK-28695)
- Support System out and err to be redirected to LOG or discarded. [FLIP-390](https://cwiki.apache.org/confluence/x/4guZE)
    - It is useful for controlling disk usage of Containers.

### Troubleshooting: _**Make `FlameGraph` production-ready**_ ⚡

- Support flamegraph at subtask level. [FLINK-30583](https://issues.apache.org/jira/browse/FLINK-30583)
- Improve the performance when collecting flamegraph at subtask level. [FLINK-30585](https://issues.apache.org/jira/browse/FLINK-30585)
- Allow trigger flamegraph when task is initializing [FLINK-33042](https://issues.apache.org/jira/browse/FLINK-33042)
- Fixed a couple of bugs related to FlameGraph: [FLINK-30250](https://issues.apache.org/jira/browse/FLINK-30250), [FLINK-30239](https://issues.apache.org/jira/browse/FLINK-30239)

### Flink release

Participated in several Flink and flink-kubernetes-operator releases, including:

- Flink 
  - 1.20.0 (The LTS version in the Flink 1.x)
  - 1.16.3
- flink-kubernetes-operator
  - 1.8.0
  - 1.7.0
  - 1.6.1

### Other contributions

The above are some core features and not up to date. Following are the whole contributions:

- 🌱 My [commits](https://github.com/apache/flink/commits?author=1996fanrui) to Apache Flink.
- 🤔 My [commits](https://github.com/apache/flink-kubernetes-operator/commits?author=1996fanrui) to Apache Flink Kubernetes Operator And Autoscaler.
