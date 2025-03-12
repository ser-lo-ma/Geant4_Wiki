---
title: G4VUserDetectorConstruction
draft: false
tags:
---

This class provides an “interface” to describe the geometrical setup, including shape, volume, position and [Material definition](obsidian://open?vault=Radiation%20Physics%20Wikia&file=Geant4%20Material%20Modelling) of all volumes in the simulation.

This class contains a few purely virtual methods that must be overran, this includes: 
	- **Construct()**: This method should be implemented in your derive class, it should define all the materials needed, describe the detector geometry by creating and positioning all volumes, and return a pointer to the "World" physical volume.
	- 
- 