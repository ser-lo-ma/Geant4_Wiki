G4NistManger is a way to interact with the NIST material database.
#### Elements and isotopes:
This database contains data of more than 3000 isotopes. This includes the elements with Z 1 to 408 and their natural isotope abundance, which can be fetched with either their symbol or atomic number Z. For example:
`G4Element* C = G4NistManager::Instance()->FindOrBuildElement("C")`
`G4Element* Si = G4NistManager::Instance()->FindOrBuildElement(14)`
#### Pre-defined materials:
The database also contains a large collection of pre-defined materials (more than 300). These materials have descriptions of their density, elemental composition (with isotope densities), ionization energy, optical properties... 
Thus, using this materials is preferred to manually modelling when available, as it guarantees a high accuracy (because of the many included parameters) and easy replicability. 
These materials are divided into multiple classes:
- **Single element materials**: For Z values between 1 and 98, these materials are named after the atomic symbol ("G4_Al").
- **Compound NIST materials**: For common real life materials: "G4_AIR", “G4_ALUMINUM_OXIDE”, “G4_MUSCLE_SKELETAL_ICRP”.
- **HEP and Nuclear Materials**: Things such as liquid argon ("G4_lAr"), stainless steel ("G4_STAINLESS-STEEL") or lead tungstate ("G4_PbWO4").
- **Space (ISS) Materials**: Only three available, Kevlar ("G4_KEVLAR"), neoprene ("G4_NEOPRENE") and Dracon polyester fiber ("G4_DACRON"). 
- **Biochemical materials**: The DNA bases: "G4_ADENINE", "G4_GUANINE", etc.
Example code of how to access various materials: 
`G4Material* mat_Al = G4NistManager::Instance()->FindOrBuildMaterial("G4_Al")`
`G4Material* air = G4NistManager::Instance()->FindOrBuildMaterial("G4_AIR")`
`G4Material* liquid_argon = G4NistManager::Instance()->FindOrBuildMaterial("G4_lAr")`
`G4Material* Kevlar = G4NistManager::Instance()->FindOrBuildMaterial("G4_KEVLAR")`
`G4Material* Adenine = G4NistManager::Instance()->FindOrBuildMaterial("G4_ADENINE")`
#### Sources:
- First Steps with Geant4 (CERN)
- [Atomic Weights and Isotopic Compositions with Relative Atomic Masses](https://www.nist.gov/pml/atomic-weights-and-isotopic-compositions-relative-atomic-masses)(NIST)
- [Geant4 Material Database](https://geant4-userdoc.web.cern.ch/UsersGuides/ForApplicationDeveloper/html/Appendix/materialNames.html) (CERN)