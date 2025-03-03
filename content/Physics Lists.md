A physics list is an object responsible of defining how our simulation will behave and what it will take into account. That is specifying all the particles that will be used in the simulation and the processes assigned to each individual particle. It is one of the 3 mandatory objects needed for the [[G4RunManager]]. It can be created modularly by choosing and specifying the particles and processes to be used, or one can select a prebuilt in physics list.

### What physics are included?
In Geant4 we have access to Electromagnetic interactions, which covers the standard processes that we will see in medical physics, together with optical photons; weak interactions, including radioactive decays, and the decay of subatomic particles; and hadronic physics.

### Creating a physics list
There are 3 potential methods for creating a physics list:
1. **The atomistic approach:** The most complex approach is using [[G4VUserPhysicsList]], where the user only has access to a basic interface, and must specify all the particles needed and the processes that each particle can undergo, including transportation, [[cross section]], etc.
3. **The mixed approach:** Using [[G4VModularPhysicsList]], one can use existing physics constructors, but can also create custom physics constructors.
4. **The prepackaged approach:** Finally, one can use G4PhysicsListFactory to select a [[Prepackaged physics list]], these can be extended or modified for particular needs.
### How to select a physics list
If there exists a good understanding of the physics processes involved in the application, one might choose to create its own physics list (preferably via the [[G4VModularPhysicsList]] method), but otherwise, the user can decide to select a [[Prepackaged physics list]] based on the field of the application. 


### Sources:
- Geant4 Advanced Course (CERN).
- [Geant4 Physics in More Detail](https://conferences.fnal.gov/g4tutorial/g4cd/Slides/Fermilab/PhysicsTutor2.pdf) (Fermilab Geant4 Tutorial).