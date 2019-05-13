# Dimensionality Reduction on Chemical Pathways

## Objective: Use Python’s sci-kit learn library to reduce the dimensionality of a molecular dynamics trajectory, ultimately those generated in VR. Plot the results. 

### Phase I: Get each task in the dimensionality reduction pipeline working by using starter data
1. *Pre-Processing*  
Take "malonaldehyde.xyz" file and extract the coordinates data into an array that can be used by the processing team.
2. *Processing*   
Use PCA available in sci-kit learn to process a matrix of input data, using one of the datasets included in scikit-learn. A great place to start learning about PCA and how to implement it in Python is [here.](https://jakevdp.github.io/PythonDataScienceHandbook/05.09-principal-component-analysis.html)
3. *Visualization/Plotting*  
Generate 2D and 3D of whatever data you like. The [matplotlib gallery](https://matplotlib.org/gallery/index.html) is a great place for example scripts for various types of plots, e.g., [fancy scatter plots](https://matplotlib.org/gallery/shapes_and_collections/scatter.html#sphx-glr-gallery-shapes-and-collections-scatter-py), [having 2D and 3D plots in the same figure](https://matplotlib.org/gallery/mplot3d/mixed_subplots.html#sphx-glr-gallery-mplot3d-mixed-subplots-py), [ an animated 3D random walk](https://matplotlib.org/gallery/animation/random_walk.html#sphx-glr-gallery-animation-random-walk-py), etc.

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

