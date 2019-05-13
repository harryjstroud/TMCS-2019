# Dimensionality Reduction on Chemical Pathways

## Objective: Use Python’s sci-kit learn library to reduce the dimensionality of a molecular dynamics trajectory, ultimately those generated in VR. Plot the results. 

### Phase I: Writing a script to reduce dimensionality of a single trajectory
1. *Pre-Processing*  
Take a file in xyz or pdb file format and extract the coordinates data into an array that can be used by the processing team.
2. *Processing*   
Use PCA available in sci-kit learn to process Cartesian coordinates of input data. 
3. *Visualization/Plotting*  
Plot PCs of reduced dimensional chemical pathway in 2D and 3D.

### Phase II: Dimensionality reduction on VR trajectories.  
1. *Pre-Processing*  
Make sure pre-processing code is able to handle data from VR (depending on the size, consider using VMD to select a subset of the coordinates). 
2. *Processing*  
Do PCA on this new matrix of structures.  
3. *Visualization/Plotting*  
Plot PCs of pathways in VR. 

### Phase III: Project new molecular dynamics trajectory of the “training” system into the defined reduced dimensional space
1. *Pre-Processing*  
Make sure pre-processing code is able to handle this new data. 
2. *Processing*  
Fit new data into previously defined space.  
3. *Visualization/Plotting*  
Plot both old and new data in previously defined space.  

### Phase IV: Investigate other options 
1. *Pre-Processing*  
Investigate other ways of representing input data (e.g., interatomic distances, intramolecular angles, dihedrals, mass-weighted coordinates, etc.).  
2. *Processing*  
Investigate other dimensionality reduction techniques (e.g., PCA, TICA, kernel PCA, etc.).  
3. *Visualization/Plotting*  
Animated plots, line vs. scatter plots, different color maps.  



