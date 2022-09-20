# **Evaluating Uncertainty in Remotely-Sensed Irrigation Estimates for the SD-6 LEMA**

Ashley Grinstead, Sam Zipper

Kansas Geological Survey, University of Kansas, Lawrence, Kansas, USA

## **1. Executive Summary**

Agriculture is globally the main consumer of freshwater resources worldwide, and 20% of irrigation water is nonrenewable groundwater (Deines et al., 2020; Foster et al., 2021). Because the majority of agricultural water use is not monitored, irrigation is difficult to measure. As a result, aquifer depletion is happening at a rapid rate and threatening local economies and remote sensing has been proposed as a way to fill in these data gaps (Foster et al., 2021). In the central High Plains Aquifer in the United States, farmers in Kansas have turned to self-governing methods in efforts to preserve groundwater aquifers that are used for irrigation. In response, the Kansas Geological Survey (KGS) proposed to investigate how socio-environmental and institutional diversity determines how well groundwater self-governance regimes do in response to social and environmental change at different scales (DISES). The plan will help groundwater-dependent agriculture communities create more effective, resilient, and adaptive groundwater management strategies (DISES). The purpose of this study is to identify the uncertainties and effectiveness of using satellite-based evapotranspiration data to estimate irrigation and identify different conservation practices. Our findings show that irrigation efficiency improvements, fallowing, and changing crops can be identified as soon as the first cycle of the Local Enhanced Management Area (LEMA) begins, but starts showing an increase after the first few years and into the second cycle. Our findings also highlight that OpenET can accurately be used for estimating irrigation, but further research would be required to understand how other components of water balance affect these calculations.

## **2. Motivation & Goals**

### **2.1 Questions**
Can different conservation practices be detected in the overall LEMA?

- What types of uncertainties exist in estimating irrigation from evapotranspiration data and why are they important?
- How do estimates of irrigation from evapotranspiration data compare to field measurements of water use?
- How can conservation practices in the LEMA and non-LEMA be evaluated?

**2.2 SD-6 LEMA**

The study site for this project is the Sheridan County 6 (SD-6) LEMA in the Northwest Kansas Groundwater Management District (GMD) 4. This region was of focus due to the unique stakeholder-driven groundwater management framework that was put in place to conserve groundwater in an area with no flowing perennial streams. The LEMA works in 5 year cycles, where the first one lasted from 2013-2017 and was renewed for 2018-2022. The goal was to reduce groundwater pumping by 20% compared to 2002-2012 levels, so groundwater allocation was restricted to 55 acre inches per irrigated acre with a maximum carry-over amount of 11 in for the next cycle.

