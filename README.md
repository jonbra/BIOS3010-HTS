# BIOS3010-HTS

Installing software on a Linux server like the ones we are using in this class can sometimes be difficult. Many program have "dependencies", other programs of libraries, that needs to be installed in a specific way in order for the program to run properly. On the servers that we are using this course there are many programs that have been pre-installed. The command `module avail` will give you a list of all pre-installed software. To activate a specific program, run `module load software name`. 

It is common these days to use so-called "package managers", software that can help us install programs and all necessary dependencies for us. Common package managers for the Unix environments are [Homebrew](https://brew.sh/) and [Conda](https://anaconda.org/). Software can also be run using so-called containers. . Also Docker and Singularity. 
```
module load Anaconda3/2020.11
``` 
