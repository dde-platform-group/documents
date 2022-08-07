# DDE Platform User Manual

# About

## What is DDE Platform?
DDE Platform (Fig. 1) is a one-stop online research platform, built for enabling and empowering global earth science collaborative innovation and discoveries, dedicated to the advancement of earth sciences research.

DDE Platform aims to:
+ Build an open global data network to assist data production, accessibility, analysis, visualization, sharing, and archiving;
+ Construct a global earth science knowledge graph based on expert knowledge and literature to gain insights into deep-time earth from wider perspectives;
+ Provide an online platform for interdisciplinary collaborative research;
+ Create an online workspace to support data-model computing-driven research; Contribute to the transformation of earth science research through the emerging practices of digital scholarship, data manipulation and use, knowledge and computation stewardship, and open science.

## Architecture

<figure>
  <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/About_platform-concept-diagram.png" alt="my alt text" align="center"/>
  <figcaption align="center">Figure 1. The conceptual diagram of DDE Platform.</figcaption>
</figure>

### Deep-time Engine
Deep-time Engine is the cornerstone of DDE Platform. It contains four sub-engine levels, which correspond to computing, data, knowledge, and research services, respectively. These services support cases in different geoscientific and earth science fields.

### Data Service
Earth science data are abundant, but not all data are accessible or utilized efficiently. Rather, the data are scattered around the world – for example, they may be in the archives of a geological institute or university,on the pages of a book or journal in the library, in a set of laboratory records, or on the hard drive of a personal computer. By connecting and aggregating these scattered and long-tailed data, it is possible to gain greater understanding of important scientific issues such as the evolution of the earth, its climate, materials, and even life.

DDE Platform promotes the construction of a global geological data network that conforms to the FAIR principle by establishing data discovery and connection supported by the FAIR concept and by expressing global earth science data through a unified DDE meta-standard. At the same time, it establishes a user-centered data sharing system, utilizing breakthroughs in new information technology and the explosive growth in data abundance. DDE Platform enables data to seamlessly flow and be shared among users, fulfilling the open science sharing of global earth science data.

The data nodes linked by the DDE hub can be retrieved, browsed, worked in, managed, and shared by users of the Platform according to the different security protocols applied to the data. The Platform also supports the collaboration of multiple users.

### Knowledge Service
DDE's governance of knowledge mainly consists of two products of big knowledge, namely a Geoscience Academic Knowledge Graph (GAKG) and a Geoscience Professional Knowledge Graph (GPKG). GAKG is a multimodal knowledge graph formed by extracting knowledge from global earth science literature and manually annotating it. GPKG is a platform for knowledge content editing by professional earth scientists around the world.

With top-down expert knowledge editing and bottom-up literature knowledge extraction, DDE Platform provides a one-stop earth science knowledge service for users with global shared and co-constructed earth science knowledge. This knowledge will better guide users to conduct scientific research, and also provide raw materials for knowledge-based scientific research (such as artificial intelligence).

### Computing Service
Computing resources are the basis of data-driven geological and earth sciences analysis. DDE provides global earth scientists with FAIR data principles and convenient and powerful online computing services through Deep-time Engine, which includes:

+ Globally accessible cloud infrastructure services through DDE Cloud;
+ Abundant earth science analysis tool and workflow services;
+ Large-scale, high-performance computing services.

Using these three attributes, earth science researchers can make full use DDE's computing resources, models, and workflows to complete their own scientific research via efficient online computing and analysis capabilities, obtaining the desired level of research and analysis.

### Scene-oriented Service
Based on Deep-time Engine's computing, data, and knowledge services, and flexible assembly capabilities, DDE Platform can quickly create a customized working platform for complex scientific research and analysis scenarios with service Application Programming Interface (API) and browser components. Several working platforms, such as the Paleogeography Platform and the Global Layer Platform, have already been created.

# Modules
## Resources

The Resources module helps the user locate abundant and continuously updated earth science data, knowledge, and analysis tools as part of our overall DDE open network. Users can search via keywords and standard geologic time and get more information about the resource via the "more" button. Especially, to reach the goal of Data FAIR, we set the minimum unit of data flow in the platform, namely **DataAtom**. More figuratively, it is a broad form of data presentation in the platform, in actual form it can be a layer service, a web service, or a table from database and so on. Moreover, we offer **DataSet** to organize and manage **DataAtom**, similar to the relationship between folders and files.

