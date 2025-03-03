In Geant4, an optical photon is a photon which has $\lambda>>$ atomic spacing. They model the wave-like nature of EM radiation, and they are not the same as a gamma, with no smooth transition existing between the two!

When defined by hand, optical photons need to be given a spin vector, which will describe their polarization. Otherwise, if the correct [[Physics Lists]] are implemented, they can stem from Cerenkov radiation, scintillation processes of transition radiation. Although Geant4 will keep track of the polarization, it does not keep track of overall phase, so it cannot simulate interference.

In Geant4, optical photons can undergo the following processes:
- Refraction and Reflection at medium boundaries.
- Absorption.
- Rayleigh Scattering.

The optical properties of the material are essential to the implementation of these processes and in the case when the material has no optical properties defined, no optical photons will exist in the material. The optical properties available for the materials are:
- Reflectivity
- Transmission efficiency 
- Dielectric constant
- Surface properties (including binned wavelength dependencies)
- Scintillation yield
- Time structure (fast and slow components)


#### Sources:
- [Physics III. SLAC Geant4 Tutorial: version 10.0.p01](https://www.slac.stanford.edu/xorg/geant4/SLACTutorial14/PhysicsIII.pdf) (Stanford)