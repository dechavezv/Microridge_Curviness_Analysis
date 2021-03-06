# Microridge Curviness Analysis

This program takes pixel coordinate data from images of microridges and analyzes microridge 
curviness. Microridges are small ridges formed by actin protrusions on the surface of skin cells 
which are thought to function in mucus retention. These microridges are imaged on the surface 
of zebrafish skin cells by using LifeAct-GFP transgenic lines, making microridges 
fluorescent. Another member of the lab took these images and has a program that deconvolutes 
this data and turns it into a series of coordinates for each ridge. This program uses that 
existing data and returns an excel file containing a measure of curviness for each microridge.

### Introduction
#### Microridges
Background on microridges.  
Microridge pictures.
#### Analysis
This is how the program analyzes the data.

### Planned Program flowchart (week 6 discussion)
There are a few major problems before I can begin coding, which I have been working on:
1. The x/y coordinates I have are the boundaries of the ridge, not the points contained by the 
ridge. For example, the data points of the ridges for one cell are plotted below.
<img src="https://github.com/hamarkovic/Microridge_Curviness_Analysis/blob/master/W6_Dicussion_whole_cell_example.png" width="50%" height="50%">
    
* One idea to solve this is to simly take the average between each pair of points (example below - blue is the input data, and orange is the averages). However, this is a bit crude.

<img src="https://github.com/hamarkovic/Microridge_Curviness_Analysis/blob/master/W6_Discussion_ex_graph_points.png" width="40%" height="50%"> <img src="https://github.com/hamarkovic/Microridge_Curviness_Analysis/blob/master/W6_Discussion_ex_graph_lines.png" width="40%" height="50%">
    
* The goal is to use the existing data to create a new set of points which better represent
the actual shape of the microridge.

2. The other issue, once a more representative dataset is determined, is how to calculate curvature
from these pixels or lines.
* If all else fails, I could simply calculate the first and second derivative between points (instantaneous derivatives).
The second derivative itself should be a crude measure of curvature, but I can also use a formula
such as this (from [this website](http://tutorial.math.lamar.edu/Classes/CalcIII/Curvature.aspx)). This value for each point of the ridge would most likely be added and divided by ridge length:

<img src="https://github.com/hamarkovic/Microridge_Curviness_Analysis/blob/master/W6_curvature_fomula.png" width="50%">

3. We have not yet started learning R, and I would like to write this program in R.

I have also created a flowchart for how the program should work once these issues are resolved:
1. Get raw data from user, combine cell types with the same manipulation or at the same developmental time point into one table
2. Transform the raw data into points that better represent microridge shape
3. Calculate the curvature of each microridge from these points
4. Output the curvature of each ridge of the cell
5. If this is achieved with time to spare, also output graphs comparing the microridge curvature across manipulations/development.

### Program Usage

#### Requirements
You need to install these things.  
You need these versions of those things.  
The data needs to look like this.
 * You can use this program (cite Aaron's paper) to convert miroridge images to pixels and 
then use my program with the output coordinates..
#### Usage Instructions
This is how to name the input files and how to run the program. These are the outputs that 
the program will give.
#### Test Files
This is a description of how to test that the program is working right.

### Author
* Hannah Markovic
    * incoming Biology PhD student at the University of Oregon
    * B.S. in Molecular, Cell and Developmental Biology with minor in Biomedical Research, 
        expected June 2019, UCLA
    * contact: hannah.markovic@gmail.com
* This program was created as the final project for the class EEB 177, Spring 2019

### Acknowledgements
* Aaron van Loon - data
* Dr. Emily Curd and Daniel Chavez - guidance

### References
* papers
* math
