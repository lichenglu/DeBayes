The code that was originally used to run the experiments for "DeBayes: a Bayesian Method for Debiasing Network Embeddings", a paper that was accepted at ICML 2020. Further development may be done in the future and bugs will be fixed. If you have any questions or concerns, feel free to report it here or send an email to 'maarten.buyl@ugent.be'. 

## Use
An example of how the DeBayes code can be used for the Movielens 100k dataset is given in main_example.py. Important functions and class constructors are also documented. Please take a look at the DeBayes constructor and fit function documentation!

The DeBayes method does not require any special hyperparameter tuning to debias embeddings compared to "Conditional Network Embedding 
(CNE)". It suffices to set the 'biased_degree' prior as the training prior and the 'degree' prior for evaluation. However, the AUC of the underlying CNE method is dependent on the 'dimension' and 's2' variable. In order to improve this prediction AUC, we ask you to tune s2 for values larger than s1, e.g. for the following values: [2, 8, 16, 32, 64]. The dimensionality can probably remain at 8 for most applications. 

Several mechanisms for speedups were implemented, including the saving and loading of priors and embeddings from past iterations/seeds. This may make reruns of the same experiment (with the same random seed) easier. To toggle this, see the constructor of the classes.


## Setup
The used packages can be installed with pip and are listed in requirements.txt. Note that scikit-learn is strictly used in main_example.py and not required for the method itself. 

The Movielens dataset was not included, but it may be downloaded here: https://grouplens.org/datasets/movielens/100k/.



If you found this method useful in your work, please cite our paper:

    @inproceedings{buyl2020debayes,
        title={DeBayes: a Bayesian Method for Debiasing Network Embeddings},
        author={Buyl, Maarten and De Bie, Tijl},
        booktitle={International Conference on Machine Learning},
        series={Proceedings of Machine Learning Research},
        volume={119},
        pages={1220--1229},
        year={2020}
    }
