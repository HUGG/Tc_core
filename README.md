# T<sub>c</sub> core

This repository contains the core age prediction codes needed for use in [T<sub>c</sub>plotter](https://github.com/HUGG/tcplotter) and [T<sub>c</sub>1D](https://github.com/HUGG/TC1D).
You can find instructions for how to install these programs and/or compile them for your operating system below.

**Note**: If you simply want to explore how T<sub>c</sub>plotter or T<sub>c</sub>1D work, you can visit the [T<sub>c</sub>plotter](https://github.com/HUGG/tcplotter) or [T<sub>c</sub>1D](https://github.com/HUGG/TC1D) GitHub repositories and click on the [![Binder](https://mybinder.org/badge_logo.svg)]() button on the README page, which will open an interactive notebook where you can play with the code without a need to install anything!

## Installation

In order for both T<sub>c</sub>plotter and T<sub>c</sub>1D to work, they must be able to find the executables `RDAAM_He` (`RDAAM_He.exe` in Windows) and `ketch_aft` (`ketch_aft.exe` in Windows) in the PATH for executables on your system. Setting things up to work for different operating systems thus requires specific instructions for each operating system, which you can find below. Instructions for each operating system comprise two steps: (1) obtaining or building the executables, and (2) installing them.

### Windows :window:

#### Obtaining the executables

The easiest way to get up and running in Windows is to download the two executable files `RDAAM_He.exe` and `ketch_aft.exe` from the [latest code release](https://github.com/HUGG/Tc_core/releases/). If this doesn't work, you can consult the instructions below for how to compile the executables.

#### Installing the executables

Once you have downloaded the executables, you can put them in a suitable location for use. This could be a folder within your user space or somewhere else on your system. The important thing is that your operating system needs to be able to find the files to use Tcplotter or Tc1D. So, you can either install the files in a location where your computer already looks for executables or add the location where the files have been downloaded to the PATH where executables are found. There are many examples online that explain how to check your PATH and/or add an executable to your PATH in Windows. For example, [here](https://medium.com/@kevinmarkvi/how-to-add-executables-to-your-path-in-windows-5ffa4ce61a53), [here](https://windowsloop.com/how-to-add-to-windows-path/), or [here](https://helpdeskgeek.com/add-windows-path-environment-variable/).

### Linux :penguin:

#### Obtaining the executables

The easiest way to get up and running in Windows is to download the two executable files `RDAAM_He.exe` and `ketch_aft.exe` from the [latest code release](https://github.com/HUGG/Tc_core/releases/).

#### Installing the executables

### macOS :apple:

### Compiling the executables

...

## Testing the installation

If everything is working OK you should be able to [open a command prompt in Windows](https://www.wikihow.com/Open-the-Command-Prompt-in-Windows) or a terminal in [Linux](https://www.geeksforgeeks.org/linux-unix/how-to-open-terminal-in-linux/) or [macOS](https://support.apple.com/guide/terminal/open-or-quit-terminal-apd5265185d-f365-44cb-8b09-71a064a42125/mac) and type `RDAAM_He` or `ketch_aft` and press Enter. You should see the following:

```bash
> RDAAM_He
usage: RDAAM_He tTfile [ap_rad ap_U ap_Th zr_rad zr_U zr_Th]
```

```bash
> ketch_aft
usage: ketch_aft tT_file
```

This output indicates the executables have been installed in a location where they can be found in the PATH. To test they are functioning properly, you can use an [example time-temperature history file](tt.txt) to produce the following output:

```bash
> RDAAM_He tt.txt
Apatite Age = 5.35, Corrected age = 7.16
Zircon Age = 11.84, Corrected age = 14.98
```

```bash
> ketch_aft tt.txt
The final age is 13.707531 Ma (Mean track length: 13.707993 um)
```
