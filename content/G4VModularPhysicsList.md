---
title: G4VModularPhysicsList
draft: false
tags:
---

Derived from [[G4VUserPhysicsList]], it extends it by adding several methods, some of these are:
- RegisterPhysics(G4VPhysicsConstructor * )
- GetPhysics(…)
- ReplacePhysics(G4VPhysicsConstructor * )
- RemovePhysics(…)
By using RegisterPhysics, we get a more convenient way of creating a physics list, while preserving the modularity of the original class. Transportation is automatically added with this method. **One must avoid adding the same physics process twice!** Using this method, one is free to add a new constructor or modify the existing ones, some of them are:
### G4VPhysicsConstructor:
Some of the physics lists constructors available are:
- G4EmStandardPhysics: Default EM constructor.
- [G4EmStandardPhysics_option3](https://geant4-userdoc.web.cern.ch/UsersGuides/PhysicsListGuide/html/electromagnetic/Opt3.html#em-opt3): For medical and space science applications.
- G4OpticalPhysics: For processes dealing with optical photons.
- G4IonPhysics: For ion interactions.
The full list can be seen in the toolkit by going to `geant4/source/physics_lists/constructors`. 

### Sources:
- Geant4 Advanced Course (CERN)
- [Physics List Guide](http://cern.ch/geant4-userdoc/UsersGuides/PhysicsListGuide/html/index.html) (CERN)