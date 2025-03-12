---
title: Geant4 Lecture Notes
draft: false
tags:
---

#### What is this?
This is a compilation of my notes on Geant4, including everything I have learned in the “First Steps with Geant4“ course from CERN or from different sources. It is not guaranteed that anything in this notes is right or the full picture, they are simply my way to compile and synthesize all of the things that I have learned in this journey. Enjoy.
#### What is Geant4:
Geant4 is a toolkit specially used for simulating the passage of particles through matter by using Monte Carlo Methods and [[Random numbers]]. It provides all the necessary components to describe and solve particle transport simulation problems.

The user defines the geometry, particles, physics… and obtains the step by step particle transport computation (with possible interaction points for the user). The best source of documentation for us is the [Book For Application Developers](https://geant4-userdoc.web.cern.ch/UsersGuides/ForApplicationDeveloper/fo/BookForApplicationDevelopers.pdf), although it is very complex and its easy to get lost in it.

There are some components of a simulation which are mandatory and needed for every simulation, these are the geometry, physics and primary particle generators, which change from program to program. Through our projects, we will see classes named G4…, these are classes provided by the toolkit. Often we will see them followed by the letter V (G4V…) these are virtual classes.
#### Steps to begin a simulation:
This assumes you have already installed Geant4 by following the [[Geant4 Installation Guide]].

1. You need to create a [[G4RunManager]] object, the **only** fully necessary object that needs to be created by the user.
2. This run manager will then require three things:
	 1. A [[G4VUserDetectorConstruction]] object, which will describe the experimental setup, geometry and materials. 
	 2. A [[G4VUserPhysicsList]] object, which will explain the allowed particles, processes and energies. (For more information see [[Physics Lists]]).
	 3. A [[G4VUserActionInitialization]], which contains a [[G4VUserPrimaryGeneratorAction]] object, describing how the original particles in the simulation are produced.
3. There are many more actions that can be added, such as a [[G4UserRunAction]], [[G4UserEventAction]], [[G4UserSteppingAction]], etc. 


### Sources:
- First Steps with Geant4 (CERN)