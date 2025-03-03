==INCOMPLETE==

When dealing with [[Optical photons]], we have the possibility to define optical surfaces, which will define the processes occurring at the boundary of a volume. The boundary processes are called at the end of each step, but never limit the step length, it only occurs if the step is meant to start in one volume, but finish in the other one. Furthermore, because Geant4 simulated “particle-like” behavior, there is no possible “splitting” of the tracks, ie. Photons are either reflected or refracted, but both cannot happen at the same time. **When no optical surface is defined, reflection is simulated as purely geometrical;** and when we create an optical surface with no parameters, it works with diffusive reflection. The surfaces modeling these behaviors can be defined in two ways:
#### GLISUR MODEL:
Original model from G3; currently depreciated.
#### UNIFIED MODEL:
There are two possibilities In terms of surfaces:
- Dielectric-metal: Photon is either absorbed or reflected.
- Dielectric-dielectric: Photon can undergo total internal reflection, Fresnel refraction or Fresnel reflection. This depends on $\lambda$, polarization and refractive indexes.
With a few options for the surface finish afterwards: 
- **Polished**: In this model, we define the normal used by the G4BoundaryProcess as the normal to the surface of either the daughter solid being entered or the solid being left behind.
- **Ground:** In this model, as the photon enters a rough surface, we define the normal by selecting an angle $\alpha$ between the surface normal and the normal of a micro-facet. The model assumes that the probability of selecting an angle in $\sin{(\alpha)} d\alpha$  is Gaussian.
#### Sources:
1. [Optical Photon Processes in GEANT4, Peter Gumplinger, TRIUMF/GEANT4 G4 Space Users’ Forum at ESTEC, January 2003](https://indico.esa.int/event/48/contributions/2528/attachments/2039/2387/G4SpaceForum_Optical.pdf) (ESA)
2. [Physics III. SLAC Geant4 Tutorial: version 10.0.p01](https://www.slac.stanford.edu/xorg/geant4/SLACTutorial14/PhysicsIII.pdf) (Stanford)
3. [Peculiarities in the Simulation of Optical Physics with Geant4](https://arxiv.org/abs/1612.05162)