<figure>
  <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/Resources_fig0.png" alt="my alt text" align="center"/>
  <figcaption align="center">Figure 2. Search via keyword in DataHub (illustrated), Knowledge Hub and Computation Hub.</figcaption>
</figure>



<figure>
  <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/Resources_fig3.png" alt="my alt text" align="center"/>
  <figcaption align="center">Figure 3. Search via geologic time in DataHub. Select a specific geologic period or enter a time interval to filter specific data.
</figcaption>
</figure>

<table>
    <tr>
        <td><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/Resources_fig4a.png" alt="my alt text"/>Figure 4a. Detailed information about DataAtom. </center></td>
        <td><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/Resources_fig4b.png" alt="my alt text"/>Figure 4b. Detailed information about Model. </center></td>
    </tr>
    <tr><td colspan="2"><center>Figure 4 More Resources Information on DDE Platform.</center></td></tr>
</table>

To support services of these resources in DDE open network, DDE build a series of products, like **Geoscience DataStore** to show PURE data sites can be browsed and searched on Internet, **Geoscience Knowledge Graph Collaborative Editor** to offer the ability to build knowledge graph etc. These products are mainly in the secondary directory of the navigation bar, and more products and features will be added in the upcoming version.

<table>
    <tr>
        <td><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/Resources_fig5a.png" alt="my alt text"/>Figure 5a. Geoscience DataStore </center></td>
        <td><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/Resources_fig5b.png" alt="my alt text"/>Figure 5b. Geoscience Knowledge Graph Collaborative Editor </center></td>
    </tr>
    <tr><td colspan="2"><center>Figure 5. DDE Products for further support on resources.</center></td></tr>
</table>


## Earth Explorer
Earth Explorer provides a visual interface with the integration of deep geological age, three-dimensional digital earth, and two-dimensional map capability to help the user create exquisite, accurate and vivid visual results.

<figure>
  <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig1.png" alt="my alt text" align="center"/>
  <figcaption align="center">Figure 6. Earth Explorer.
</figcaption>
</figure>

### Select Data
The "add data" page can search the dataset and atom data. The search conditions include keywords, spatial range, geological time, and more.

<table>
    <tr>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig2a.png" alt="my alt text"/>Figure 7a. Geological time filter result. </center></td>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig2b.png" alt="my alt text"/>Figure 7b. Spatial range filter result. </center></td>
    </tr>
    <tr><td colspan="2"><center>Figure 7. Add data panel.</center></td></tr>
</table>

In addition to the basic retrieval function, a distinction is made between public and private data, and official and personal data, and a data interest function is provided to allow users to collect the desired data. When the mouse hovers over the icon, operation tips are shown, which can be clicked to switch to the corresponding content.

Click the data name to view the data details and click the plus sign to add the data to the Earth Explorer.

<figure>
  <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig3.png" alt="my alt text" align="center"/>
  <figcaption align="center">Figure 8. DataSet details.
</figcaption>
</figure>



### DataManage

Data is divided into "DataSet" and "DataAtom" in the Earth Explorer. After adding data, they will appear in the data management panel.

<figure>
  <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig4.png" alt="my alt text" align="center"/>
  <figcaption align="center">Figure 9. Data management panel.
</figcaption>
</figure>
In the dataset management panel, the right side is the corresponding data unit entry in the dataset. Click to add it as a layer. At the same time, it provides the spatiotemporal filtering function of dataset. On the left side, data sets can be removed and played in sequence.

<figure>
  <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig5.png" alt="my alt text" align="center"/>
  <figcaption align="center">Figure 10. DataSet in play mode.
</figcaption>
</figure>

In the layer management panel, the user can adjust the order of layers, display or hide layers, and view layer details. Click the button in the lower right corner to view the legend.

<figure>
  <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig6.png" alt="my alt text" align="center"/>
  <figcaption align="center">Figure 11. Earth Explorer loaded with multiple layers.
</figcaption>
</figure>

Earth Explorer provides rich rendering functions for different types of layers. The user can open the rendering panel in layer management to modify and save preferred rendering style.

Taking the layer of Raster type as an example, users can choose different color bars (even custom color bars) and accurate value range to render the layer into a beautiful style.

