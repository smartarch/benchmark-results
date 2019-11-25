---

warning if you are viewing this in bare repository links won't work please go the the https://smartarch.github.io/benchmark-results/: warning if you are viewing this in bare repository links won't work please go the the https://smartarch.github.io/benchmark-results/

permalink: /
---
## [Results of benchmarks](https://smartarch.github.io/benchmark-results/) 

This repository is a companion to the paper  "Managing Latency in Edge-Cloud Environment." We used 17 different benchmarks to create tasks that would simulate maximum usage on our platform. This data is then used in the predictor to predict worst-case scenarios (90% confidence level). 

All experiments were carried out on a 64-bit quad-core  [Intel Xeon E3-1230v6 @ 3.50GHz](https://ark.intel.com/content/www/us/en/ark/products/97474/intel-xeon-processor-e3-1230-v6-8m-cache-3-50-ghz.html) system running Fedora Linux 28 5. Hyper-threading, turbo-boost and other power management features were disabled to obtain stable timing
results.

The large testing was conducted and the results are presented here. The presented values are comparable within run of the single benchmark. We want to predict statistical boundaries so the total runtime suits us. The measurements of each benchmark without any background load is [here](./single). The presented results are of a many runs of the single benchmark in cycle. 

The page [doubles](./single_and_doubles) contains a complete coverage of state space of combination of a task and one background task. All tasks were measured with background load of each type of the benchmarks resulting in 289 (17*17) measurements.

Since this category might be already too large to be viewed in one figure the results were spitted to smaller chunks grouped by the main task. 

We measured as well the triples (2 background tasks), quadruples (3 background tasks) and quintuples (4 background tasks). The measurements in quintuples are already outside of the operation boundary as defined in the paper, since the number of running task over exceeds the number of available processor cores.

The space for triples and higher-level n-tuples is not covered entirely, but at least 1500 measurements of each category were produced. The following pages contain results for each of the tuples grouped by the measured task: [triple](./whole_triple/), [quadruple](./whole_quadruple/), [quintuple](./whole_quintuple/).

There are three categories of views for the data:

* [whole benchmark](./index_whole)
  * Contains the overall view for triples, quadruples and quintuples for a given task
* [multi tuple](./index_multi_tuple)
  * Provides deeper level view for triples, quadruples and quintuples for a given task
* [combination](./index_combination)
  * For each n-tuple contains view grouped by measured task