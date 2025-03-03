Geant4 models materials in 3 different ways:
- **G4Isotope**: Describes the properties of the atoms (Z,N and A) with unique name and index. 
- **G4Element**: Describe the properties of elements (effective Z, effective N, effective A, # of isotopes, etc.) with unique name, symbol and index. 
- **G4Material**: Describe the macroscopic properties of matter with unique name and index.

The unique indexes is a pointer to the created object which is automatically stored in the global table. More information can be seen in Material documentation. 

G4Material can be defined as a chemical molecule, in this way, you can define it by adding the number of atoms of each group. It can also be defined as a mixture of elements or materials, which you can do by using the fractional mass rather than the mass of atoms. 

Some materials and elements are already included in Geant4, with their data coming from the National Institute of Standards (NIST) database. Using this database is **recommended** if the materials are available. They can be retrieved by using [[G4NistManager]].

### Sources:
- [Defining Materials in Geant4](http://geant4-resources.com/Geant4Tutorials/G4tutorial_files/006_G4MaterialTutorial_dbrandt.pdf)(Marshall Space Flight Center)