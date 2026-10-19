# Capacity and Performance

Learn to frame a bottleneck question before collecting more measurements.

## Choose a measurement method

| Open | What you can find | Access |
| --- | --- | --- |
| [Systems Performance](https://www.brendangregg.com/systems-performance-2nd-edition-book.html) | Brendan Gregg; study how to frame and investigate performance questions across a system. | Paid book; author material |
| [BPF Performance Tools](https://www.brendangregg.com/bpf-performance-tools-book.html) | Brendan Gregg; explore tracing tools when ordinary counters cannot explain a Linux performance question. | Paid book; Linux familiarity needed |
| [Brendan Gregg: Learning Linux performance](https://www.brendangregg.com/linuxperf.html) | Choose a performance method, visualization, or lecture around a question you can measure. | Free author material; linked books separate |
| [Operating Systems: Three Easy Pieces](https://pages.cs.wisc.edu/~remzi/OSTEP/) | Study operating-system concepts with free chapters and associated exercises. | Free online textbook |

## Focused references

**[The USE Method →](https://www.brendangregg.com/usemethod.html)**  
Use a measurement checklist to avoid collecting counters without a question.  
**Free author guide**

## Follow the tools

[k6](../04-tools-and-technologies/k6.md) · [Locust](../04-tools-and-technologies/locust.md) · [Apache JMeter](../04-tools-and-technologies/jmeter.md) · [Prometheus](../04-tools-and-technologies/prometheus.md)

## Put one idea to work

Run a small bounded test against an owned service and relate the load model to observed latency and resource use. Use the selected guide’s prerequisites and verification steps. Choose an owned or provided learning environment, keep sensitive data out of your notes, and remove the exercise resources when finished.

[Browse this collection](README.md) · [Directory homepage](../README.md)
