Before you start developing applications with Geant4, the first problem that you might encounter is how to install Geant4 in your system. There are multiple methods and ways to use Geant4, but here I will describe the steps to get Geant4 running in the 2 different methods that I have experience with.
#### Option 1. Build from source on Linux:
Before you begin, you should ensure that your system fulfills the [system and software prerequisites](https://geant4-userdoc.web.cern.ch/UsersGuides/InstallationGuide/html/gettingstarted.html#softwarerequirements). Then you should obtain your desired version of Geant4 from the [downloads page](https://geant4.web.cern.ch/download/) (you can search for older versions here. Then download the .tar.gz file of your selected version (in this case 10.7.4), and unpack it in a directory. In this case, we unpack it in the `/sofware` subdirectory, then the source code is in a subdirectory:

`/software/geant4-v10.7.4`

This is the *source directory* of Geant4. Then we need to configure a directory to store the build files and run the build. This *build directory* should **not** be the same directory nor inside the *source directory*, this is important as it ensures that no vital source files are overwritten during the installation, and it also allows to have different installations with various options.

`$ cd /software
`$ mkdir geant4-v10.7.4-build`
`$ ls`
`geant4-v10.7.4  geant4-v10.7.4-build`

Then you can configure the build, start by changing into the build directory:

`$ cd geant4-v10.7.4-build`

Then you should run CMake. You can use CMake, but there are many options available, so using CCMake, which gives you an interface to see and modify the different options before building can be useful. To run a default installation you can use:

`$ cmake -CMAKE_INSTALL_PREFIX=/software/geant4-v10.7.4-install /software/geant4-v10.7.4`

Where `DCMAKE_INSTALL_PREFIX` establishes the directory where Geant4 will be installed and `/software/geant4-v10.7.4` is the *source directory*. There are many options, and you will see all of them available in CCMake (and in the Installation Guide). Here are some of the most relevant:

- `CMAKE_INSTALL_PREFIX`: Specifies the *installation directory*
- `GEANT4_BUILD_MULTITHREADED`: `ON`/ `OFF` Sets up [[Multithreading]] (on by default).
- `GEANT4_INSTALL_DATA`: `ON`/ `OFF` Downloads and installs any dataset that is missing from `GEANT4_INSTALL_DATADIR` (off by default).
- `GEANT4_USE_OPENGL_X11`: `ON`/ `OFF` Sets up X11 OpenGL visualization driver (off by default).
- `GEANT4_USE_QT`: `ON`/ `OFF` Sets up Qt User Interface and Visualization drivers (off by default).
- `GEANT4_USE_RAYTRACER_X11`: `ON`/ `OFF` Sets up RayTracer visualization driver with X11 support (off by default).
- `GEANT4_USE_SYSTEM_EXPAT`: `ON`/ `OFF` Sets up Geant4 with an external install of Expat. Expat is installed on the vast majority of systems, but if it was missing, this option can be switched off and Geant4 will build and use its internal version of Expat (on by default).

After you are happy with your configuration, you can run the configuration. CMake will then generate the Unix Makefiles for building Geant4. To run the build, simply execute `make` in the build directory. Running the build takes a long time, so it is recommended (but not necessary) to use the command `-jN` where `N` is the number of parallel jobs to be used (e.g. if your machine has a dual core processor, you could set `N` to 2). 

`$ make -jN` 

You should not get errors during the installation, but if you do get them, you can add `VERBOSE=1` at the end of the command to give you more output, which can be useful for debugging.

After the build is complete, you can install Geant4 by running:

`$ make install`

This command should be run while in the *build directory*. After running it, all of the necessary libraries, files and resources will be available in your *installation directory*, if you have followed this guide, this is `/software/geant4-v10.7.4-install`. To uninstall Geant4, you can go to the *build directory* and run 

`$ make uninstall`

which will remove all installed files but not any installed directories.

Finally, you need to make Geant4 available to your `PATH` and library path together with a default environment variable for locating datasets. To do this, you should source the relevant script which will be found in `CMAKE_INSTALL_PREFIX/bin` (if you have followed this guide, that is `/software/geant4-v10.7.4-install/bin`.

`$ cd /software/geant4-v10.7.4-install/bin `
`$ source geant4.sh` 

Now, you should be ready to start developing your applications.
#### Option 2. Virtual Machine:
This is the only option supported and recommended for the Geant4 course. [LP2i Bordeaux](https://www.lp2ib.in2p3.fr/), CNRS / IN2P3 / Bordeaux University laboratory provides a free **Geant4 Virtual Machine**, which contains the necessary visualization, development and analysis tools, available on a virtual Linux Machine. The software that I use to run this is [Virtual Box](https://www.virtualbox.org/), developed by Oracle, but free and open-source. Although this is likely to be less powerful than running Geant4 straight in a Linux system, the configuration is simpler, and can be useful to debug code on a clean system, or if no Linux systems are available.



#### Sources:
- [Geant4 Installation Guide](https://geant4-userdoc.web.cern.ch/UsersGuides/InstallationGuide/html/) (CERN)
- [Virtual Box Manual - Introduction](https://www.virtualbox.org/manual/topics/Introduction.html) (Oracle)
- [Geant4 Virtual Machine](https://extra.lp2ib.in2p3.fr/G4/) (LP2i Bordeaux)