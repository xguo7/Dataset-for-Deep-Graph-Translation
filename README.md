# Dataset-for-Deep-Graph-Translation
This page summarize and provide the data and applications for the deep graph translation problem. The deep graph translation problem aims to learn the mapping rules among graphs atomatically by oberving large amount of graph pairs based on the deep learning methods. There are two versions of deep graph translation problems: one is to learn a one-to-one mapping rule between the input graph and target graph, as the defination by Guo et al [1]; another is to learn a one-to-many mapping rule between the input graph and a set of target graphs, which is defined by Guo et al [2]; To avoid loss of generality, the graph in this problems can be all kinds of graphs, such as directed/undirected graphs, sign graphs, and multi-attributed graph. 

![image_text](images/graph_translation.png "Deep Graph Translation")

For wider investigation and explaration by researchers around the world, we provide five synthetic or real-world data as well as their application tasks for this problem: Scale-free graphs dataset, IoT (Internet of Things) dataset, Brainnetwork connectivety dataset, User authenticfication dataset, and the chemistry reaction dataset. 
    
    
## Scale-free Graphs 
This dataset fits the "one-to-many" mapping graph translation version. There are no node features in the dataset, and the goal is to learn the mapping from the input graphs' topology to the target graph's topology. Each input graph is generated as a directed scalefree network, which is a network whose degree distribution follows power-law property (Bollobas´ et al., 2003). To generate a target graph, a node will by selected as target node with probability proportional to its in-degree, which will be linked to a new source node with probability of 0.41. Similarly, a node will by selected as source node with probability proportional to its out-degree, which will be linked to a new target node with probability of 0.54. Then, a corresponding target graph is generated by adding m (m equals the number of nodes of the input graph) edges between two nodes. Thus, both input and target graphs are directed scale-free graphs. 


#### Content
There are five subsets of data with different graph size (i.e. number of nodes): 10, 20, 50, 100, and 150. In each subset, each input and output graph are stored in the "scale-(graph_size)-input-index.csv" and "scale-(graph_size)-target-index.csv" file. For each file, the value in i(th) comlume, j(th) row indicates whether the number of connections (edge weights) between Node i and Node j (1 indicating there is an edge and 0 otherwise). These dataset can be downloaded through the following links:

