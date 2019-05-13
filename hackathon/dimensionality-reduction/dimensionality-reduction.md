# Dimensionality Reduction on Chemical Pathways

## Objective: Use Python’s sci-kit learn library to reduce the dimensionality of a molecular dynamics trajectory, ultimately those generated in VR. Plot the results. 

### Phase I: Writing a script to reduce dimensionality of a single trajectory using starter data
1. *Pre-Processing*  
Take "malonaldehyde.xyz" file and extract the coordinates data into an array that can be used by the processing team.
2. *Processing*   
Use PCA available in sci-kit learn to process a matrix of input data, using one of the datasets included in scikit-learn. A great place to start learning about PCA and how to implement it in Python is [here.](https://jakevdp.github.io/PythonDataScienceHandbook/05.09-principal-component-analysis.html)
3. *Visualization/Plotting*  
Plot a reduced dimensional chemical pathway in 2D and 3D.

### Phase II: Project new molecular dynamics trajectory of the “training” system into the defined reduced dimensional space
1. *Pre-Processing*  
2. *Processing*  
Fit new data into previously defined space.  
3. *Visualization/Plotting*  
Plot both old and new data in previously defined space.  

### Phase III: Investigate other options 
1. *Pre-Processing*  
Investigate other ways of representing input data (e.g., interatomic distances, intramolecular angles, dihedrals, mass-weighted coordinates, etc.).  
2. *Processing*  
Investigate other dimensionality reduction techniques (e.g., PCA, TICA, kernel PCA, etc.).  
3. *Visualization/Plotting*  
Animated plots, line vs. scatter plots, 2D and 3D plots.  

### Phase IV: Dimensionality reduction on VR trajectories.  

