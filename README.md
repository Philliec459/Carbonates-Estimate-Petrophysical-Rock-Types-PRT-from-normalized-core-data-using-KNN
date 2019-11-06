# Estimate-Petrophysical-Rock-Types--PRT--from-normalized-core-data-using-KNN
Predict Petrophysical Rock Types (PRT)

This repository utilizes normalized core data with Euclidean distance-weighted estimations for only the KNN samples being considered. This program queries the Petrophysical Rock Types (PRT) as published in a paper containing this carbonate core analysis database with Thomeer Capillary Pressure parameters1.

Clerke acquired over 400 High Pressure Mercury Injection Capillary Pressure (HPMI) measurements and fit Thomeer hyperbolas to these data to generate the Thomeer Capillary Pressure parameters Bulk Volume Occupied (BVi), Variability of Pore Throats (Gi) and Initial Displacement Pressures (Pdi) for each pore system i. From these data he established the PRTs for this Arab D carbonate reservoir. The bulk of the work by Clerke establishing the PRTs was based on the Initial Displacement Pressures for each pore system and the number of pore systems present in each sample. From the figure below it is rather evident that Clerke's methods created rather well defined PRTs as shown in the Figure below where each color represents a different PRT.  The Capillary Pressure curves and Pore Throat Distributions (PTD) shown on the right hand side of the figure show the uniqueness of each PRT. 

![TS_Image](PRT.png)

The PRTs are defined as follows:


Rock Index	Clerke PRT 	Size of Pore System			Color

1		M_1		Macro with Meso Grains			Cyan
2		M_2		Macro with Micro Grains			Dodger-Bule
3		M_1_2		Macro with Meso and Micro Grains	Blue
4		1		Meso Porous Rock			Yellow
5		1_2		Meso and Micro Poros Rock		Orange
6		>2		Micro Porous Rock			Brown

As can be seen in the figure above the PRTs are rather well segregated on the Porosity vs. Permeability Cross Plot. In addition, the correlation of Permeability vs. the Mode of the Pore Throats (Mode) has a high correlation with an correlation coefficient (r2) of 0.88 and Pd1 correlates to the Mode with a correlation coefficient of 0.99, where mode is calculated from the Thomeer Parameters:

	Mode = exp(-1.15*G1) * (214/Pd1)

The calculated Mode above as at the exact peak of the Pore Throat Distribution and does relate to the most abundant Pore Throat in the sample. We have found that the Mode of the PTD is very useful in the 3D modeling of Petrophysical Properties in both Carbonate and Clastic reservoirs. 


For this repository we are using the inverse of the Euclidean distances for normalized porosity and permeability data to generate the distance-weighted KNN PRTs for each poro-perm combination. This process is based on the Euclidean distance difference between the normalized core analysis reference poro-perm data vs. the normalized user defined poro-perm combination and the inverse of the n nearest Euclidean distances are the only values being used for the distance-weighted averages. 



1 Clerke, E. A., Mueller III, H. W., Phillips, E. C., Eyvazzadeh, R. Y., Jones, D. H., Ramamoorthy, R., Srivastava, A., (2008) “Application of Thomeer Hyperbolas to decode the pore systems, facies and reservoir properties of the Upper Jurassic Arab D Limestone, Ghawar field, Saudi Arabia: A Rosetta Stone approach”, GeoArabia, Vol. 13, No. 4, p. 113-160, October, 2008. 

