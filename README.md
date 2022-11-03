# Deep-GRAIL Algorithm: Deep Deterministic Policy Gradient with Imitation Learning

This is the PyTorch implementation for the deep deterministic policy gradient with imitation learning (Deep-GRAIL) algorithm, with a specific application to solve the sum-rate maximization problem in rate-splitting multiuser systems. The code includes the implmentations of the learning algorithm, deep neural network models, system model for the rate-spliting multiuser systems, as well as a conventional optimization algorithm. If you use our code or data please cite [the paper](https://arxiv.org/abs/2210.12191) entitled "Rate-Splitting for Intelligent Reflecting Surface-Aided Multiuser VR Streaming". The application in the multiuser VR streaming systems will be updated upon final paper acceptance. Please check this page for updates.

### Prerequisites

The following libraries are required for this code base. We recommend to use the same versions as listed.
* Python v3.7.9
* PyTorch v1.9.0
* Numpy v1.19.1
* Matlab Engine for Python (R2020a) (Only required for generating the demonstration replay. [How to install Matlab Engine for Python](https://www.mathworks.com/help/matlab/matlab_external/install-the-matlab-engine-for-python.html))

### Usage
1. Generate the demonstration replay by running:
```
python demonstration_gen.py
```
Running the script will generate the demonstration replay and store it as NumPy array file (.npy) with names `replay_*.npy`. 

You can skip this step by using the pre-generated demonstration replay (together with the experience replay), which can be downloaded [here](https://drive.google.com/file/d/1PCTX1Li6Gow6G3ij0vK2dCuPVHBV2FzZ/view?usp=share_link) (File size ~1.5 GB).

2. Start the training algorithm by running:
```
python main.py
```

### Structures
* `main.py`: Main training loop and the implementation of Markov decision process (MDP).
* `DeepGRAIL.py`: The learning algorithm.
* `networks.py`: The implementation of the deep neural networks.
* `utils.py`: The implementation of the replay, including adding, loading, saving, and sampling of transition tuples.
* `demonstration_gen.py`: Method for generating the demonstration replay. The MDP implemented here needs to be the same as `main.py`.
* `opt_algo.m`: Matlab script for the conventional optimization algorithm (e.g., alternating optimization (AO) algorithm.

### Bibtex

```
@article{rui2022rate,
    title={Rate-Splitting for Intelligent Reflecting Surface-Aided Multiuser {VR} Streaming},
   	author={Huang, Rui and  W.S. Wong, Vincent and Schober, Robert},
    year={2022},
    month = {Oct.},
    journal={arXiv preprint arXiv:2210.12191},
}
```
