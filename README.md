# T<sub>c</sub> core

This repository contains the core age prediction codes needed for use in [Tcplotter](https://github.com/HUGG/tcplotter) and [Tc1D](https://github.com/HUGG/TC1D).
You can find instructions for how to install these programs and/or compile them for your operating system below.

**Note**: If you simply want to explore how [Tcplotter](https://github.com/HUGG/tcplotter) and/or [Tc1D](https://github.com/HUGG/TC1D) work, you can visit the linked pages and click on the **launch binder** button on the README page, which will open an interactive notebook where you can play with the code without a need to install anything!

## Installation

In order for both Tcplotter and Tc1D to work, they must be able to find the executables `RDAAM_He` (`RDAAM_He.exe` in Windows) and `ketch_aft` (`ketch_aft.exe` in Windows) in the PATH for executables on your system. Setting things up to work for different operating systems thus requires specific instructions for each operating system, which you can find below. Instructions for each operating system comprise two steps: (1) obtaining or building the executables, and (2) installing them.

### Windows

#### Obtaining the executables

The easiest way to get up and running in Windows is to download the two executable files `RDAAM_He.exe` and `ketch_aft.exe` from the [latest code release](https://github.com/HUGG/Tc_core/releases/).

#### Installing the executables

Once you have downloaded the executables, you can put them in a suitable location for use. This could be a folder within your user space or somewhere else on your system. The important thing is that your operating system needs to be able to find the files to use Tcplotter or Tc1D. So, you can either install the files in a location where your computer already looks for executables or add the location where the files have been downloaded to the PATH where executables are found. There are many examples online that explain how to check your PATH and/or add an executable to your PATH in Windows. For example, [here](https://medium.com/@kevinmarkvi/how-to-add-executables-to-your-path-in-windows-5ffa4ce61a53), [here](https://windowsloop.com/how-to-add-to-windows-path/), or [here](https://helpdeskgeek.com/add-windows-path-environment-variable/).