The user can freely explore the rendering function provided by Earth Explorer and save it to the cloud so that the customized style will be retained when opened next time.

<table>
    <tr>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig7a.png" alt="my alt text"/>Figure 12a. WMTS/pbf layer render as single value. </center></td>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig7b.png" alt="my alt text"/>Figure 12b. WMTS/pbf layer segmented rendering. </center></td>
    </tr>
    <tr>
        <td><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig7c.png" alt="my alt text"/>Figure 12c. Raster layer render as three bands. </center></td>
        <td><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig7d.png" alt="my alt text"/>Figure 12d. Raster layer render by custom color bar. </center></td>
    </tr>
    <tr><td colspan="2"><center>Figure 12. Layer render options.</center></td></tr>
</table>


### Tools
The Tools page provides several common tools including paleogeographic reconstruction, split screen and multi-screen linkage.

In the paleogeographic reconstruction application, after the user selects the vector layer, geological time, and rotation model, the geometry will be reconstructed into a new layer after back-end operation.

<table>
    <tr>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig8a.png" alt="my alt text"/>Figure 13a. Paleogeography Reconstruction.</center></td>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig8b.png" alt="my alt text"/>Figure 13b. Split screen.</center></td>
    </tr>
    <tr>
        <td colspan="2"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig8c.png" alt="my alt text"/>Figure 13c. Multi screen linkage. </center></td>
    </tr>
    <tr><td colspan="2"><center>Figure 13. Tools.</center></td></tr>
</table>


### Export
The map Export function can quickly export the map content of the current workspace into a picture, and provide customizable titles, compass, longitude and latitude network, legend, layout, and more.

<table>
    <tr>
        <td colspan="2"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig9a.png" alt="my alt text"/>Figure 14a. Dynamic professional legend. </center></td>
    </tr>
    <tr>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig9b.png" alt="my alt text"/>Figure 14b. Legend clipped from a picture.</center></td>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig9c.png" alt="my alt text"/>Figure 14c. Export map in 3D scene.</center></td>
    </tr>
    <tr><td colspan="2"><center>Figure 14. Map Export.</center></td></tr>
</table>


### Map Project

The user can save the current work content as a Map Project and set its sharing properties. All saved personal or public map projects can be browsed or loaded. Click the project name to open in a new tab. After changing, the user can update it again or save it as a personal map project. The default Earth Explorer configuration can be changed through the settings panel, including compass, LongLat indicator, anti-aliasing, terrain exaggeration, performance settings, and more.

<table>
    <tr>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig10a.png" alt="my alt text"/>Figure 15a. Map project saving.</center></td>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig10b.png" alt="my alt text"/>Figure 15b. Searching map projects.</center></td>
    </tr>
    <tr>
        <td colspan="2"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/EarthExplorer_fig10c.png" alt="my alt text"/>Figure 15c. Setting Earth Explorer. </center></td>
    </tr>
    <tr><td colspan="2"><center>Figure 15. Map Project.</center></td></tr>
</table>



## Analysis Flow

The Analysis Flow provides an interactive operation interface to create, edit and manage Workflow. Workflow takes the output of one tool as the input of another tool.

<figure>
  <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/AnalysisFlow_fig1.png" alt="my alt text" align="center"/>
  <figcaption align="center">Figure 16. Overview of Analysis Flow.
</figcaption>
</figure>


### Assemble Workflow

The user can view the description of the model by hovering over the model’s name on the left model panel and select the appropriate model by dragging it to the canvas (center of the page). To depict research ideas comprehensively, the user can add directed links between models to generate a graph.

<table>
    <tr>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/AnalysisFlow_fig2a.png" alt="my alt text"/>Figure 17a. Drag models from the model catelog tree. </center></td>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/AnalysisFlow_fig2b.png" alt="my alt text"/>Figure 17b. Add links between models. </center></td>
    </tr>
    <tr><td colspan="2"><center>Figure 17. Darg & link models.</center></td></tr>
</table>

The linked models can be saved as a workflow by clicking the "Save as" button at the upper-right of corner of the page and  the stored results can be viewed in the "Example" panel on the left side.

There are multiple ways to fill in the parameters, while Analysis Flow will store a set of default options to save your time. The user can type directly into the input box or select files and folders in the cloud file system browser.

