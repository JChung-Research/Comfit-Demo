# Web-based Microservice for monitoring indoor air quality based on BIM & IoT

Visit the Live Demo: [https://jchung-research.github.io/Comfit-Demo/](https://jchung-research.github.io/Comfit-Demo/)

## Project Background
- In smart home IoT sensors, one of the difficulties for users is to connect the sensor data with building information and analyze the real-time data. This project aims to develop a web-based building system platform for non-experts to easily monitor indoor thermal comfort and air quality using BIM & IoT sensors

## Concept Diagram
- In this project, the workflow consists of BIM software, web platform, IoT sensor modules, and database
- In summary, BIM model can be imported from BIM software to the web platform with IFC.JSON file format. Sensor modules can be connected with the web via MQTT protocol, and sensor data is collected from the sensor. The aggregated sensor data can be stored in a database using Google API. 
- In the previous project, NodeRED is used as a server that processes and transfers the sensor data to the web platform; however, in this project, the sensor data is directly forward to the web without the additional server. It improves computational efficiency.   
<p align="center">
  <img src="/assets/Workflow.jpg" alt="Workflow of the Project" style="width:80%;"/>
</p>

## Data Exchange between BIM software and web platform
- If the users generate building elements using Rhino Grasshopper plugin or Revit software, the data including geometries, positioning, object types, and sensor ID can be exported into IFC.JSON or IFC format file.
- The exported file can be imported by a web platform, and the IFC file can be automatically converted into IFC.JSON format. The imported data can be visualized on the platform using THREE.js and the user can simply manipulate the objects using dat.gui controls. Also, the objects can be viewed or colored by object type.
<p align="center">
  <img src="/assets/Data_exchange.jpg" alt="Data Exchange" style="width:80%;"/>
</p>
  
## Data Exchange between Sensor, Web, and Database
- IoT sensors and the web-based system can be connected through MQTT protocol using MQTT.js library. If the user writes the pre-specified MQTT topic on the platform, the sensor data will be shown on the web.
- Using Google sheet API, the collected data with time series can be automatically stored in the Google sheet, and the historical data can be visualized as line charts. The users need to provide API Key, and Client ID in advance.
<p align="center">
  <img src="/assets/Data_exchange2.jpg" alt="Data Exchange" style="width:80%;"/>
</p>
  
## User Interface of Web Platform
- The user interface is comprised of six sections: 3D View, Status, Controls, Object Types, Data Table, and Data Displaying.
- '3D View' section displays the imported 3D geometries.
- 'Status' section shows status of MQTT connection, the length of the aggregated sensor data, and real-time data from the sensor modules.
- 'Controls' section provides controllers to visualize sensor data or import/export the data from/to a database.
- 'Object Types' section enables to show on/of objects or change opacity/color of the objects by object type.
- 'Data Table' section shows building information of the object that the user selects
- 'Data Displaying' section displays all the objects and their properties that user selects
<p align="center">
  <img src="/assets/UI.jpg" alt="UI" style="width:80%;"/>
</p>

## Demo Video
- The Demo video of the web platform is available at [this link](https://www.youtube.com/watch?v=gqgwoeNuSBU).
<p align="center">
  <a href="https://www.youtube.com/watch?v=gqgwoeNuSBU" target="_blank"><img src="https://img.youtube.com/vi/gqgwoeNuSBU/0.jpg" alt="Demo Video" style="width:60%;"/></a>
</p>

## Requirements
- ifcopenshell
- IFCJSON converter
- MQTT.js
- THREE.js
- Datatable.js
- Bootstrap


  
## References
- https://github.com/IFCJSON-Team/IFC2JSON_python/tree/master/file_converters
- https://github.com/IfcOpenBot/IfcOpenShell
- https://github.com/mqttjs/MQTT.js
- https://developers.google.com/sheets/api/guides/concepts
