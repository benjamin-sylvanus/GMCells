# Algorithm Overview

## Overview

<figure><img src="../../.gitbook/assets/Fixcell (1).svg" alt=""><figcaption><p>Algorithm Outline</p></figcaption></figure>

The high level outline is rather straightforward. The bulk of the work done is dependent on graph and network algorithms relating to paths and spanning trees. \


### Create a Graph from an SWC

* Nodes: \[Id,x,y,z,r];
* Edges: \[childId,parentId];
* Graph: \[Nodes, Edges];

### Prune Tree

High resolution EM data such as data obtained from H01 yields complex trees. On larger cells the underlying backbone is obstructed by small branches. We remove these appendages for now.

* Remove Degree 1 nodes iteratively&#x20;
* Store Appendages (for later use)

{% hint style="info" %}
Node Degree in an undirected graph is a common metric for Nodes. For any node n its degree is equal its number of edges.&#x20;

For a well formed swc file nodes should have degree 1 or 2 and the total number of edges = total number of nodes - 1.
{% endhint %}

### Determine Breakpoints

Using the backbone graph we generated from pruning we can identify candidate breakpoints as the Degree 1 Nodes.&#x20;

### Calculate the Global and Local Directions

Each breakpoint belongs to a branch of our tree. The global direction is a vector the defines the general direction a branch is traveling with respect to the soma. It helps us classify what type of connection we are looking for. There are two types:&#x20;

A branch is already connected to the main branch and is looking for a connection to an unconnected branch. Or a branch is disconnected and is looking for a connection to the main branch.&#x20;

Using the global direction as frame of reference we can determine the localized direction of each breaking point.&#x20;

### Determine Candidate Connections

Connections are made based on the distance and angle between breaking points. We create a weighted score of each breaking point and set our candidates for each breaking point as the connections with scores above a dynamic threshold.&#x20;

### Select a Connection

We prioritize connections close to the soma. This ensures multi level break points don't miss segments.&#x20;

### Validity Check

We repeat the selection procedure until our graph is fully connected.
