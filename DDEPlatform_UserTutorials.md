# Tutorials

DDE provides a fair, convenient and powerful online geoscientific big data computing service for geoscientists worldwide, solving the problems faced by geoscientists at three levels, enabling users to compute, compute well and compute at scale.

- Provide globally accessible cloud infrastructure services through DDE Cloud, allowing geoscientists to enjoy equal and open shared computing resources no matter where they are.
- Provide rich geoscientific analysis tools and models, including statistical analysis, data mining, and specialized disciplines, so that geoscientific researchers can use a combination of models and tools to complete research that requires the cooperation of multiple software.
- Provide large-scale, high-performance geoscientific computing services that can directly handle terabytes of data volume, billions of data entries, and thousands of tasks executed concurrently, raising the upper limit of computational tasks for geoscientific researchers while shortening research time costs.
Through the above three levels of services, geoscience researchers can use DDE's computing resources and modeling tools to complete their scientific research and get the research and analysis results they want through efficient online computing and analysis capabilities.

# Geothermal Favorability Analysis

## Introduction

The heatflow case takes in customized factors to generate a Geothermal favorability map for region of interest.

## Functionality

- OSS cloud storage
- Analysis Flow:
  - Cloud-native container orchestration
  - Cloud-native computing resource scheduling
- Earth Explorer:
  - Cloud-native 4D Earth rendering

## Example Data

The platform integrates multi-source heterogeneous datasets of Geothermology, which serves the users as an arena to play around and try out ideas. The data that can be used in this case are listed below:
(Base directory: /exampleData/heatflow/)

- Spring distribution and temperature: spring/Tibet_spring.shp
- Bouguer gravity: bouguerG/Bouguer_gravity_Tibet_4326.shp
- Geothermal Heatflow: GeothermalHeatflow/heatflow_Tibet.shp
- Fault distribution: fault/fault_Tibet.shp
- Region of Tibet : region/Tibet_boundary.shp

## Demonstration

1. Login
2. Browse the computation hub in the navigation bar
   1. Explore the model hub.
   ![image.png](https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/1.png)

   1. Choose the model of interst, click "More>" and "Interest".
   <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/2.png" alt="image.png" style="zoom:150%;" />

3. Enter the computation interface
   1. Click the MyDDE (upper-right corner of the front page)
   ![image.png](https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/3.png)

   2. Click the Analysis in the sidebar.
   ![image.png](https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/4.png)

   3. Click the "New Task" button.
   ![image.png](https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/5.png)

4. Assemble a workflow
   1. Drag the model in the sidebar to the center canvas.
      1. Construct the "IDW - Mask - Reclassify" group.
      1. Construct the "Euclidean Distance - Mask - Reclassify" group.
      1. Copy and Paste the linked groups of "IDW - Mask - Reclassify" and "Euclidean Distance - Mask - Reclassify" twice and once more respectively.
      <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/6.png" alt="image.png" style="zoom:150%;" />
      1. Link all these five groups to the "Weighted Sum" model.
   1. Save the workflow by clicking the "Save as" button on the upper-right corner of the canvas.

