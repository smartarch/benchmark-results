---
warning if you are viewing this in bare repository links won't work please go the the https://smartarch.github.io/jss-2019-benchmark-results/: warning if you are viewing this in bare repository links won't work please go the the https://smartarch.github.io/jss-2019-benchmark-results/
permalink: /
---
## Introduction 

This repository is a companion to the paper  "Managing Latency in Edge-Cloud Environment." We used 17 different benchmarks to create tasks that would simulate maximum usage on our platform. This data is then used in the predictor to predict worst-case scenarios (90% confidence level). 

All experiments were carried out on a 64-bit quad-core  [Intel Xeon E3-1230v6 @ 3.50GHz](https://ark.intel.com/content/www/us/en/ark/products/97474/intel-xeon-processor-e3-1230-v6-8m-cache-3-50-ghz.html) system running Fedora Linux 28 5. Hyper-threading, turbo-boost and other power management features were disabled to obtain stable timing
results.

The large testing was conducted and the results are presented here. The evaluation comprises combinations of 17 benchmarks, which are listed in the table below.

| Benchmark ID | Source group | Benchmark description |
|  ---- | ---- | ---- |
| A | scalabench | Renders a set of images using ray tracing |
| F | scalabench | In-memory benchmark of transactions in banking application |
| H | scalabench | Framework to optimize ABC, SWC, and SWF files |
| K | scalabench | Stanford Topic Modeling Toolbox |
| O | scalabench | Simulates programs run on a grid of AVR microcontrollers |
| SMATRIX | stress-ng | Transposition on a 4096x4096 matrix |
| JSOND | own | Generates and writes JSON data to disk |
| PDFD | own | Generates images and writes them as PDF file to disk |
| SORTD | own | Generates, sorts and writes random numbers to disk |
| CYPHERD | own | Generates random string, cyphers it and writes to disk |
| AVL | own | Inserts and then removes 1 000 000 items to AVL tree |
| RB | own | Inserts and then removes 1 000 000 items to Red--Black tree |
| FLOYD | own | Floyd-Warshall's all pairs shortest path search on 2 200 vertices |
| ROD | own | Rod cutting problem using dynamic programming |
| EGG | own | Egg dropping problem using dynamic programming |
| FACE | own | Human faces detection in images from the local directory |
| ZB | own | Zip archive extraction of compressed folder with many small files |

## Results

The measurements of each benchmark without any background load is [here](./single). This establishes the baseline for further measurements in combinations. The presented results are of a many runs of the single benchmark in cycle. 

The page [doubles](./single_and_doubles) contains all pairs of a task and one background task -- this resulted in 289 (17*17) measurements. Since this category is already too large to be viewed in one figure the results were spitted to smaller chunks grouped by the main task. 

We also measured the triples (2 background tasks), quadruples (3 background tasks) and quintuples (4 background tasks). The measurements in quintuples are already outside of the operation boundary as defined in the paper, since the number of running task over exceeds the number of available processor cores.

The product space of triples and higher-level n-tuples is not covered entirely, but at least 1500 measurements of each category were produced. The following pages contain results for each of the tuples grouped by the measured task: .

There are four different views on the data:
* Grouped by tasks concurenty executed
    * [triple](./whole_triple/)
    * [quadruple](./whole_quadruple/)
    * [quintuple](./whole_quintuple/)
* [Overall view for triples, quadruples and quintuples for a given task](./index_whole)
* [Detailed view for triples, quadruples and quintuples per task](./index_multi_tuple)
* [For each n-tuple contains view grouped by measured task](./index_combination)
