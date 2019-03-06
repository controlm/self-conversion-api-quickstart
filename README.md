# Control-M Self Conversion API quick start
This repository contains "Conversion Rules" code samples that use groovy and [**Control-M Self Conversion API**](https://docs.bmc.com/docs/ctmselfconv/control-m-self-conversion-api-814570051.html) to convert sample demo input data into Control-M Data. You can also view these conversion rules code samples from the Control-M Self Conversion homepage in the “sample_project”.
You can use these conversion rules code samples to learn different script rules structures and learn how you can use the [**Control-M Self Conversion API**](https://docs.bmc.com/docs/ctmselfconv/control-m-self-conversion-api-814570051.html) to create Control-M data, such as Folders, Jobs, Hierarchy, Conditions, and different job types (like OS Command jobs SAP R3, File transfer, Informatica and more).

# Online Documentation
For more information, see [**Control-M Self Conversion**](https://docs.bmc.com/docs/ctmselfconv/control-m-self-conversion-817142681.html) and the [**Control-M Self Conversion API**](https://docs.bmc.com/docs/ctmselfconv/control-m-self-conversion-api-814570051.html) online documentation.
To download the latest Control-M  Self Conversion, click: [**Download Control-M self-conversion**](ftp://ftp.bmc.com/pub/control-m/opensystem/Control-M_Conversions_for_DS/).
# Demo Tool Conversion example
### The Demo Tool Conversion example includes:

* __SampleData__ - A folder that holds demo tool sample Input Data in XML format that we want to convert to Control-M data.
* __MappingLogic.xlsx__ - The mapping logic used for conversion in this sample, from the demo tool sample input data to Control-M data.
* __ConversionRules.json__ - The Demo Tool Conversion Rules json file that contains the Self Converion rules code.
* __ControlM_Result.xml__ - The Control-M data created by the Self Converion when converting the Demo tool sample data using the Demo Tool conversion rules.

### XML structure sample:

```xml 
<BOX>
  <JOB Name="JOB1">Job Text</JOB>
</BOX> 
```
 __Above sample contains:__
* BOX Element that has child JOB Element. 
* JOB Element contains an "Name" attribute with value "JOB1"
* JOB Element text value is "Job Text"


### Demo Tool mapping logic  
Demo Tool Data | Control-M Data
-|-
__BOX__ Element|Smart Folder
BOX __"Box_Name"__ Attribute value|Smart Folder name
__JOB__ Element|Job
JOB __"Name"__ Attribute value|Job Name
JOB Element with Attribute __"TYPE=OS"__|OS Job
JOB __"Command"__ Attribute value|OS Job - Command
JOB __"UserName"__ Attribute value|OS Job - Run As
JOB Element with Attribute __"TYPE=SAP"__|SAP R3 Job
JOB > saptask > __jobname__ Element text|SAP R3 Job - SAP Job Name
JOB __"UserName"__ Attribute value|SAP R3 Job - Connection Profile
JOB > saptask > step > __abap__|SAP R3 Job - ABAP Step
JOB Element with Attribute __"TYPE=SAPBW"__|SAP BW Job
JOB __"UserName"__ Attribute value|SAP BW Job - Connection Profile
JOB > saptask > __ProcessChain__|SAP BW Job - Process Chain
JOB Element with Attribute __"TYPE=MFT"__|File Transfer Job
JOB __"UserName"__ Attribute value|File Transfer Job - Connection Profile
JOB > __transfer__|File Transfer Job - Transfer Attributes
__Hierarchy__: BOX > JOB|Smart Folder parent of Job


### Usage Instructions
1. Clone or download the repository.
2. Open Control-M Self Conversion.
3. Import the __Demo Tool Conversion Rules__ json file.
4. Create a new Self Conversion project: 
   * Enter a project name.
   * Load the **Demo Tool Sample Input Data**.
   * In "Use existing conversion rules" dropdown list, select the conversion rules imported in step 3.
   * Click "Create Project".
5. Click Run.
6. Review the conversion results.

## Contribution guide
To contribute, please follow these guidelines.

### Files, folders and naming conventions
1. Every conversion and its associated files must be contained in its own **folder**. Name this folder as the name of the tool that you convert from.
2. The __folder__ should contain:
   * __SampleData__ - A folder that holds tool sample Input Data in XML format that we want to convert to Control-M data.
   * __MappingLogic.xlsx__ - The mapping logic used for conversion in this sample, from the  tool sample input data to Control-M data.
   * __ConversionRules.json__ - The tool Conversion Rules json file that contains the Self Converion rules code.
   * __ControlM_Result.xml__ - The Control-M data created by the Self Converion when converting the tool sample data using the Demo Tool conversion rules.

3. Include a **README.md** file that explains the sample. A good description helps other community members to understand your sample. The README.md uses [Github Flavored Markdown](https://guides.github.com/features/mastering-markdown/) for formatting text.