![](https://www.agriculture.ks.gov/images/default-source/wms-images/sd6boundary.png?sfvrsn=68a6e98e_6) **Figure 1.** This map was taken from the Kansas Department of Agriculture’s website showing the spatial outline of the SD-6 LEMA. The Thomas and Sheridan counties are labeled and the yellow shaded area is the location of the LEMA. The LEMA is located within GMD 4 in the United States High Plains Aquifer.

## **3. Data**

**Table 1.** Description and characteristics of the data used.
| Dataset | Type of Data | Years | Description |
|---------|--------------|-------|-------------|
| OpenET | Evapotranspiration | 2016-2021 | Monthly open satellite-based estimates of ET for the SD-6 area and surroundings; 7 datasets consisting of 6 different algorithms (**eeMetric, DisALEXI, geeSEBAL, PT-JPL, SIMS, SSEBop**) + an average of all the algorithms (**Ensemble**) |
|POLARIS | Soil | N/A | 30-m probabilistic soil property data in the SD-6 area and surroundings using only 10 relevant soil properties: **silt**: silt (%), **sand**: sand (%), **clay**: clay (%), **theta_s**: saturated soil water content (m3/m3), **theta_r**: residual soil water content (m3/m3), **ksat**: saturated hydraulic conductivity (log10(cm/hr)), **lambda**: pore size distribution index (brooks corey), **hb**: bubbling pressure (brooks corey), **n**: measure of the pore size distribution (van genuchten), **alpha**: scale parameter inversely proportional to mean pore diameter (van genuchten) (log10(kPa-1)) | 
| gridMET | Meteorological | 2000-2021 | Monthly meteorological clipped to the SD-6 LEMA and surroundings | 
| AIM-HPA | Irrigation Status | 1984-2020 | Annual data for irrigation status clipped to the SD-6 area and surroundings | 
| Cropland Data Layers | Land use/Land cover | 2006-2020 | Annual crop-specific land cover data clipped to the SD-6 area and surroundings | 
| WIMAS | Flowmeter well data | 1990-2020 | Annual data for wells clipped to the SD-6 area and surroundings for total acre-feet of water used, reported irrigated acres, and total acre-feet of water used for irrigation |

![](/images/ChangeInCrops.png) **Figure 2.** Total area in km^2^ of all crops grown in the SD-6 LEMA in irrigated and rainfed fields. The red dashed line marks the beginning of the LEMA. AIM data was used as a standard for classifying the fields as irrigated (fields 50% irrigated and above) and rainfed (fields under 50% irrigated). Corn was the dominant crop in irrigated fields while rainfed fields had a variety of corn, grass/shrub, and winter wheat. 

![](/images/SpatialViz.png) **Figure 3.** Spatial visualizations of some of the data we worked with including the percentage of irrigated fields for 2016, precipitation for 2016, crop type for 2016, and mean evapotranspiration for the Ensemble algorithm from OpenET.

![](/images/SoilContent.png) **Figure 4.** Soil content maps showing the percentages of sand, silt, and clay for various depths in the SD-6 LEMA.

## **4. What types of uncertainty exist in estimating irrigation from ET data?**

![](/images/workflow.png)
**Figure 5.** Flow chart of the workflow for this analysis. The blue boxes represent the data we worked with and the red boxes represent the uncertainties we encountered when sorting through the data. 

### **4.1 Irrigation Uncertainty**
After researching different methods of estimating irrigation from evapotranspiration, we decided to use 

Irrigation (m^3^) = (ET (mm) - P (mm) / 1000 (mm)) x (m) x area of field (m^2^)

This equation was inspired by the equation found in *Integrated Groundwater Management: Concepts, approaches, and challenges* written by Eamus et al., where (ET - P)*NDVI** was used to find the amount of groundwater transpired by crops. 

### **4.2 Evapotranspiration Algorithm Uncertainty**
OpenET provides satellite-based evapotranspiration estimates based on an ensemble of 6 different evapotranspiration models that rely on publicly available data. The majority of the algorithms are based on the full or simplified versions of the Surface Energy Balance model, which accounts for the energy used for the process of evapotranspiration (OpenET). Specifically, the algorithms METRIC, geeSEBAL, and DisALEXI estimate energy balance using optical (short-wave) and thermal (long-wave) data. SSEBop and PT-JPL use simplifying assumptions where some of the variables in energy balance aren’t estimated or calculated. SIMS relies on surface reflectance data and crop type information to compute evapotranspiration as a function of canopy density using a crop coefficient approach for agricultural land. Additionally, each algorithm used to calculate the ensemble for OpenET are all slightly different when estimating evapotranspiration, meaning different types of biases can occur. For convenience, a short description of the known biases are listed below in Table 2. Details about each bias can also be found on OpenET’s website.

For this study, we also wanted to visualize the distributions of each algorithm to better understand the different biases. In Figure 6, the distribution of the ET-P values are shown as histograms. The AIM data was masked over these values to determine which fields were irrigated and rainfed. Looking vertically at the plot, you can tell which years were irrigated less since the distribution for each algorithm shifted towards the left side of the x-axis. SIMS is an interesting algorithm since the distribution is bimodal, and we predict that there were two crops that stood out to that algorithm.

Figure 7 zones in on fields in the SD-6 LEMA that are only producing corn. The bins for these histograms were lowered from 100 to 10 due to having less data to work with. The AIM data was also masked over these values. These distributions are more difficult to identify irrigated and rainfed fields since the majority of the histograms have overlap. 2016 and 2019 seem to have the least amount of overlap as the two field categories are easier to distinguish. These years also seem to have been wetter. eeMETRIC and SSEBop are the two algorithms that show the least amount of overlap as well, [something to do with the biases].

![](/images/fieldsIrrigationEstimates.png)
**Figure 6.** Histograms displaying the different distributions of precipitation deficit in each field in each algorithm. Each row accounts for a different algorithm, and each column represents a different year. AIM data was masked over the estimated irrigation to separate the fields into irrigated and rainfed using the condition that irrigated fields were fields with an irrigated percent of 50 and above and rainfed fields were fields with an irrigated percent of below 50.

![](/images/CornIrrigationEstimates.png)
**Figure 7.** Histograms that show the distribution of precipitation deficit in fields that only produce corn. Each row accounts for a different algorithm, and each column represents a different year. AIM data was masked over the estimated irrigation to separate the fields into irrigated and rainfed using the condition that irrigated fields were fields with an irrigated percent of 50 and above and rainfed fields were fields with an irrigated percent of below 50.

### **4.3 Precipitation Data Uncertainty**
The gridMET precipitation data had 20 fields out of 11,314 fields with missing values. To fill in the missing data, a gap-filling script [link to Appendix/Github] that used the nearest-neighbor method was used to find the precipitation value of the nearest field. The probability that this affected the ET-P calculation is significantly low, but the missing values in the dataset is worth noting.

### **4.4 Irrigation Status Uncertainty**
The uncertainty with the irrigation status was that the percent of fields irrigated had a wide range of percentages. To simplify the classification of irrigated and rainfed fields, a condition was set where every field that had an irrigation status 50% and above was considered irrigated and every field below 50% was considered rainfed. Realistically, the known irrigated fields were fields that had an irrigation percentage of 100% and known rainfed fields were fields that had an irrigation percentage of 0%. We also had a high confidence that fields with an irrigated percentage from 0-30% were rainfed and 60-100% were irrigated, but low confidence emerged from fields that were 30-60% irrigated. 

### **4.5 Crop Data Uncertainty**
The uncertainty with crop type data appeared in 7 out of the total 11,314 fields where two crops were listed. The UID of the fields are 347501 (2008), 349849 (2013), 351319 (2009), 374066 (2016), 374319 (2010), 1371395 (2013), and 1371712 (2017). Only 3 out of 1538 fields in the LEMA had two crops listed (UID: 347501, 351319, 1371395). These fields were ignored when Figure 2 was made, as well as any other analysis using the CDL dataset.

## **5. How do estimates of irrigation from ET data compare to field measurements of water use?**
In this comparison, we chose to only look at the mean ET estimates from the OpenET ensemble because it has been proven that when estimates from an ensemble of models are combined, they tend to be more accurate than an individual model [(OpenET)](https://openetdata.org/methodologies/). Figure 8 shows that the estimates of irrigation from the ensemble compare very well to the WIMAS field measurements of water use. The measured irrigation is plotted against the estimated irrigation and shows a line of best fit being y = 0.020033 x + (-251073.211288) and the R^2^ = 0.94. The uncertainty lies with the measured irrigation being two orders of magnitude larger than the irrigation estimates.

![](/images/MeasuredvEstimatedIrr.png)
**Figure 8.** Scatter plot of measured irrigation from WIMAS flowmeter data in m3 plotted against the estimated irrigation derived from ET-P using the mean ensemble ET values for the irrigated fields in the SD-6 LEMA. The equation for the line of best fit is y = 0.020033 x + (-251073.211288) and the R^2^ = 0.94. 

## **6. Evaluating Conservation Practices In and Out of the LEMA**

### **6.1 Efficiency Improvements**
Efficiency improvements could be identified in Figure 9 where there was a switch from corn to sorghum after the first LEMA began in 2013. After the second LEMA began in 2018, there was another increase in sorghum but the total acres seemed to decrease throughout the LEMA. Switching to sorghum suggests that sorghum requires less water than corn, allowing farmers to meet the goals of the LEMA. More research would need to go into the economics behind switching corn and sorghum.

![](/images/ChangeInCornSorghum.png)
**Figure 9.** Barplot showing the total acres of irrigated and rainfed fields in the LEMA that produced corn and sorghum. Every year to the left of the red dashed line is before the LEMA begins and every year to the right of the red dashed line is during the LEMA. 

### **6.2 Changes in Crop Type**
Changes in crop type can also be identified in Figure 9 where irrigated fields show an increase in sorghum and a decrease in corn after the LEMA begins. Sorghum peaks in 2014, then starts to decrease through 2020 while acres of corn grown starts increasing. The same pattern is also shown in rainfed fields. The bar plot also shows that the most acres producing corn in the LEMA is in 2020. Figure 9 suggests that a change in crop type was observed for the first cycle of the LEMA, but was brushed off in the second cycle. 

### **6.3 Changes in Fallowing**
Fallowing is when farmland is left alone for a few weeks to over a year without planting any seeds so that the soil can regain nutrients it might have lost during the growing season. It is also an important conservation practice because it allows ___. Figure 10 shows the total area of irrigated fields in the SD-6 LEMA. The general trend seems that the total amount of irrigated acres increased over time, but every other year shows that the total amount of irrigated fields was less than the previous year, indicating that fallowing might have been practiced during the LEMA. 

![](/images/ChangeInAIM.png)
**Figure 10.** Barplot showing the total area in acres of irrigated fields in the SD-6 LEMA. This is based on the condition that was produced from the AIM data where irrigated fields were fields with an irrigated percent of 50 and above. The plot shows an increase in irrigation after the LEMA begins.

## **7. Future Work**
Since this study only spanned 12 weeks, it serves as a building block for future research. Questions that we came up with but could not explore include:
- What other data should OpenET be coupled with so that farmers can accurately make self-governing management decisions?
- What other analyses would be useful?
- How can water savings be quantified from the LEMA and how can they be attributed to specific management actions and decisions?
- What other factors in the soil water balance model play a significant role in estimating groundwater reliant irrigation? 

## **8. Appendix & Sources**
- Reference code used to make figures
- Deines, Jillian M., et al. “Combining Remote Sensing and Crop Models to Assess the Sustainability of Stakeholder-Driven Groundwater Management in the US High Plains Aquifer.” Water Resources Research, vol. 57, no. 3, 2021, p. e2020WR027756. Wiley Online Library, https://doi.org/10.1029/2020WR027756.
- Foster, T., et al. “Satellite-Based Monitoring of Irrigation Water Use: Assessing Measurement Errors and Their Implications for Agricultural Water Management Policy.” Water Resources Research, vol. 56, no. 11, 2020, p. e2020WR028378. Wiley Online Library, https://doi.org/10.1029/2020WR028378.
- Vogels, Marjolein F. A., et al. “An Object-Based Image Analysis Approach to Assess Irrigation-Water Consumption from MODIS Products in Ethiopia.” International Journal of Applied Earth Observation and Geoinformation, vol. 88, June 2020, p. 102067. ScienceDirect, https://doi.org/10.1016/j.jag.2020.102067.
- Eamus, D., Fu, B., Springer A., E, Stevens, L.E. (2016). Groundwater dependent ecosystems: Classification, identification techniques and threats. In A.J. Jakeman, O. Barretaeu, R. J. Hunt, J.D. Rinaudo, A.R. Ross (Eds.), Integrated Groundwater Management: Concepts, approaches, and challenges (pp. 332)SpringerOpen. 10.1007/978-3-319-23576-9
- https://agriculture.ks.gov/divisions-programs/dwr/managing-kansas-water-resources/local-enhanced-management-areas/sheridan-county-6-lema
- https://openetdata.org/methodologies/
