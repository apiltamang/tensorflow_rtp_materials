


Introduction:
-------------

Welcome to the weekly discussions on [Tensorflow](https://www.tensorflow.org/) for RTP's Deep Learning Meetup group. This discussion will tentatively happen every Thursday during lunch at the Frontier.

Environment Setup
-----------------
We will be using [anaconda](https://docs.continuum.io/anaconda/install) to setup a contained python environment. Make sure you download anaconda to your computer. Once this is done, you may do the following to install the required packages:

 - conda create -n tensorflow_dlrtp python=3 (Creates a new environment)
 - source activate tensorflow_dlrtp (Activates the environment)
 - conda install -c conda-forge tensorflow=1.0.0 (Installs tensorflow)
 - conda install jupyter=1.0.0 (Installs Jupyter)

Likewise, if you ever need to search for and install a package in the future
 - conda search [package]
 - conda install [package=version]

 OR, if the above doesn't yield anything, you can search in the conda-forge repository using the following:
 - conda search -c conda-forge [package]
 - conda install -c conda-forge [package=version]


Be sure to activate the 'tensorflow_dlrtp' environment before attempting to run the code. To get started:

 - source activate tensorflow_dlrtp
 - jupyter notebook
 
 And that's it! Once this is done, be sure to checkout the notebooks posted weekly in the corresponding folders. There might be assignments you could challenge yourself to too... happy learning!
