# Spark Overview

1. What does the rest of this module look like?
2. Context -- when / where is spark relevant?
    - When would I work with spark? When it's already setup
    - Big Data
        - Volume: outside of HDD
            - storage (HDD) vs memory (RAM)
                - short vs long-term memory
        - Variety: can't be stored in a traditional database
        - Velocity (Spark Streaming)
        - Veracity (missing data)
        - 4 Vs (Volume, Veracity, Velocity, Variety)
        - alternative: dask
3. Spark Architecture
    - Spark is written in Scala, which runs on the JVM
    - client libraries written in many PL
    - all client code ends up as the same spark code
    - Java Stack Traces
    - A *Spark Cluster* runs in the cloud
    - a cluster consists of multiple *nodes*
    - Master / Cluster Manager
    - Drivers run *applications*, which consist of *jobs* and *tasks*
    - We'll run spark in Local Mode
4. Working in parallel
    - faster at scale, but constant overhead
    - two levels: executors and partitions (# partitions = # cpus)
5. Spark DataFrames
    - abstraction of the above
    - lazy: doesn't do work until it has to
        - efficient
        - example
            1. Just dinner
            1. size > 3
            1. calculate tip percentage (tip / total_bill)
            1. total_bill / party_size
        - **transformations** and **actions**
    - shuffle: data from different partitions
        - non-shuffles: arithmetic with columns, filters
        - shuffle: sort, groupby
