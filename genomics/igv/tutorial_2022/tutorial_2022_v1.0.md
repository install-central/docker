<img src="../../../images/MORALAB_Banner.png">

# Installing IGV in Linux
<br>

> The following are the instructions to install **Integrated Genomic Viewer (IGV)** (version 2.4.9, from 2018) on Linux. The tutorial uses a **Linux Mint 21** installed in a **VirtualBox 7.0.2** virtual machine, as described here: [Creating a Linux Mint-21 VM](../../../../../virtualbox/blob/main/virtualbox/tutorial_2022/). Also, **Anaconda3**, as described here: [Installing Anaconda3](../../../../../anaconda/blob/main/tutorial_2022/).

## - Install IGV

> 1. Go to your Linux machine. In our case, open the **VirtualBox** and start the VM.
<br>
<img src="images/Anaconda01.PNG" width="600">
<br><br>
<img src="images/Anaconda02.PNG" width="600">
<br>

> 2. Open a terminal and activate the conda `base` environment.

```
cd ~/anaconda3/bin
. ./activate
```

<br>
<img src="images/IGV03.PNG" width="600">
<br>

> 3. Create a new conda environment to install **IGV**. Here we will call it **igvEnv**. You will observe that the comand does install **igv** and **openjdk**.
```
conda create -n igvEnv igv
```

<br>
<img src="images/IGV04.PNG" width="600">
<br><br>
<img src="images/IGV05.PNG" width="600">
<br><br>
<img src="images/IGV06.PNG" width="600">
<br>

> 4. Check the list of current environments.
```
conda env list
```

<br>
<img src="images/IGV07.PNG" width="600">
<br>

> 5. Activate the new conda environment (**igvEnv**). You can list all of the packages inside this environment using `conda list`.
```
conda activate igvEnv
conda list
```

<br>
<img src="images/IGV08.PNG" width="600">
<br><br>
<img src="images/IGV09.PNG" width="600">
<br>

## - Test IGV

> 6. Run IGV by typing `igv`.
```
igv
```

<br>
<img src="images/IGV10.PNG" width="600">
<br><br>
<img src="images/IGV11.PNG" width="600">
<br><br>
<img src="images/IGV12.PNG" width="600">
<br>

## - Deactivate
> 7. To leave the environment, use: `conda deactivate`
```
conda deactivate
```

<br>
<img src="images/IGV13.PNG" width="600">
<br>

<br>

*Last updated: Antonio Mora, November 23rd, 2022*
