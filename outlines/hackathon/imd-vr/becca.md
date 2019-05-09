# Code-your-own iMD-VR molecular simulations
This course in focused on creating a virtual reality simulation of the protein-ligand system (blah blah).

## Useful Terminology 
* NarupaXR -
* Amber/AmberTools
* OpenMM -
* VMD
* pdb file - 
* prmtop file - 
* inpcrd file - 
* xml file - 
**More to add later...**

## Set-up
For this course, you will need the following packages installed (which can be done through Anaconda):
* AmberTools19
* VMD
* OpenMM 

## Instructions

1. First, choose a protein-ligand system from the [PDB database](https://www.rcsb.org/) and then download the pdb

2. Now that we have chosen our system, we have to clean it up and make sure it is parameterised correctly! To do this, we will use AmberTools 19. Make sure you have installed AmberTools19, which can be done through [cuda](http://ambermd.org/GetAmber.php)

3. Once AmberTools has been installed, this should give you access to a programme called tLEaP. This is the primary programme to create a new system in Amber, or to modify existing systems. The tutorial that goes through the various steps you need to complete to paramterise your protein and ligand is given [here](http://ambermd.org/tutorials/pengfei/index.htm)

4. Once you have successfully created new Amber topology (.prmtop) and coordinate (.inpcrd) files for your system, you should check that the system looks sensible by checking it in VMD. First, [install VMD](https://www.ks.uiuc.edu/Development/Download/download.cgi?PackageName=VMD)

5. Check your system is sensible by first loading in your .prmtop file, and then loading the .inpcrd file into the molecule. Once your molecule has been loaded in, you can check that everything looks fine by highlighting certain parts of the system separately, such as the protein and the ligand. A useful introductory guide to VMD is given [here](https://chryswoods.com/dynamics/visualisation/mouse.html)

6. Now you are sure your system looks okay, you are ready to make your python script that creates the neccessary files to put your system into NarupaXR! This is done by running a small amount of molecular dynamics (MD) using OpenMM to create a new coordinate (.pdb) file and topology (.xml). The OpenMM documentation provides a introduction on how to write a script to run MD [using Amber files](http://docs.openmm.org/latest/userguide/application.html#using-amber-files). 
You should use this script as a guide, but you are encourgaed to investigate each of the parameters and change them around - the documentation does a good job of explaining what each part of the script does. 
**Note that the OpenMM script in the documentation only gives an output pdb file. To generate an output .xml file, the following lines of code will have to be added to the end of your script**
```
outputFile = 'systemname.xml'
system_xml = mm.XmlSerializer.serialize(system)
with open(outputFile, 'w') as f:
    f.write(system_xml)
```

7. Once your script runs and you get an output .xml and .pdb file, you are ready to put your system into VR. The VR is split into two parts: the *server* and the *frontend*.   (https://intangiblerealities.gitlab.io/narupaXR/md__user_guide__user_guide.html)