[Scale_free_150](https://exchangelabsgmu-my.sharepoint.com/:u:/g/personal/xguo7_masonlive_gmu_edu/EQ7FRL8QWYdPg25QaCe0VpEBHwioyA4nEjP2GDgiVQQwVw)

[scale_free_100](https://exchangelabsgmu-my.sharepoint.com/:u:/g/personal/xguo7_masonlive_gmu_edu/EXLsRjyz7z1HhRur-F9jkpwBFfRhO14NfQxXoLSHwCzYfg)

[scale_free_50](https://exchangelabsgmu-my.sharepoint.com/:u:/g/personal/xguo7_masonlive_gmu_edu/Ec7OxxtCrW5Nr7itfQAlcagBQaRNG-ttRt-DZkj8jBxphQ)

[scale_free_20](https://exchangelabsgmu-my.sharepoint.com/:u:/g/personal/xguo7_masonlive_gmu_edu/EQ3WsWoTBwNLsQXQOIwChOgBsbDIUfZpp0tmvJYGp0JrtA)

[scale_free_10](https://exchangelabsgmu-my.sharepoint.com/:u:/g/personal/xguo7_masonlive_gmu_edu/EartEwo94NtJrsBUSDCaSyIBYgHxLSVj6qwziixaQHHHdw)

#### Acknowledgements
Please cite formally when you use these dataset as:

Guo, X., Wu, L., & Zhao, L. (2018). Deep graph translation. arXiv preprint arXiv:1805.09980.

## Erdos-Renyi Graphs
This dataset fit the problem of "one-to-one" mapping verision of graph translation. For each pair of graphs, the input graph is generated by the Erdos Renyi model with the edge probability of 0.2. The target graph topology is the 2-hop connection of the input graph, where each edge in the target graph refers to the 2-hop reachability in the input graph (e.g. if node i is 2-hop reachable to node j in the input graph, then they are connected in the target graph). There are edge and node attributes for graphs in this dataset: the edge attributes E_(i,j) denotes the existence of the edge and the node attributes are continuous values computed following the polynomial function: f(x) : y = ax^2 + bx + c(a =0; b =1; c= 5), where x is the node degree and f(x) is the node attribute.

#### Contents
There are three subsets of data with different graph size (i.e. number of nodes): 20, 40, and 60. In each subset, each input and output graph are stored in the "ER-(graph_size)-input-index.csv" and "ER-(graph_size)-target-index.csv" file. For each file, the value in i(th) comlume, j(th) row indicates whether the number of connections (edge weights) between Node i and Node j (1 indicating there is an edge and 0 otherwise). The value in i(th) row and i(th) column indicates the node attributes of the i(th) node. These dataset can be downloaded through the following links:

[ER_20](https://exchangelabsgmu-my.sharepoint.com/:u:/g/personal/xguo7_masonlive_gmu_edu/EacBEmToBKdPtOhjJocARikBV6WRr7kNs50QyFShsx1k1w)

[ER_40](https://exchangelabsgmu-my.sharepoint.com/:u:/g/personal/xguo7_masonlive_gmu_edu/EU7TdmWC_z1HvY3KLcPonZwBB167_MYTQZuW8wSso4Qc1g)

[ER_60](https://exchangelabsgmu-my.sharepoint.com/:u:/g/personal/xguo7_masonlive_gmu_edu/EQYmsg6wu3ZAuvHS1Klc_gwBdZP3jCl_PM2p6p7nLMZ66g)

#### Acknowledgements
Please cite formally when you use these dataset as:

Guo X, Zhao L, Nowzari C, Rafatirad S, Homayoun H, Dinakarrao SM. Deep Multi-attributed Graph Translation with Node-Edge Co-evolution. Inhe 19th International Conference on Data Mining (ICDM 2019), pp. to appear 2019.

## Barab´asi-Albert Graphs
This dataset fit the problem of "one-to-one" mapping verision of graph translation. For each pair of graphs, the input graph is generated by the Barab´asi-Albert model. The target graph topology is the 2-hop connection of the input graph, where each edge in the target graph refers to the 3-hop reachability in the input graph (e.g. if node i is 3-hop reachable to node j in the input graph, then they are connected in the target graph). There are edge and node attributes for graphs in this dataset: the edge attributes E_(i,j) denotes the existence of the edge and the node attributes are continuous values computed following the polynomial function: f(x) : y = ax^2 + bx + c(a =0; b =1; c= 5), where x is the node degree and f(x) is the node attribute.

#### Contents
There are three subsets of data with different graph size (i.e. number of nodes): 20, 40, and 60. In each subset, each input and output graph are stored in the "BA-(graph_size)-input-index.csv" and "BA-(graph_size)-target-index.csv" file. For each file, the value in i(th) comlume, j(th) row indicates whether the number of connections (edge weights) between Node i and Node j (1 indicating there is an edge and 0 otherwise). The value in i(th) row and i(th) column indicates the node attributes of the i(th) node. These dataset can be downloaded through the following links:

[BA_20](https://exchangelabsgmu-my.sharepoint.com/:u:/g/personal/xguo7_masonlive_gmu_edu/ESU5immRQ3xCvxkAy0LFvlgBTJrF0eHDosjRhnnayUXqHw)

[BA_40](https://exchangelabsgmu-my.sharepoint.com/:u:/g/personal/xguo7_masonlive_gmu_edu/EaihwXZdW2dHpl0X22dtD5wBcKFD9X6F1SoYhDKzAhRX1w)

[BA_60](https://exchangelabsgmu-my.sharepoint.com/:u:/g/personal/xguo7_masonlive_gmu_edu/EV96-W8Kw1hFnMxDudDWCk0BK6J24_my2yD7KrgJLR-yWw)

#### Acknowledgements
Please cite formally when you use these dataset as:

Guo X, Zhao L, Nowzari C, Rafatirad S, Homayoun H, Dinakarrao SM. Deep Multi-attributed Graph Translation with Node-Edge Co-evolution. Inhe 19th International Conference on Data Mining (ICDM 2019), pp. to appear 2019.


## IoT 
The process of malware confinement over IoT (Internet of Things) is typically a graph translation problem. It takes the initial status
of IoT as input, and predicts the target graph which is ideally the optimal status of the network with modified connections (i.e., edges) and devices (i.e., nodes) state that helps to limit malware propagation and maintain network throughput. Malware dataset are collected for malware confinement prediction. There are three sets of IoT nodes at different amount (20, 40 and 60) encompassing temperature sensors connected with Intel ATLASEDGE Board and Beagle Boards (BeagleBone Blue), communicating via Bluetooth protocol. Benign and malware activities are executed on these devices to generate the initial attacked networks as the input graphs. Benign activities include MiBench [34] and SPEC2006 [35], Linux system programs, and word processor. The nodes represent devices and node attribute is a binary value referring to whether the device is compromised or not. Edge represents the connection of two devices and the
edge attribute is a continuous value reflecting the distance of two devices. The real target graphs are generated by the classical malware confinement methods: stochastic controlling with malware detection. We collected 334 pairs of input and target graphs with different contextual parameters (infection rate, recovery rate, and decay rate) for each of the three datasets. 
#### Description
There are three subsets with different graph sizes. Each input/target graph is stored in the file with name " IoT-[graph_size]-[input/output]-[infection rate]-[recovery rate]-[decay rate]-[index].csv". The infection rate, recovery rate and decay rate can be used as the contextual controlling parameters in generating the target graph. The value of i(th) row and j(th) colomn refers to the phsical distance of Node i and j (0 refers to no links). The value of i(th) row and i(th) colomn refers to the node attribute (i.e. device status) of the Node i. 
[IoT_20](https://exchangelabsgmu-my.sharepoint.com/:u:/g/personal/xguo7_masonlive_gmu_edu/EcZsWKkLcxBKpaZ-X7_CHcoB5VAEzd9AGYgxATWIUPAsRw)
[IoT_40](https://exchangelabsgmu-my.sharepoint.com/:u:/g/personal/xguo7_masonlive_gmu_edu/Eekr5lVPZBlMk6_1KkBgZbIBWPRYzDrA6tt9WOhJ1yUbEA)
[IoT_60](https://exchangelabsgmu-my.sharepoint.com/:u:/g/personal/xguo7_masonlive_gmu_edu/EY6Emi5mPQdDodCY0dK_ISQB4oYGpRnaMfxY2EpSCE7VLw)

#### Acknowledgements
Please cite formally when you use these dataset as:

Guo X, Zhao L, Nowzari C, Rafatirad S, Homayoun H, Dinakarrao SM. Deep Multi-attributed Graph Translation with Node-Edge Co-evolution. Inhe 19th International Conference on Data Mining (ICDM 2019), pp. to appear 2019.

## Brainnetwork  
#### Description
#### Acknowledgements

## User Authetication
#### Description
#### Acknowledgements

## Chemistry Reaction
#### Description
#### Acknowledgements
