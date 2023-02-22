<img src="../../images/MORALAB_Banner.png">

# Installing Anaconda in Linux

> [conda](https://docs.conda.io/en/latest/) is defined as a multi-platform package, dependency, and environment management. [Anaconda](https://www.anaconda.com/) is a software distribution that includes **conda**, a few languages such as **Python** and **Java**, a repository of some other languages and their packages (such as **R**), and a few IDEs, such as **PyCharm**, **RStudio**, and others.

> The following are the instructions to install **Anaconda3** (version 2022.10) on Linux. The tutorial uses a **Linux Mint 21** installed in a **VirtualBox 7.0.2** virtual machine, as described here: [Creating a Linux Virtual Machine](../../../../virtualbox/blob/main/virtualbox/tutorial_2022/). A similar procedure can be followed using other OS.

## - Downloads
<br>

> 1. Go to your Linux machine. In our case, open the **VirtualBox** and start the VM.
<br>
<img src="images/Anaconda20.PNG" width="600">
<br>

> 2. Open a terminal and download **Anaconda3** latest version (currently, 2022.10) using:
```
curl -O https://repo.anaconda.com/archive/Anaconda3-2022.10-Linux-x86_64.sh
```
<br>
<img src="images/Anaconda22.PNG" width="600">
<br>
<img src="images/Anaconda23.PNG" width="600">
<br>

## - Installing Anaconda
<br>

> 3. Run the downloaded file by using:
```
bash Anaconda3-2022.10-Linux-x86_64.sh
```
<br>
<img src="images/Anaconda24.PNG" width="600">
<br>

> 4. Follow the installation procedure (accept license, etc).
<br>
<img src="images/Anaconda25.PNG" width="600">
<br>
<img src="images/Anaconda26.PNG" width="600">
<br>
<img src="images/Anaconda27.PNG" width="600">
<br>
<img src="images/Anaconda28.PNG" width="600">
<br>

## - Activate python's base environment

> 5. Go to the *bin* folder and activate **Anaconda**'s base environment.

```
cd /home/username/anaconda3/bin
. ./activate
```

<br>
<img src="images/Anaconda29.PNG" width="600">
<br>

## - Check Anaconda's functionality

> 6. Test **python** version (3.9.13).

<br>
<img src="images/Anaconda30.PNG" width="600">
<br>

> 7. Test **Jupyter notebooks**.

<br>
<img src="images/Anaconda31.PNG" width="600">
<br>
<img src="images/Anaconda32.PNG" width="600">
<br>
<img src="images/Anaconda33.PNG" width="600">
<br>

> 8. Test **Jupyter Lab**.
<br>
<img src="images/Anaconda34.PNG" width="600">
<br>
<img src="images/Anaconda35.PNG" width="600">
<br>
<img src="images/Anaconda36.PNG" width="600">
<br>

> 9. Test the **Anaconda Navigator**.

<br>
<img src="images/Anaconda37.PNG" width="600">
<br>

> 10. If you get the option of updating the navigator version, follow the instructions.

<br>
<img src="images/Anaconda38.PNG" width="600">
<br>
<img src="images/Anaconda39.PNG" width="600">
<br>
<img src="images/Anaconda40.PNG" width="600">
<br>

> 11. Anaconda Navigator includes a variety of programming tools, including **PyCharm**, **RStudio**, and many others.

<br>
<img src="images/Anaconda41.PNG" width="600">
<br>
<img src="images/Anaconda42.PNG" width="600">
<br>
<img src="images/Anaconda43.PNG" width="600">
<br>

## - Deactivate

> 12. To leave the environment, use: `conda deactivate`
<br>
<img src="images/Anaconda44.PNG" width="600">
<br>

## - Using `conda` to install packages, create environments, and add more installation channels

> 13. Conda channels are the remote locations (URLs) where programs are stored. The `conda config` command allows us to add new channels or to sort the channels priority. Here we will add two community-driven channels called [conda-forge](https://conda-forge.org/) and [bioconda](https://bioconda.github.io/).

```
conda config --add channels defaults
conda config --add channels bioconda
conda config --add channels conda-forge
```

<br>
<img src="images/Anaconda45.PNG" width="600">
<br>
<img src="images/Anaconda46.PNG" width="600">
<br>

> 14. The `conda config` command allows us to see our current channels.

```
conda config --show channels
```

<br>
<img src="images/Anaconda47.PNG" width="600">
<br>

> 15. In order to search for a specific package, we use `conda search`. For example, let's say that we want the most recent version of python.

```
conda search python
```

<br>
<img src="images/Anaconda48.PNG" width="600">
<br>
<img src="images/Anaconda49.PNG" width="600">
<br>

> We can see the channels for different python versions. We can see that the most recent version (3.11.0) can only be found at the `conda-forge` channel (at the time of creating this tutorial).

> 16. Conda environments are similar to Python's Virtual Environments, that is, they are directories isolated from all other environments so the user can install and keep different versions of a given software in different environments of the same machine, and, more commonly, isolate software that share the same dependencies but use different versions of those dependencies, leading to conflicts. Here we will create a new conda environment to install the most recent version of python.

```
conda deactivate
conda create -n newPython python=3.11
conda env list
```

<br>
<img src="images/Anaconda50.PNG" width="600">
<br>
<img src="images/Anaconda51.PNG" width="600">
<br>
<img src="images/Anaconda52.PNG" width="600">
<br>
<img src="images/Anaconda53.PNG" width="600">
<br>

> 17. Now we must activate the environment to access its contents.

```
conda activate newPython
conda list
```

<br>
<img src="images/Anaconda54.PNG" width="600">
<br>
<img src="images/Anaconda55.PNG" width="600">
<br>

> We can see python version 3.11.0 (while in the base environment was version 3.9.13).

> 18. We can install more packages to the environment. Here, we will install the **numpy** and **pandas** python libraries.

```
conda install numpy pandas
```

<br>
<img src="images/Anaconda56.PNG" width="600">
<br>
<img src="images/Anaconda57.PNG" width="600">
<br>
<img src="images/Anaconda58.PNG" width="600">
<br>

> Note that, while "apt" installs packages system-wide, "conda" installs packages on the currently active conda environment.

> 19. To exit the environment, we use `conda deactivate`.

```
conda deactivate
```

<br>
<img src="images/Anaconda59.PNG" width="600">
<br>

> 20. Finally, conda environments can be completely removed.

```
conda env remove -n newPython
conda env list
```

<br>
<img src="images/Anaconda60.PNG" width="600">
<br>
<img src="images/Anaconda61.PNG" width="600">
<br>

> 21. Optional/Alternative: Management of channels and environments can also be done from **Anaconda Navigator** by using the **Channels** button and the **Environments** menu.

<br>
<img src="images/Navigator01.PNG" width="600">
<br>
<img src="images/Navigator02.PNG" width="600">
<br>

## - More on *bioconda*

> 22. You can find more bioinformatics-related software at the [bioconda website](https://bioconda.github.io/).

<br>

*Last updated: Antonio Mora, November 16th, 2022*
