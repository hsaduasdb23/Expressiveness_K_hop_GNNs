# Expressiveness_K_hop_GNNs
Code and other resources for the submission of Improving the Expressiveness of K-hop Message Passing GNNs by Injecting Contextualized Substructure Information
### Graph Property Dataset
1. To run SEK-GIN, please follow these steps:
   i) Preprocessing dataset. In the root directory, run `python data_pna.py`, it will generate the GraphProperty dataset suitable for SEK-GIN, and preprocess it for SEK-GNN.
   ii) To try our code, run `python run_graph_property.py --use_both --mhc_layer_num ${SEK-GIN layer number} --mhc_num_hops ${number of hops} --lr ${lr_value} --weigfht_decay ${l2_wd value} --pooling_method ${Pooling Method} --combine ${combine method} --task ${task_id}`, for complete arguments, please see the detailed code and comment in run_graph_property.py. For example, to run a 5-layer 6-hop SEK-GIN with geometric combine function and attention-based pooling function for task 0, run the following code:
     
     ```python run_graph_property.py --use_both --mhc_layer_num 5 --mhc_num_hops 6 --lr 8e-3 --pooling_method attention --combine geometric --task 0```

2. To run SEK-PPGN, go to `GraphProperty/` directory, and then use the provided code `run_gp_ppgn.py`, e.g., to run 1-layer 3-hop SEK-PPGN for task 1, run the following code:
  
    ```python run_gp_ppgn.py --use_ppgn 1 --hop 3 --task 0``` 
  
  currently the code only supports 1-layer SEK-PPGN, which is used in our experiment. The dataset will be automatically preprocessed.
  
  *** Subgraph Count Dataset
  1. To run SEK-GIN, please follow these steps:
   i) Preprocessing dataset. In the root directory, run `python SubgraphCount.py`, it will generate the GraphCount dataset suitable for SEK-GIN, and preprocess it for SEK-GNN.
   ii) To try our code, use the code `run_subgraph_count.py`, for complete arguments, please see the detailed code and comment in run_graph_property.py. For example, to run a 5-layer 6-hop SEK-GIN with geometric combine function and attention-based pooling function for task 1, run the following code(for GraphCount dataset, the pooling method is default to be attention, no choice is provided in the command line):
     
     ```python run_subgraph_count.py --use_both --mhc_layer_num 5 --mhc_num_hops 6 --lr 8e-3 --combine geometric --task 0```
  
  2. To run SEK-PPGN, go to `GraphCount/` directory, and then use the provided code `run_subgraph_count.py`, e.g., to run 1-layer 3-hop SEK-PPGN for task 1, run the following code:
    
    ```python run_graphcount_ppgn.py --use_ppgn 1 --hop 3 --task 1``` 
  
  
  
  
