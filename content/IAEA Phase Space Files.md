==Note: IAEA phsp files are currently not working with Geant4==

Phase Space files contain detailed information of particles passing through a volume in Geant4, including things such as the momentum, energy, position or type of the particles. These files can be very useful in speeding up a simulation, or ensuring reproducibility of experiments. We can for example simulate the proton beam interacting with a water phantom, and subsequently use the phase space file of the gammas leaving the phantom as a gamma source for the next simulation, saving time and resources. 

There is more than one format that can be used for phase space files, with Geant even allowing to use root files as input/output or to create your own files. However, there is a standardized format form the International Atomic Energy Agency (IAEA), that has built-in functions to read and write these files.
#### Variables in the IAEA format:
The IAEA format stores positional information about the X,Y,Z coordinates of the particle (in cm) and the first and second direction cosines, together with the sign of the third direction cosine. It also stores the particle type and kinetic energy, and its statistical weight. It has options to include extra integer or float information.

#### Using Phase Space Files in Geant4:
To use the IAEA phase files, one needs:
+ The [read/write routines](https://www-nds.iaea.org/phsp/software/iaea_phsp_Sept2013.zip) 
+ The files defining the classes G4IAEAphspReader and G4IAEAphspWriter, which are not included by default in a Geant4 installation.

The G4IAEAphspReader class is derived from [[G4VPrimaryGenerator]], and substitutes [[G4ParticleGun]] or [[G4GeneralParticleSource]]. Minor things to note about this class are that all the correlated particles are generated in the same event, this implies that a simulation with $n$ events using a G4IAEAphspReader source will have $n$ independent events, and not necessarily $n$ single particles. 

Now the G4IAEAphspWriter class works in a different manner, it is not derived from any basic class, and it simply stores the information during the run. After the run, the writer has created two files, a header and a binary file.  



#### Sources:
- [Geant4 Interface to Work with IAEA Phase-Space Files](https://www-nds.iaea.org/phsp/Geant4/G4IAEAphsp_HowTo.pdf)(IAEA)
- [Phase-space database for external beam radiotherapy](https://www-nds.iaea.org/phsp/phsp.htmlx)(IAEA)