1. Fill in the parameters of the workflow in each model.
   1. Fill the first group "IDW - Mask - Reclassify" (the "Geothermal Heatflow" group)
      1. Click the "Inverse Distance Weighting Interpolation" to fill parameters, examples are shown in the table below:
      
      | Parameter Name   | Parameter Value                                                      |
      | ---------------- | -------------------------------------------------------------------- |
      | path_data_points | DDE://exampleData/heatflow/GeothermalHeatflow/heatflow_Tibet.shp     |
      | x_field_id       | 0                                                                    |
      | y_field_id       | 1                                                                    |
      | z_value_id       | 3                                                                    |
      | radius           |                                                                      |
      | max_neighbors    | 12                                                                   |
      | x_cell_size      | 0.1                                                                  |
      | y_cell_size      | 0.1                                                                  |
      | extent           | 78,99.5,26.5,37                                                      |
      | path_result      | DDE://exampleData/heatflow/GeothermalHeatflow/heatflow_Tibet_idw.tif |

      <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/7.png" alt="image.png" style="zoom:150%;" />

      2. Click the "Extract by Mask" to fill the parameters, examples are shown in the table below:

      | Parameter Name | Parameter Value                                                           |
      | -------------- | ------------------------------------------------------------------------- |
      | raster_data    | DDE://exampleData/heatflow/GeothermalHeatflow/heatflow_Tibet_idw.tif      |
      | mask_data      | DDE://exampleData/heatflow/region/Tibet_boundary.shp                      |
      | output         | DDE://exampleData/heatflow/GeothermalHeatflow/heatflow_Tibet_idw_mask.tif |

      <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/8.png" alt="image.png" style="zoom:150%;" />

      3. Click the "Reclassify" to fill the parameters, examples are shown in the table below:

      | Parameter Name | Parameter Value                                                           |
      | -------------- | ------------------------------------------------------------------------- |
      | input          | DDE://exampleData/heatflow/GeothermalHeatflow/heatflow_Tibet_idw_mask.tif |
      | num_class      | 10                                                                        |
      | reverse        | false                                                                     |
      | output         | DDE://exampleData/heatflow/GeothermalHeatflow/heatflow_Tibet_idw_rec.tif  |

      <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/9.png" alt="image.png" style="zoom:150%;" />

   1. Fill the second group "Euclidean Distance - Mask - Reclassify" (the "spring" group)
      1. Click the "Euclidean Distance" to fill parameters, examples are shown in the table below:
      | Parameter Name | Parameter Value                                        |
      | -------------- | ------------------------------------------------------ |
      | input          | DDE://exampleData/heatflow/spring/Tibet_spring.shp     |
      | cellsize       | 0.1                                                    |
      | extent         | 78,99.5,26.5,37                                        |
      | output         | DDE://exampleData/heatflow/spring/Tibet_spring_euc.tif |

      <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/10.png" alt="image.png" style="zoom:150%;" />

      2. Click the "Extract by Mask" to fill the parameters, examples are shown in the table below:

      | Parameter Name | Parameter Value                                             |
      | -------------- | ----------------------------------------------------------- |
      | raster_data    | DDE://exampleData/heatflow/spring/Tibet_spring_euc.tif      |
      | mask_data      | DDE://exampleData/heatflow/region/Tibet_boundary.shp        |
      | output         | DDE://exampleData/heatflow/spring/Tibet_spring_euc_mask.tif |

      <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/11.png" alt="image.png" style="zoom:150%;" />

      3. Click the "Reclassify" to fill the parameters, examples are shown in the table below:

      | Parameter Name | Parameter Value                                             |
      | -------------- | ----------------------------------------------------------- |
      | input          | DDE://exampleData/heatflow/spring/Tibet_spring_euc_mask.tif |
      | num_class      | 10                                                          |
      | reverse        | false                                                       |
      | output         | DDE://exampleData/heatflow/spring/Tibet_spring_euc_rec.tif  |

      <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/12.png" alt="image.png" style="zoom:150%;" />

   1. Fill the third and fourth group "IDW - Mask - Reclassify" (the "Bouguer Gravity" and "spring temperature" group) referencing the "Geothermal Heatflow" group
      1. different parameters should be noted (the "Bouguer Gravity" group)

      | Parameter Name | Parameter Value |
      | -------------- | --------------- |
      | x_field_id     | 0               |
      | y_field_id     | 1               |
      | z_value_id     | 1               |

      2. different parameters should be noted (the "spring temperature" group)

      | Parameter Name | Parameter Value |
      | -------------- | --------------- |
      | x_field_id     | 0               |
      | y_field_id     | 1               |
      | z_value_id     | 3               |

   4. Fill the fifth group "Euclidean Distance - Mask - Reclassify" (the "fault" group) referencing the "spring" group
   4. Fill the final "Weighted Sum" model, examples are shown in the table below:

   | Parameter Name | Parameter Value|
   | -------------- | --------------------- |
   | input          | DDE://exampleData/heatflow/spring/Tibet_spring_euc_rec.tif;DDE://exampleData/heatflow/fault/fault_Tibet_euc_rec.tif;DDE://exampleData/heatflow/spring/Tibet_spring_idw_rec.tif;DDE://exampleData/heatflow/GeothermalHeatflow/heatflow_Tibet_idw_rec.tif;DDE://exampleData/heatflow/bouguerG/Bouguer_gravity_Tibet_4326_idw_rec.tif |
   | weights        | 0.1;0.1;0.4;0.25;0.15|
   | output         | DDE://exampleData/heatflow/Favorability_map_Tibet.tif|

   <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/13.png" alt="image.png" style="zoom:150%;" />

1. Execute the workflow.
   1. Click the "Run" button on the upper-right corner of the canvas
   2. Input the job name in the Pop-ups.

<img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/14.png" alt="image.png" style="zoom:150%;" />

7. View the running status of the workflow
   1. back to the MyDDE - Dashboard panel.

![image.png](https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/15.png)

8. View the logs of each model from the workflow
   1. Click on the Analysis panel and "Detail" button

![image.png](https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/16.png)

![image.png](https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/17.png)

<img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/18.png" alt="image.png" style="zoom:150%;" />

9. Visualize the results of the workflow
   1. Publish the GeoTiff file as the DataAtom
     ![image.png](https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/19.png)

   2. Explore on Earth
     <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/20.png" alt="image.png" style="zoom:150%;" />
   
     <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/21.png" alt="4b21c9ab9f84d2384f8f6d403fec301.png" style="zoom:150%;" />

