# Cross-Scale Analysis of Sub-pixel Variations in Digital Elevation Models

Terrain is modeled on a grid of pixels, assuming that elevation values are constant within any single pixel of a Digital Elevation Model (DEM) (a ‘rigid pixel’ paradigm). This paradigm can generate imprecise measurements because it does not account for the slope and curvature of the terrain within each pixel, leading to precious information being lost. In order to improve the precision of interpolated points, the proposed method relaxes the rigid pixel assumption, allowing possible sub-pixel variations (a ‘surface-adjusted’ paradigm) to be used to interpolate elevation of arbitrary points given a regular grid. Tests based on interpolating elevation values for 20,000 georeferenced random points from a DEM are presented, using the rigid pixel paradigm and different interpolation methods (e.g., Weighted Average, Linear, Bi-linear, Bi-quadratic, Bi-cubic, and best fitting polynomials) within different contiguity configurations (i.e., incorporating first and second order neighbors). The research examines the sensitivity of surface adjustment to a progression of spatial resolutions (10, 30, 100, and 1000 m DEMs), evaluating sub-pixel variations that can be directly measured from 3 m resolution LIDAR data.<br>
The workflow involves several steps. Each resolution DEM is input one at a time. The 3 m benchmark DEM is loaded and a random sample of 5000 points is generated, creating a shapefile containing coordinate positions in UTM meters, and elevations in meters extracted from the 3 m benchmark DEM. At this point, the LIDAR DEM is unloaded, and the shapefile is stored on disk. For each of the test DEMs, a nested loop processes each point for all DEMs and for all interpolation methods, then moves on to the next sampled point. Estimated elevations are added as new attributes in the original shapefile. Within the same nested loop, residuals are calculated for each elevation (each sampled point). Once all sampled elevations have been estimated for all DEMs at all resolutions, the residuals are summarized with RMSE standard deviation of residuals, 95% confidence interval and elevation extrema.<br>

Referenec: Ghandehari M., Buttenfield B.P., Farmer C.J.Q. (2017) Cross-Scale Analysis of Sub-pixel Variations in Digital Elevation Models. In: Peterson M. (eds) Advances in Cartography and GIScience. ICACI 2017. Lecture Notes in Geoinformation and Cartography. Springer, Cham
<br>

The code is written in two different ways:<br>
ArcPy: ArcPy is used as the main python module in this code<br>
OpenSources: Open source python modules such as numpy, geopandas,and rasterio are used in this version of code.<br>

![fig1](https://user-images.githubusercontent.com/10367311/43148923-87d2653a-8f23-11e8-9625-3b3cd3105e19.PNG)
(a) The rigid pixel paradigm and (b) the surface-adjusted paradigm. 



