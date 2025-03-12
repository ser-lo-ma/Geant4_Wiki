---
title: Simulating radioactive decay
draft: false
tags: ""
---

Simulating radioactive decay in Geant4 is not trivial, and although there is no way to create a material that decays with time, a similar effect can be obtained in multiple ways. Both methods use [[G4GeneralParticleSource]]. 
#### With G4RadioactiveDecayPhysics:
Firstly, you need to ensure that your [[Physics Lists]] contains G4RadioactiveDecayPhysics. It might be worth using the registerPhysics method to ensure that it is contained. It is important to note that [[Physics lists]] are initialized after the [[G4VPrimaryGenerator]], so the generator must be initialized with no particle, and then the process for defining the ion must be done in `GeneratePrimaries`. 

Below is included a snippet of code demonstrating how this is done for a Cobalt source:

`MyPrimaryGenerator::MyPrimaryGenerator() {`
    `fParticleSource = new G4GeneralParticleSource();}`

`void MyPrimaryGenerator::GeneratePrimaries(G4Event* anEvent) {`
    `G4int A = 60; // Mass number`
    `G4int Z = 27; // Atomic number`
    `G4double excitationEnergy = 0.0; // Excitation energy in MeV`

	`G4ParticleDefinition* ion = G4IonTable::GetIonTable()->GetIon(Z, A, excitationEnergy);
    `fParticleSource->SetParticleDefinition(ion);
    `fParticleSource->SetParticleCharge(0);
    `fParticleSource->GeneratePrimaryVertex(anEvent);}`

The ion will then decay following the processes established in the physics lists.
#### Without G4RadioactiveDecayPhysics
You can create a simple mono-particle model by using the general particle source and introducing a gamma (for example) with energy give by a histogram distribution of the energies of emission.


#### Sources:
- [Geant4 Tutorial 14: Simulating Radioactive Decays & Energy Deposition](https://www.youtube.com/watch?v=ZQWDjKiCgz4)(Physics Matters - Youtube)