# Detrital Zircon Analysis

## Introduction

The detrital zircon case use statistic method to generate Age Histogram of detrital zircon data and use Multi-dimension Scaling method to project samples to 2-D scatters for further analysis.

## Functionality

- OSS cloud storage
- Analysis Flow:
  - Cloud-native container orchestration
  - Cloud-native computing resource scheduling

## Example Data

(Base directory: /exampleData/Detrital_Zircon/)
Detrital Zircon Data From OneSediment: /tibetan_detrital_zircon.csv

## Demonstration

1. Login
1. Browse the computation hub in the navigation bar
   1. Explore the model hub.
   1. Choose the model of interst, click "More>" and "Interest".
3. Enter the computation interface
   1. Click the MyDDE (upper-right corner of the front page)
   1. Click the Analysis in the sidebar.
   1. Click the "New Task" button.

The fisrt 3 steps are the same as the case above.

4. Assemble a workflow
   1. Use example workflow directly

![image.png](https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/22.png)

   2. Drag the model in the sidebar to the center canvas.
      1. Age Histogram Plot
         1. The first model is "Connect and Query from Database" which is used for connect and query form detrital zircon database provided by DDE OneSediment.Click the "Connect and Query from Database" to fill parameters, examples are shown in the table below:

         | Parameter Name | Parameter Value                                                    |
         | -------------- | ------------------------------------------------------------------ |
         | query_col      | major_geographic_geologic_description     |
         | input_geo      | tibetan plateau,north china craton |
         | user_sql       | null     |
         | depo_age_range | 0,4000 |

         > hint: If you have your own data, the first model is no more needed.

         2. The second model is "Format Standardlization" which is used for standardlize data format.Click the "Format Standardlization" to fill parameters, examples are shown in the table below:

         | Parameter Name | Parameter Value                                                    |
         | -------------- | ------------------------------------------------------------------ |
         | input          | DDE://exampleData/Detrital_Zircon /tibetan_detrital_zircon.csv     |
         | output         | DDE://exampleData/Detrital_Zircon /tibetan_detrital_zircon_std.csv |

         > hint: If you have standardlized data, the second model is no more needed.

         3. The third one is "Time Series Proba Plot" which is used for statistical particle number formation probability histogram chart. Click the "Time Series Proba Plot" to fill parameters, examples are shown in the table below:

         | Parameter Name | Parameter Value                                                                          |
         | -------------- | ---------------------------------------------------------------------------------------- |
         | input          | DDE://exampleData/Detrital_Zircon/tibetan_detrital_zircon_std.csv                        |
         | agg_field      | major_geographic_geologic_description                                                    |
         | time_range     | 0,3500                                                                                   |
         | if_subplot     | yes                                                                                      |
         | plot_type      | KDE                                                                                      |
         | if_CI          | no                                                                                       |
         | if_hist        | yes,20                                                                                   |
         | in_agebins     | [[0,150],[200,500],[500,700],[750,1050],[1050,1300],[1350,1750],[1750,2150],[2200,2700]] |
         | in_agebinsc    | gold,royalblue,gold,royalblue,gold,royalblue,gold,       royalblue                              |
         | plot_size      | 10,4,5                                                                                   |
         | output         | DDE://exampleData/Detrital_Zircon/ts_plot.pdf                                            |

      2. MDS Analysis
         1. The first 2 model is "Connect and Query from Database" and "Format Standardlization", while the parameters example is the same as above.
         2. The third one is "Multi-dimension Scaling" which is used for project samples to 2-D scatters for further analysis, like classification, source analysis and so on. Click the "Multi-dimension Scaling" to fill parameters, examples are shown in the table below:

         | Parameter Name | Parameter Value                                                    |
         | -------------- | ------------------------------------------------------------------ |
         | input          | DDE://exampleData/Detrital_Zircon /tibetan_detrital_zircon_std.csv |
         | time_range     | [200,500]                                                          |
         | DimRed_method  | MDS                                                                |
         | colorby        | Major_Geographic_Geologic_Description                              |
         | output         | DDE://exampleData/Detrital_Zircon/MDS_plot.pdf                     |

   3. Execute the workflow.
      1. Click the "Run" button on the upper-right corner of the canvas
      2. Input the job name in the Pop-ups.

      ![image.png](https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/23.png)

      1. View the running status of the workflow, the same as the case above.
      2. Visualize the results of the workflow. The result is located in your customized filepath（e.g. "DDE://exampleData/Detrital_Zircon/ts_plot.pdf）" here.

      <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/tutorials/24.png" alt="image.png" style="zoom:150%;" />
