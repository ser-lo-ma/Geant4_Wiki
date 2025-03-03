Geant4 provides a wide variety of “ready-to—use” pre-packaged physics lists, prepared for different use cases. These can simplify the process of creating a simulation, however, not all of them contain every single physics process, not all of them are kept up to date and, in general, the user is responsible for selecting the correct one, as having unnecessary physics processes or missing key interactions can mess the results or reduce the speed of the simulation. All prepackaged physics lists are of the type [[G4VModularPhysicsList]], and physics can be extended or replaced with their methods.

The name of most physics lists follows the convention “name of hadronic inelastic physics constructor” followed by “name of em option”. The lists not following the naming convention are: QBBC, Shielding, LBE and NuBeam. Some of the others include:
- QGS or FTF for the high energy string model (a P in the end indicated the use of a Precompound & De-excitation model for the remnant nucleus).
- BERT, BIC, INCLXX for intermediate energies.
- HP for low energy neutron/particle transport.
- EMY for option 3 electromagnetic physics.
Not every combination of Hadronic and EM physics is available, but they can be created with the G4PhysListFactory method. Out of the lists available, some of the most remarkable are:
- **FTFP_BERT**: Current G4 default
- **QBBC**: For space physics and medical applications (does not include treatment of [[Optical photons]]).  


### Sources:
- Geant4 Advanced Course (CERN)
- [Physics List Guide](http://cern.ch/geant4-userdoc/UsersGuides/PhysicsListGuide/html/index.html) (CERN)