# Apache JMeter

<a href="https://jmeter.apache.org/usermanual/index.html"><img src="../assets/tool-jmeter.svg" alt="Apache JMeter source reference" width="48" height="48"/></a>

Choose a small test plan whose threads, requests, and results you can interpret.

## Start with these

**[JMeter building a web test plan →](https://jmeter.apache.org/usermanual/build-web-test-plan.html)**  
Follow the documented test-plan structure before adding many listeners.  
**Free documentation · Exercise setup and permissions vary**

[Apache JMeter reference](https://jmeter.apache.org/usermanual/index.html) · [Source and project material](https://github.com/apache/jmeter)

## Watch and understand

[FOSDEM video archive →](https://video.fosdem.org/)  
**Broader teaching or talk catalog**

## Longer reading

[Systems Performance →](https://www.brendangregg.com/systems-performance-2nd-edition-book.html) · **Paid book; author material**

## Try a small task

Exercise one endpoint on an owned test service with bounded concurrency.

**Keep:** The test plan and results tied to its configured load.

**Setup:** owned target, bounded load or fault, explicit stop condition. **Cleanup:** stop generators, undo faults, and verify recovery.

**Related discoveries:** [k6](k6.md) · [Locust](locust.md)

[Browse this collection](README.md) · [Directory homepage](../README.md)
