# PlumberJoe
PlumberJoe is a utility to create a compute graph out of individual compute units. 

Basic Representation:

Each compute node is takes a source uri (pointing to data, including null) and does some processing and writes to a sink (including a null).

If a compute node's source uri maps to any sink uri of another node, then there will be a directed edge drawn between source node to sink node.

Schema:

Each compute node needs to have the following:

source.uri: a unique pointer to source data. can be a list
sink.uri: a unique pointer to sink data. can be a list
config: optional parameters passed to the executing environment
cmd: the (shell) script that processes source data and produces sink data by executing a script which can be configured by the config file


To Do:

Services planned out of this representation:

1. Representation: Create a Directed Graph out of multiple compute node specs
2. Validity: Check if a compute graph is a DAG
3. Deployement: Generate a executable glue shell script that lays down the pipeline 
4. Audit: Relauch a pipeline and validate whether outcomes are identical (at syntactic and semantic level) 
