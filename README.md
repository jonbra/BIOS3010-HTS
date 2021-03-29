# BIOS3010-HTS

## A few words about installing and using software on a Linux system
Installing software on a Linux server like the ones we are using in this class can sometimes be difficult. Many program have "dependencies", other programs of libraries, that needs to be installed in a specific way in order for the program to run properly. On the servers that we are using this course there are many programs that have been pre-installed. The command `module avail` will give you a list of all pre-installed software. To activate a specific program, run `module load software name`. 

It is common these days to use so-called "package managers", software that can help us install programs and all necessary dependencies for us. Common package managers for the Unix environments are [Homebrew](https://brew.sh/) and [Conda](https://anaconda.org/). Software can also be run using so-called containers. Containers provide a package with all necessary software and dependencies, which makes your programs run and work the same on all computer platforms. Common containers are [Docker](https://www.docker.com/) and [Singularity](https://sylabs.io/guides/3.0/user-guide/index.html#). 

## Setting up our working environment
In these exercises we will use Conda to install the necessary software for us. Conda is already installed on the server, so just type `module load Anaconda3/2020.11` to activate it. If you now type `cond` and then press the TAB-button, the command `conda` should be "auto completed" (auto completion is the cornerstone of working in a Linux system. You simply must be able to know and use the TAB-button if you want to do bioinformatics). If you press TAB twice you should see other available commands starting with `conda`.  

It's good practice to have different "conda environments" for different projects. These environments will contain only the software that you need for that specific project. For these exercises we will create a Conda environment called "HTS". We specify what kinds of software we want in an "environment file". 

```
cp /storage/BIOS3010/HTS/environment.yml .
cat environment.yml
```

You should see something like this:
```
name: HTS

channels:
    - defaults
    - bioconda

dependencies:
    - fastqc=0.11.9
```

These are instructions that tells Conda to create an environment named "HTS" and that it should install the software "fastqc" version 0.11.9 and that it can find this software in the channels "defaults" and "bioconda".   

To create the environment run:
```
conda env create -f environment.yml
```
This installs the necessary software and you only need to run this command once. 

To activate the environment run `conda activate HTS`. 
