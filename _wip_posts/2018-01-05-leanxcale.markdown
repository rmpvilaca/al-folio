---
layout: post
title: LeanXcale
date: 2018-01-05 23:00:00
description: LeanXcale intro
---
 As you know I'm Query Engine Technical Director at [LeanXcale](http://www.leanxcale.com). In this post I want to give you a brief introduction
 about LeanXcale.
LeanXcale is a Hybrid Transaction/Analytical Processing Database (HTAP) NewSQL database that enables to blend of OLTP and OLAP workloads without compromising performance. LeanXcale enables to perform real-time analytical queries on operational data without the delay and cost of Extract-Transform-Load (ETL) from siloed operational and analytics datastores. 

Through its innovative cutting-edge research LeanXcale has been able to create a database accessible through both SQL and key-value interfaces giving the choice of rich flexible data access through an industry standard interface or ultra-fast data updates and lookups delivering enterprise class performance and scalability while lowering ownership costs.

LeanXcale has a scale-out distributed architecture that enables to scale out all its layers: storage, transactions, and query processing. All layers can scale to 100s of nodes and enable to reach many millions of update transactions per second. Briefly, LeanXcale, is composed of the storage layer, with Kivi distributed storage engine, the transactional layer and the query engine layer.

* [ZooKeeper](https://zookeeper.apache.org/) for general component's coordination.
* KiVi is an innovative distributed storage engine with a radically new design created to run efficiently on current multi-core and many-core NUMA architectures, while exploiting vectorial and SIMD capabilities of HW. The result is an ultra-efficient storage engine maximizing the throughput per core and thus, minimizing the HW footprint.
* Transaction Manager - The transction manager layer is based on a radically new approach with several subcomponents:
  - Configuration Manager that manages system configuration and deployment information. It also monitors the other components. 
  - Snapshot Server that provides and manages database snapshots. 
  - Conflict Manager that checks for conflicts among
          transactions. Multiple instances of this component can exist.
  - Commit Sequencer that determines the commit order for
          transactions.
  - LTM
* Query Engine is a enhanced version of [Apache Derby](https://db.apache.org/derby/) and provides the client entrypoint to the system via a regular JDBC connection. It provides a pool of instances that process ANSI SQL statements and transforms the SQL statements into query plans and, in turn the query plans use specialized scan operators for Kiv. Each instance preserves transactional contexts and coherence through the interface to the transaction manager layer.
Multiple instances of query engines are used both for high availability, ensuring that it is not a single point of failure, but also for scalability, to cope with a workload composed by a large number of concurrent transactions. Moreover, for elasticity, instances of DQE must be spawned and terminated dynamically while the system is running.

* Monitor Agent collects OS level and components monitoring data.
* Monitor Server based on Ganglia, aggregates and presents monitoring information
          through a Web console.
* Load Balancer to automatically manage partitions in the storage layer, Kivi
          regions. 

