# T<sub>c</sub> core

This repository contains the core age prediction codes needed for use in [T<sub>c</sub>plotter](https://github.com/HUGG/tcplotter) and [T<sub>c</sub>1D](https://github.com/HUGG/TC1D).
You can find instructions for how to install these programs and/or compile them for your operating system below.

**Note**: If you simply want to explore how T<sub>c</sub>plotter or T<sub>c</sub>1D work, you can visit the [T<sub>c</sub>plotter](https://github.com/HUGG/tcplotter) or [T<sub>c</sub>1D](https://github.com/HUGG/TC1D) GitHub repositories and click on the [![Binder](https://mybinder.org/badge_logo.svg)]() button on the README page, which will open an interactive notebook where you can play with the code without a need to install anything!

## Installation

In order for both T<sub>c</sub>plotter and T<sub>c</sub>1D to work, they must be able to find the executables `RDAAM_He` (`RDAAM_He.exe` in Windows) and `ketch_aft` (`ketch_aft.exe` in Windows) in the PATH for executables on your system. Setting things up to work for different operating systems thus requires specific instructions for each operating system ([Windows](#windows), [Linux](#linux), [macOS](#macos)).

Instructions for each operating system comprise two steps: (1) obtaining or building the executables and (2) installing them.

### Windows :window:

#### Obtaining the executables

The easiest way to get up and running in Windows is to download the two executable files `RDAAM_He.exe` and `ketch_aft.exe` from the [latest code release](https://github.com/HUGG/Tc_core/releases/). If this doesn't work, you can consult the instructions below for [how to compile the executables](#compiling-the-executables).

#### Installing the executables

Once you have downloaded the executables, you need to put them in a suitable location for use. This could be a folder within your user space or somewhere else on your system. The important thing is that your operating system needs to be able to find the files to use Tcplotter or Tc1D. So, you can either install the files in a location where your computer already looks for executables or add the location where the files have been downloaded to the PATH where executables are found. There are many examples online that explain how to check your PATH and/or add an executable to your PATH in Windows. For example, [here](https://medium.com/@kevinmarkvi/how-to-add-executables-to-your-path-in-windows-5ffa4ce61a53), [here](https://windowsloop.com/how-to-add-to-windows-path/), or [here](https://helpdeskgeek.com/add-windows-path-environment-variable/).

### Linux :penguin:

#### Obtaining the executables

The easiest way to get up and running in Windows is to download the two executable files `RDAAM_He` and `ketch_aft` from the [latest code release](https://github.com/HUGG/Tc_core/releases/). If this doesn't work, you can consult the instructions below for [how to compile the executables](#compiling-the-executables).

#### Installing the executables

Once you have downloaded the executables, you need to put them in a suitable location for use. This could be a folder within your user space or somewhere else on your system. The important thing is that your operating system needs to be able to find the files to use Tcplotter or Tc1D. So, you can either install the files in a location where your computer already looks for executables or add the location where the files have been downloaded to the PATH where executables are found.

If you would prefer to install the executables in a location where they can be found in the PATH already, it is suggested to copy them to `/usr/local/bin`. Note that you may need administrator rights to do this. You can check other possible locations for installation by typing

```bash
echo $PATH
```

in the terminal, which will list all directories in which executables can be found.

If you would prefer to install them elsewhere and add them to your PATH, you can update the path in a terminal by typing

```bash
export PATH=$PATH:/path/to/executables
```

where you would replace `/path/to/executables` with the actual filepath to them. If you want this to happen automatically, you should [add that export statement to your shell resource file](https://www.geeksforgeeks.org/linux-unix/how-to-set-path-permanantly-in-linux/).

### macOS :apple:

#### Obtaining the executables

Unfortunately, the Tc_core executables must be compiled locally for macOS. You should consult the instructions below for [how to compile the executables](#compiling-the-executables).

#### Installing the executables

Once you have downloaded the executables, you need to put them in a suitable location for use. This could be a folder within your user space or somewhere else on your system. The important thing is that your operating system needs to be able to find the files to use Tcplotter or Tc1D. So, you can either install the files in a location where your computer already looks for executables or add the location where the files have been downloaded to the PATH where executables are found.

If you would prefer to install the executables in a location where they can be found in the PATH already, it is suggested to copy them to `/usr/local/bin`. Note that you may need administrator rights to do this. You can check other possible locations for installation by typing

```bash
echo $PATH
```

in the terminal, which will list all directories in which executables can be found.

If you would prefer to install them elsewhere and add them to your PATH, you can update the path in a terminal by typing

```bash
export PATH=$PATH:/path/to/executables
```

where you would replace `/path/to/executables` with the actual filepath to them. If you want this to happen automatically, you can do so similarly to Linux and [add that export statement to your shell resource file](https://www.geeksforgeeks.org/linux-unix/how-to-set-path-permanantly-in-linux/). Or if you prefer macOS-specific instructions, you can [find those here](https://techpp.com/2021/09/08/set-path-variable-in-macos-guide/).

### Compiling the executables :desktop_computer:

Compiling the executables for the Tc_core programs requires a few things are available on your computer. The requirements for each system vary slightly:

- Windows: [CMake](https://cmake.org/download/), [MinGW](https://sourceforge.net/projects/mingw/)
- Linux: [CMake](https://cmake.org/) (suggested to be installed with your package manager (e.g., `apt install cmake`)), GCC/G++ compilers (most likely already installed)
- macOS: [CMake](https://cmake.org/) (suggested to be installed using [Homebrew](https://brew.sh/)), GCC/G++ compilers (suggested to be installed using [Homebrew](https://brew.sh/) (e.g., `brew install gcc`))

With the necessary software installed, you can compile the Tc_core executables by

1. Downloading the [latest release of the Tc_core source code](https://github.com/HUGG/Tc_core/releases/) and unpacking it
2. Opening a Windows command prompt or terminal in Linux or macOS and changing to the directory where you unpacked the source code.
3. Create a `build` directory (e.g., `mkdir build`)
4. Run CMake configure
    ```bash
    cmake -B build -DCMAKE_CXX_COMPILER=g++ -DCMAKE_C_COMPILER=gcc -DCMAKE_BUILD_TYPE=Release -S src
    ```
    - **Note**: If you have installed the GCC compilers using Homebrew on macOS, the executable names you list above should be for the corresponding verison of the installed compilers. For example, `-DCMAKE_CXX_COMPILER=g++-15` and `-DCMAKE_C_COMPILER=gcc-15`.
5. Run CMake build
    ```bash
    cmake --build build --config Release
    ```
6. Run CMake install
    ```bash
    cmake --install build --prefix . --config Release
    ```

The compiled executables will be installed in the `bin` directory and can be installed to the desired location using the [installation instructions above](#installation).

## Testing the installation :scientist:

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
