# Code-your-own iMD-VR molecular simulations
This course in focused on creating a virtual reality simulation of the protein-ligand system **neuraminidase and oseltamivir**. The group will be split into 3, where each person will start at a different section in the workflow. You will have ~3 hours to complete each section. 

## Useful Terminology 
* NarupaXR - Software produced by the Glowacki Group at the University of Bristol, for running molecular simulations and interacting with them using Virtual Reality
* Amber/AmberTools - 
* OpenMM -
* VMD - Common visualiser for viewing molecular trajectories in a variety of formats
* pdb file - File format for storing protein structures, containing atom positions, bonds and information about which amino acids are present
* prmtop file - 
* inpcrd file - 
* xml file - Standard file format for storing information. HMTL (language used to write web pages) is an example of XML.
**More to add later...**

## Set-up
For this course, you will need the following packages installed:
* AmberTools19 (installed through Conda)
* OpenMM (installed through Conda)
* VMD

## Instructions
### Step 1: Parameterising your molecule  

1. The first step in being able to visualise a system in VR is making sure your system is parameterised correctly. You must go to the [PDB database](https://www.rcsb.org/) and download the neuraminidase and oseltamivir system, which has the pdb code 3NSS.

2. Now that you have your system, you must clean it up and make sure it is parameterised! To do this, we will use AmberTools 19. Make sure you have installed AmberTools19, which can be done through [cuda](http://ambermd.org/GetAmber.php).

3. Once AmberTools has been installed, this should give you access to a programme called tLEaP. This is the primary programme to create a new system in Amber, or to modify existing systems. The tutorial that goes through the various steps you need to complete to paramterise your protein and ligand is given [here](http://ambermd.org/tutorials/pengfei/index.htm), where you should start at step 3 in the example at the bottom of the page. **Note that you should NOT solvate the system in a perdiodic box of water, as the VR uses implicit solvent, so any comments relating to water can be skipped**

4. Once you have successfully created new Amber topology (.prmtop) and coordinate (.inpcrd) files for your system, you should check that the system looks sensible by checking it in VMD (for example, by highlighting certain parts of the system separately, such as the protein and the ligand). A useful introductory guide to VMD is given [here](https://chryswoods.com/dynamics/visualisation/mouse.html).


### Step 2: Writing OpenMM Scripts 

1. In this section, you will take .prmtop and .inpcrd files generated in Amber for the neuraminidase-oseltamivir system and convert them into files that NarupaRX can understand. The Amber files you will need for this section are [here]**need to add files**. For this section, you will need to write your own python script which calls OpenMM, high performance toolkit for molecular simulation. You can [download OpenMM through anaconda here](https://anaconda.org/omnia/openmm).

2. Once you have installed OpenMM, you can now start writing your Now you are sure your system looks okay, you are ready to make your python script that creates the neccessary files to put your system into NarupaXR! This is done by running a *very small* amount of molecular dynamics (MD) through OpenMM to create a new coordinate (.pdb) file and topology (.xml). The OpenMM documentation provides a introduction on how to write a script to run MD [using Amber files](http://docs.openmm.org/latest/userguide/application.html#using-amber-files). 

You should use their example script as a guide, but you are encourgaed to investigate each of the parameters and change them around - the documentation does a good job of explaining what each part of the script does. For example, as the system has no explicit solvent molecules, you should add something that adds some implicit solvent to the system. 

**Note that the OpenMM script in the documentation only gives an output pdb file. To generate an output .xml file, the following lines of code will have to be added to the end of your script**
```
outputFile = 'systemname.xml'
system_xml = mm.XmlSerializer.serialize(system)
with open(outputFile, 'w') as f:
    f.write(system_xml)
```

3. Once your script runs and you get an output .xml and .pdb file, you are ready to put your system into VR. The VR is split into two parts: the *frontend* and the *server*. The frontend is the part which visualises the system you have sent to the VR. The server is the part which actually reads in the files you want to visualise. To be able to see your molecule in VR you must send all of the information about it to the server in a file which wraps everything together - an example of a very basic version is [here](https://github.com/davidglo/TMCS-2019/blob/master/hackathon/imd-vr/vr_openmm_template.xml). Add the path to your files and then look at the [documentation](https://intangiblerealities.gitlab.io/narupaXR/md__user_guide__user_guide.html) to see if you can add/modify any parts of this script.

### Step 3: Manipulation in NarupaXR 
*steps 1 and 2 do not depend on eachother and can be performed in either order*

1. This section is focused on i) editing the script which contains all of the information that NarupaXR needs to be able to visualise your system and ii) making selections and getting to grips with molecular manipulation in VR. First, download the server file which is needed to be able to launch NarupaXR [here] **need to add the file!!!**. This is a very basic version of the server script - there are many things which can be added to change your experience in VR. Check out the VR documentation [here](https://intangiblerealities.gitlab.io/narupaXR/md__user_guide__user_guide.html) to see what else can be added to this file! *hint: how can you record what pathways you are going to generate in VR?* Save your server file in a 

2. Now that you have your server file you are ready to launch your VR simulation! This can be done by navigating to the programme itch, then clicking on NarupaXR, then Launch -> Server and VR. Once in VR, you are free to play around with your simulation! You will notice that there are two types of mode: Interaction Mode and Selection Mode. Interaction Mode allows you to (you guessed it) interact with your simulation, whereas Selection mode allows you to select and change various parts of your system. Try doing the following things in Selection Mode:
i) Select oseltamivir and group all the atoms together
ii) Colour in residues 70 and 71 a different colour
iii) Make the remaining protein backbone rigid and a different color
iv) Choose different renderers (i.e. ball and stick etc.) for each of the selections mentioned above
Have fun! See what selections and trajectories you can generate. 

