# Component CFG based Android Vetting System by Applying CapsGNN

Android is an event-based/component-based system. By triggering different events, the control flow can be various, plus building component control flow graph could cuasue computational challenge. The graph we are using is based on highly precise inter-procedural control flow graph (**API-call nodes only**) of one app's components. 

The development of this vetting system's capsule graph neural netowrk is based on:  
> Capsule Graph Neural Network.
> Zhang Xinyi, Lihui Chen.
> ICLR, 2019.
> [[CapsGNN]](https://github.com/XinyiZ001/CapsGNN)

### Package Version
```
networkx    2.4
numpy       1.16.2
scipy       1.4.1
tensorflow  1.12.2
```
It can run on tensorflow 1.15 and the latest version of the other packages when this thesis was submitted.

### Usage

#### Graph embedding

1. Sample graph data is in `graph_dataset/APKICFG`. Each graph is a combination one apk's all component control flow graph. To geneate more graphs, check `icfg_generator`.


2. To processing graph embedding:
```
  $ python dataset_utils/preprocessing.py
```

#### Training model
All the hyperparameters can be set in `config.py`. Training a model by using default configs:
```
  $ python main.py
```

Training a model with specific epochs:
```
  $ python main.py --epochs 30
```

(Would require amandroid based jar file to extract API sequence graphs.)
