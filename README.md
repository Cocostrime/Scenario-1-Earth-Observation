# Scenario-1-Earth-Observation
This project is about AI based audit of Delhi airshed

**Q1. Earth Observation**
- In this task, the Delhi–NCR region is being analysed using Earth Observation data.
- The boundary of Delhi–NCR was provided in GeoJSON format with EPSG:4326.(🔗 https://www.kaggle.com/datasets/rishabhsnip/earth-observation-delhi-airshed?select=delhi_ncr_region.geojson)
- First, the Delhi–NCR region was plotted using matplotlib.
- After that, a uniform grid of size 60 × 60 km was created over the region.
- The grid was then overlaid on a satellite basemap using leafmap to visually verify alignment with the region.
- Image locations were filtered by checking whether the center coordinate of the image lies inside any grid cell.

**Q2. Label Construction and Dataset Preparation**
- For each valid image location, a 128 × 128 pixel patch was extracted from the ESA land cover GeoTIFF.
- The extraction was done by centering the window at the image coordinate.
- Each patch was assigned a land-use label using the most frequent (mode) land cover class present in the patch.
- ESA land cover class codes were mapped to 11 standard land-use categories.
- The dataset was randomly split into 80% training data and 20% testing data.

**Q3. Model Training and Supervised Evaluation**
-A CNN was trained using TensorFlow and Keras. 
- The model was trained using the Adam optimizer.
