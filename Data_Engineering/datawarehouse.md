# Data Warehousing Techniques

# Fact Tables
+ Types of Fact Tables
  - Transaction
  - Periodic Snapshot
  - Accumulating Snapshot

## Transaction Fact Table
Tracks the individual activities that define a business process and supports 
several facts that describe these activities. It can provide rich analytic 
possibilities, and often serves as a granular repository of atomic data.

## Snapshot Fact Table
Periodically samples status measurements such as balances or levels. These 
measurements may be equivalent to the cumulative effect of a series of 
transactions but are not easy to study in that format. Some status measurements, 
such as temperature, cannot be modeled as transactions at all.

## Accumulating Snapshot
Used to track the progress of an individual item through a series of processing 
steps. It enables the study of elapsed time between major process milestones or 
events. This kind of fact table correlates several different activities in a 
single row.

## Hierarchies
Different types of hierarchies.
* Balanced  Hierarchy (Standard) - Contains a fixed number of levels.
  * Attribute Hierarchies - a set of mandatory parent-child relationships among 
    subsets of attributes. All attribute hierarchies are balanced.
* Unbalanced (Variable Depth) Hierarchy
  * Instance Hierarchies - relationships between rows of the dimension. These 
    are recursive. Instance hierarchies are usually unbalanced but they won't 
    always be unbalanced. You can use recursive SQL to query these types of 
    hierarchies. You can also flatten the hierarchy or create a bridge table
    to more easily look up or down the hierarchy.
* Ragged

## Data Profile
### Slow Change Data
* Type 1 - Use when history of the data element is not significant. When data in
  your source system changes you simply update the data and overwrite the
  previous value.
* Type 2 - Use when you need to preserve the historic context of facts. When the
  source data changes then a new row is added to the table so the previous
  version remains unchanged.
* Type 3
* Frozen
* Time-stamped dimensions - used for point in time analysis.
* Hybrid Techniques