<table>
    <tr>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/AnalysisFlow_fig3a.png" alt="my alt text"/>Figure 18a. Input directly. </center></td>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/AnalysisFlow_fig3b.png" alt="my alt text"/>Figure 18b. Select from browser. </center></td>
    </tr>
    <tr><td colspan="2"><center>Figure 18. Ways to type in parameters.</center></td></tr>
</table>


### Execute & Monitor Workflow

After executing the workflow using the "Run" button on the upper-right corner, the user can view the running status of workflow tasks in MyDDE (Instructions in the next section). Detailed information describing each model’s workflow performance can be viewed by clicking on a specific model.

<figure>
  <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/AnalysisFlow_fig4.png" alt="my alt text" align="center"/>
  <figcaption align="center">Figure 19. Logs for each model of running tasks.
</figcaption>
</figure>


## MyDDE

MyDDE is your online scientific research workspace, where you, the user, can explore multiple scientific research questions by customizing any combination of data, model, knowledge, and computing power provided by the DDE Platform.

### Dashboard
The dashboard elucidates how users interact with the resources provided by the DDE Platform by presenting statistical and graphical overviews.

<figure>
  <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Dashboard_fig1.png" alt="my alt text" align="center"/>
  <figcaption align="center">Figure 20. The Dashboard for MyDDE.
</figcaption>
</figure>

Users can view how they have contributed to the Platform in "Materials" and how computing jobs have performed in "Workflow Task". Users can view the amount of resources and resource balances currently used in the "Monitor" on the right.

### Materials

In the "Materials" module, users can view their own Interest and Contribute "Data", "Computation" and "Knowledge" materials.

#### Materials - Data

Materials-Data includes File, DataAtom, DataSet.

1. File

   In File, the Cloud File System in MyDDE, the user can browse, upload, and download files, with any actions that operate in a local computer.

   <table>
    <tr>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Materials-Data_fig1a.png" alt="my alt text"/>Figure 21a. Browse the File. </center></td>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Materials-Data_fig1b.png" alt="my alt text"/>Figure 21b. New a folder in File. </center></td>
    </tr>
    <tr>
        <td><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Materials-Data_fig1c.png" alt="my alt text"/>Figure 21c. Upload a file. </center></td>
        <td><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Materials-Data_fig1d.png" alt="my alt text"/>Figure 21d. View the progressbar for uploading. </center></td>
    </tr>
    <tr><td colspan="2"><center>Figure 21. Cloud File System in MyDDE.</center></td></tr>   
   </table>



2. DataAtom
   
   In this module, the user can see their Interest and Contribute DataAtoms. Clicking "Explore" will take you to Earth Explorer. Interest can be removed and Contribute can be deleted.

   <table>
       <tr>
           <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Materials-Data_fig2a.png" alt="my alt text"/>Figure 22a. DataAtom of interest. </center></td>
           <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Materials-Data_fig2b.png" alt="my alt text"/>Figure 22b. Contributed DataAtom and "Explore". </center></td>
       </tr>
       <tr><td colspan="2"><center>Figure 22. Overview for DataAtom in MyDDE.</center></td></tr>
   </table>

Of course, the user can publish a new DataAtom. There are three types of DataAtom that can be created: HTTP DataAtom, JDBC DataAtom and Layer Service DataAtom.

3. Dataset

   The DataSet is designed to be the set for DataAtom, where users can freely allocate a self-contributed or Platform-provided DataAtom in and out of a dataset.

	<figure>
    <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Materials-Data_fig3.png" alt="my alt text" align="center"/>
    <figcaption align="center">Figure 23. Link DataAtom into a dataset.
   </figcaption>
   </figure>
   
   

#### Materials - Computation
Materials-Computation module is designed for models and workflows. You can use a variety of earth science models and build your own workflows. Enter a keyword to search the model.

In the model tab, the user’s favorite models are listed. Click the model's name to learn more about the model. If the user has no interest in the model any longer, click “remove” and this model will be removed from the favorites list.

<table>
    <tr>
        <td width= "33%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Materials-Model_fig1a.png" alt="my alt text"/>Figure 24a. Models of interest. </center></td>
    </tr>
    <tr>
        <td width= "33%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Materials-Model_fig1b.png" alt="my alt text"/>Figure 24b. Detailed information of models. </center></td>
    </tr>
    <tr>
        <td width= "33%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Materials-Model_fig1c.png" alt="my alt text"/>Figure 24c. Use a single model. </center></td>
    </tr>
    <tr><td colspan="3"><center>Figure 24. Overview of Model in MyDDE.</center></td></tr>
