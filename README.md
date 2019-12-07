## Numba & Dask Workshop - PyConf Hyderabad 2019

This repo contains the code for the Numba & Dask Workshop I presented during PyConf Hyderabad 2019 at IIIT-Hyderabad on Dec 7th 2019.

For running locally, please download Anaconda Scientific Distribution for your respective platform.

Recommended OS is Ubuntu 18.04 LTS.

### Installation

Please clone the repo

```sh
git clone git@github.com:vijaysharmay/pyconf-workshop.git
cd pyconf-workshop
```

For creating the conda environment, please run

```sh
conda create --name pyconf-workshop --clone base
```

once the environment is setup, you can activate it by running 

```sh
conda activate pyconf-workshop
```

Install the dask extension by using the below commands after activating your conda env

```sh
pip install dask_labextension
jupyter labextension install dask-labextension
jupyter labextension enable dask-labextension
```

### Data Setup

Run the below commands for data setup after following the instructions for using kaggle API [here](https://github.com/Kaggle/kaggle-api#api-credentials)

```sh
sudo apt install unzip
mkdir data
make data
```

OR

You can simply download the Kaggle dataset [here](https://www.kaggle.com/datasnaek/youtube-new/data) to a directory called data/youtube (which should contain only CSV files)

### Contents

There are 4 Jupyter notebooks in this repo:

- [01-introduction.ipynb](./01-introduction.ipynb), which introduces python's performance problem and how numpy adds value (if any)
- [02-numba.ipynb](./02-numba.ipynb), explains basics of numba and gives practical examples of @jit and @vectorize, two important decorators to work with numba immediately
- [03-dask.ipynb](./03-dask.ipynb), explains the necessity for computing larger than memory datasets and how dask adds value 
- [04-cluster.ipynb](./04-cluster.ipynb), explains how to use dask in a simple SSH cluster and explains how to integrate numba and dask

### F.A.Q

Q: **Will numba and dask help me in scaling up my existing data science pipeline?**  
A: It depends. For example, have you tried understanding what exactly is the bottleneck with your current stack? Have you quantified the performance bottleneck? Do you really need to optimize? Are there any other alternatives?

Q: **Can I use it in production? Is it stable?**  
A: Numba & Dask are still improving and can only get better over time. I wouldn't suggest using it in production yet, unless you know what exactly you are doing.

Q: **Can I use numba with GPUs?**  
A: Yes but there are gotchas. Look [here](https://numba.pydata.org/numba-doc/dev/cuda/cudapysupported.html)

Q: **Whom do I reach out to if I have more questions?**  
A: [Travis Oliphant](https://twitter.com/teoliphant), [Mathew Rocklin](https://twitter.com/mrocklin) or maybe ..umm.. [me](https://twitter.com/VijayYellepeddi)?