This is the **basic** Geant4 physics list interface, this means that all other physics lists derive from this class, there are two pure virtual methods and thus **must** be implemented, these are:
- **ConstructParticle():** Which creates all the particles needed in the simulation (including secondary particles). Particles can be constructed individually or by using a helper.
- **ConstructProcess():** Which assigns the specific processes to each particle. A process is a reaction probability (measured by the [[cross section]]) and it **models the interaction**, that is, it creates the final state of the interaction. 
### Sources:
- Geant4 Advanced Course (CERN).