</table>

The Workflow tab contains two parts: the Interest Workflow and the Contribute Workflow. "Interest" is the user’s favorite workflow, and "Contribute" is the created workflow.

<table>
    <tr>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Materials-Model_fig2a.png" alt="my alt text"/>Figure 25a. Workflows of interest. </center></td>
    </tr>
    <tr>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Materials-Model_fig2b.png" alt="my alt text"/>Figure 25b. Detailed information of workflows. </center></td>
    </tr>
    <tr><td colspan="3"><center>Figure 25. Overview of Workflow in MyDDE.</center></td></tr>
</table>

The user can also click "Use" to execute their interested workflow and will be directed to "Analysis Flow" interface.

#### Materials - Knowledge

Materials-Knowledge is divided into three systems: GPKG (Geoscience Professional Knowledge Graph), GAKG (Geoscience Academic Knowledge Graph) and GKGD (Geoscience Knowledge Graph open Directory). You can switch between these knowledge systems by clicking on their tabs and view the knowledge of interest in the list.

<figure>
 <img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Materials-Knowledge_fig1.png" alt="my alt text" align="center"/>
 <figcaption align="center">Figure 26. Knowledge in MyDDE.
</figcaption>
</figure>


### Analysis

MyDDE Analysis is a convenient option for computing the data provided by the DDE Platform. The Analysis module includes three sections: workflow task, code task and map. Workflow task will provide workflow in the low code forms. Combined with the data and model integrated by the Platform, it will provide users with a simple and easy to operate multi-functional geographic information processing method and has the ability of batch processing. Code task will provide a Jupyter hub deployment that includes a set of commonly used packages for geospatial and sustainability data analysis. Map can save all kinds of layers and data as a project, which is convenient for users to call quickly and continue their previous work.

Workflow task can save the Workflow generated by users, which is convenient for users to view, clone and delete. Users can view the Workflow created in the past and make changes or clone a new Workflow with the same content as the existing Workflow. In addition, users will also intuitively see the running state of each Workflow.


<figure>
 <center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Analysis_fig1.png" alt="my alt text"/></center>
 <figcaption align="center">Figure 27. Overview of Workflow Task.</figcaption>
</figure>

Code task contains all personal workspaces created by users. Users can create, enter, pause and delete code tasks. At the same time, users will also intuitively view the number of resources occupied by each code task and the percentage of resources used in the upper limit of resources.

During the creation process, the user needs to determine the name, CPU resource size, memory resource size and other parameters of the created code task. After creation, the user can click “enter” to enter the code task, write and run the code, and obtain the desired processing results. Jupyter Lab is the latest web-based interactive development environment for notebooks, code, and data. Its flexible interface allows users to configure and arrange workflows in data science, geoscientific computing, and machine learning. A modular design invites extensions to expand and enrich functionality. Now, it can be used in MyDDE Code Task.

<table>
    <tr>
        <td colspan="2"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Analysis_fig2a.png" alt="my alt text"/>Figure 28a. Overview of Code Task. </center></td>
    </tr>
    <tr>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Analysis_fig2b.png" alt="my alt text"/>Figure 28b. Creation of a new Code Task.</center></td>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Analysis_fig2c.png" alt="my alt text"/>Figure 28c. Export map in 3D scene.</center></td>
    </tr>
    <tr><td colspan="2"><center>Figure 28. Code Task in MyDDE.</center></td></tr>
</table>

The map module allows users to collect other people's map projects or manage their self-created ones for subsequent use. Users can also modify the permissions of map projects in "Privilege".

<table>
    <tr>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Analysis_fig3a.png" alt="my alt text"/>Figure 29a. DataAtom of interest. </center></td>
        <td width= "50%"><center><img src="https://deep-time-org.oss-cn-hongkong.aliyuncs.com/materials/usermanual_figures/MyDDE-Analysis_fig3b.png" alt="my alt text"/>Figure 29b. Contributed DataAtom. </center></td>
    </tr>
    <tr><td colspan="2"><center>Figure 29. Overview for DataAtom in MyDDE.</center></td></tr>
</table>
