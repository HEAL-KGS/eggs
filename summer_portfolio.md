# **Evaluating Uncertainty in Remotely-Sensed Irrigation Estimates for the SD-6 LEMA**

Ashley Grinstead, Sam Zipper

Kansas Geological Survey, University of Kansas, Lawrence, Kansas, USA

## **Executive Summary**

Agriculture is globally the main consumer of freshwater resources worldwide, and 20% of irrigation water is nonrenewable groundwater (Deines et al.,2020; Foster et al., 2021). Because the majority of agricultural water use is not monitored, irrigation is difficult to measure. As a result, aquifer depletion is happening at a rapid rate and threatening local economies, therefore remote sensing has been proposed as a way to fill in these data gaps (Foster et al., 2021). In the central High Plains Aquifer in the United States, farmers in Kansas have turned to self-governing methods in efforts to preserve groundwater aquifers that are used for irrigation. In response, the Kansas Geological Survey (KGS) proposed to investigate how socio-environmental and institutional diversity determines how well groundwater self-governance regimes do in response to social and environmental change at different scales. The plan will help groundwater-dependent agriculture communities create more effective, resilient, and adaptive groundwater management strategies (DISES). The purpose of this study is to analyze OpenET, a new evapotranspiration dataset, along with other datasets to identify the uncertainties and effectiveness of using satellite-based evapotranspiration data to estimate irrigation and identify different conservation practices. Our findings show that irrigation efficiency improvements, fallowing, and changing crops can be identified as soon as the first cycle of the Local Enhanced Management Area (LEMA) begins, but starts showing an increase after the first few years and into the second cycle. Our findings also highlight that OpenET can accurately be used for estimating irrigation, but further research would be required to understand how other components of water balance affect these calculations.

## **Motivation & Goals**

### Questions
Can different conservation practices be detected in the overall LEMA?

- What types of uncertainties exist in estimating irrigation from evapotranspiration data and why are they important?
- How do estimates of irrigation from evapotranspiration data compare to field measurements of water use?
- How can conservation practices in the LEMA and non-LEMA be evaluated?

Study site at SD-6 LEMA + brief overview

![](https://www.agriculture.ks.gov/images/default-source/wms-images/sd6boundary.png?sfvrsn=68a6e98e_6)

## **Data**

| Dataset | Type of Data | Years | Description |
|---------|--------------|-------|-------------|
| OpenET | Evapotranspiration | 2016--2021 | Monthly open satellite-based estimates of ET for the SD-6 area and surroundings; 7 datasets consisting of 6 different algorithms (**eeMetric, DisALEXI, geeSEBAL, PT-JPL, SIMS, SSEBop**) + an average of all the algorithms (**Ensemble**) |
|POLARIS | Soil | N/A | 30-m probabilistic soil property data in the SD-6 area and surroundings using only 10 relevant soil properties: **silt**: silt (%), **sand**: sand (%), **clay**: clay (%), **theta_s**: saturated soil water content (m3/m3), **theta_r**: residual soil water content (m3/m3), **ksat**: saturated hydraulic conductivity (log10(cm/hr)), **lambda**: pore size distribution index (brooks corey), **hb**: bubbling pressure (brooks corey), **n**: measure of the pore size distribution (van genuchten), **alpha**: scale parameter inversely proportional to mean pore diameter (van genuchten) (log10(kPa-1)) | 
| gridMET | Meteorological | 2000-2021 | Monthly meteorological clipped to the SD-6 LEMA and surroundings | 
| AIM-HPA | Irrigation Status | 1984-2020 | Annual data for irrigation status clipped to the SD-6 area and surroundings | 
| Cropland Data Layers | Land use/Land cover | 2006-2020 | Annual crop-specific land cover data clipped to the SD-6 area and surroundings | 

![](/images/IrrigatedRainfedCropCount.png)


## **What types of uncertainty exist in estimating irrigation from ET data?**

Workflow Chart
![](/images/workflow.png)
Figure 1: Flowchart showing my workflow for this project.

How I came up with ET-P for estimated irrigation


## **How do estimates of irrigation from ET data compare to field measurements of water use?**



## **Evaluating Conservation Practices in LEMA/Non-LEMA**

### Changes in Fallowing

### Changes in Crop Type

![](/images/ChangeInCrops.png)

### Changes in Irrigation Efficiency

## **Future Work**

- What other data should OpenET be coupled with so that farmers can accurately make self-governing management decisions?
- What other analyses would be useful?


## **Appendix**

![](https://www.agriculture.ks.gov/images/default-source/wms-images/sd6boundary.png?sfvrsn=68a6e98e_6)
![](/images/workflow.png)
