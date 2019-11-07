# Estimate-Petrophysical-Rock-Types--PRT--from-normalized-core-data-using-KNN
Predict Petrophysical Rock Types (PRT)

The objective of this project is to estimate Petrophysical Rock Types (PRTs) as defined by Clerke(1) for the Arab-D carbonate reservoir using just Porosity and Permeability. This project utilizes normalized Porosity and Permeability values. We calculate the Euclidean distance between the reference data and the normalized user defined poro-perm and determines the most likely PRT for the user defined values. 

The Arab D data set from Clerke is quite distinctive. Clerke acquired nearly 450 High Pressure Mercury Injection Capillary Pressure (HPMI) measurements in the Arab D reservoir; however, Clerke's final samples were randomly selected from 1,000's of pre-qualified core samples ensuring a broad distribution and representation of all Petrophysical properties.  Clerke fit a Thomeer hyperbolas to each pore system in each sample to generate the published Thomeer Capillary Pressure parameters including Bulk Volume Occupied (BVi), curvature of Capillary Pressure curve related to the variability of pore throats (Gi) and the Initial Displacement Pressures (Pdi) for each pore system i. From these data Clerke established the PRTs based on the Initial Displacement Pressures for each pore system and the number of pore systems present in each sample. From the figure below it is rather evident that Clerke's PRTs are Petrophysically well-defined where each color represents a different PRT.  The Capillary Pressure curves and Pore Throat Distributions (PTD) shown on the right hand side of the figure illustrate the unique characteristics of each PRT. 


![TS_Image](PRT.png)


The characterization of each PRTs is shown below:


![TS_Image](Rock-Types.png)


As can be seen in the first figure above, the PRTs are rather well segregated on the Porosity vs. Permeability Cross Plot as they fall in distinct regions or clusters on the Cross Plot. 

For modeling purposes it is important to take advantage of the excellent correlations between the Thomeer Capillary Pressure parameters. the correlation of core Permeability vs. the Mode of the Pore Throats Distribution has a high correlation coefficient of 0.88. Pd1 correlates to the Mode of the PTD with a correlation coefficient of 0.99. The Mode of the PTD can be calculated directly from the Thomeer Parameters using the following equation:

	Mode of PTD (microns) = exp(-1.15*G1) * (214/Pd1)

The calculated Mode of PTD above is located at the exact peak of the Capillary Pressure derivative-derived Pore Throat Distribution for the most dominate pore size, and this represents the most abundant pore throat for the sample. We have found that the Mode of the PTD to be very useful in the 2D and 3D modeling of Petrophysical Properties for both Carbonate and Clastic reservoirs. Winland's r35 tries to approximate the mode; however, Amaefule's FZI is the mean pore throat radius and falls between the two modes of a bi-modal carbonate sample. 







1 Clerke, E. A., Mueller III, H. W., Phillips, E. C., Eyvazzadeh, R. Y., Jones, D. H., Ramamoorthy, R., Srivastava, A., (2008) “Application of Thomeer Hyperbolas to decode the pore systems, facies and reservoir properties of the Upper Jurassic Arab D Limestone, Ghawar field, Saudi Arabia: A Rosetta Stone approach”, GeoArabia, Vol. 13, No. 4, p. 113-160, October, 2008. 

