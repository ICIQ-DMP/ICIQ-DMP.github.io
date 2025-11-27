---
layout: default
title:  Dataset Files
permalink: /CORA.RDR/User-Guide/dataset-files
nav_order: 70
parent: User Guide
grand_parent: CORA.RDR
---

# File structure in CORA.RDR / Dataverse

The main goal of CORA.RDR is to store and preserve digital data.

Digital data related  is stored in **Datasets**. You can understand each dataset in CORA.RDR as a computer folder that 
can contain files or other folders, just as any 
folder of your
computer. 

Digital data are stored in software-specific file formats. The choice of software and format depends on the intended 
use. For example:

* Spreadsheets support formulas, sorting, and filtering — features not preserved in word processors.
* Word processors support complex formatting such as page numbers and tables of contents.

However, saving a file in a program’s default format does **not** guarantee long-term usability. Risks include:

* Dependency on specific software or software versions
* Obsolescence of proprietary formats
* Exclusive or expensive software required to access files
* Loss of significant characteristics if the format does not support them

To minimize these risks and improve long-term accessibility, use file formats with a high likelihood of remaining usable for many years.

Here are some guidelines on which formats are accepted and the recommended folder structure for a dataset.
We encourage that you enforce these guidelines on the datasets that you upload to CORA.RDR, but it is not a 
technical limitation, which means that in some case the guidelines can be bypassed with a justified reason. 

For example, we do recommend using CSV for tabular data, but usually users use Excel files to store their tabular data.
It may be possible that when transforming this Excel file into a CSV file,  
the original Excel loses an important part of format of the Excel, affecting to the quality of the data. In this case 
and others it may be reasonable to bypass the guidelines on the recommended file formats.


## Preferred and Non-Preferred File Formats (DANS)

Preferred formats are file formats that DANS – based on international agreements – is confident offer the best long-term 
guarantees in terms of usability, accessibility, and sustainability. Deposits of research data in preferred formats 
will **always** be accepted by DANS.

Non-preferred formats are widely used in addition to preferred formats and are expected to remain moderately to 
reasonably usable, accessible, and robust in the long term.


## General Guidelines

DANS believes that file formats best suited for long-term sustainability and accessibility:

* Are frequently used
* Have open specifications
* Are independent of specific software, developers, or vendors

In practice, it is not always possible to use formats that satisfy all criteria.

It may be desirable to deposit certain original data in **non-preferred** formats because these are common usage formats
(e.g., Esri Shapefiles, Microsoft Access databases, SPSS `.sav` files).
In those cases, DANS requests you to deposit:

* The original format **and**
* A preferred format for long-term sustainability.


### File Format Overview

This information is based upon [this article](https://dans.knaw.nl/en/file-formats/) and has suffered some 
modifications. 

#### Text Documents

| Type                      | Preferred Formats                                                                               | Non-Preferred Formats       |
|---------------------------|-------------------------------------------------------------------------------------------------|-----------------------------|
| **Text documents**        | PDF/A (.pdf), ODT (.odt), Microsoft Word (.doc), Office Open XML (.docx), Rich Text File (.rtf) | PDF other than PDF/A (.pdf) |
| **Plain text**            | Unicode text (.txt)                                                                             | Non-Unicode text (.txt)     |
| **Markup languages**      | XML (.xml), HTML (.html) + related (.css, .xslt, .js, .es), Markdown (.md)                      | —                           |
| **Programming languages** | MATLAB, NetCDF, Text-Fabric, Python                                                             | —                           |

#### Spreadsheets

| Preferred              | Non-Preferred                                                 |
|------------------------|---------------------------------------------------------------|
| ODS (.ods), CSV (.csv) | Microsoft Excel (.xls), Office Open XML (.xlsx), PDF/A (.pdf) |

#### Databases

| Preferred                              | Non-Preferred                                                          |
|----------------------------------------|------------------------------------------------------------------------|
| SQL (.sql), SIARD (.siard), CSV (.csv) | Microsoft Access (.mdb, .accdb), dBase (.dbf), HDF5 (.hdf5, .he5, .h5) |

#### Statistical Data

| Preferred                                                | Non-Preferred                                                                          |
|----------------------------------------------------------|----------------------------------------------------------------------------------------|
| SPSS (.dat/.sps), STATA (.dat/.do), JASP (.csv/.html), R | SPSS Portable (.por), SPSS (.sav), STATA (.dta), SAS (.7dat, .sd2, .tpt), JASP (.jasp) |

#### Raster Images

| Preferred                                                                          | Non-Preferred |
|------------------------------------------------------------------------------------|---------------|
| JPEG (.jpg, .jpeg), TIFF (.tif, .tiff), PNG (.png), JPEG 2000 (.jp2), DICOM (.dcm) | —             |

#### Vector Images

| Preferred  | Non-Preferred                                                         |
|------------|-----------------------------------------------------------------------|
| SVG (.svg) | Adobe Illustrator (.ai), EPS (.eps), WMF/EMF (.wmf, .emf), CDR (.cdr) |

#### Audio

| Preferred                                                                | Non-Preferred                                                |
|--------------------------------------------------------------------------|--------------------------------------------------------------|
| BWF (.bwf), MXF (.mxf), Matroska (.mka), FLAC (.flac), OPUS, WAVE (.wav) | MP3 (.mp3), AAC (.aac, .m4a), AIFF (.aif, .aiff), OGG (.ogg) |

#### Video

| Preferred                                                                                       | Non-Preferred                     |
|-------------------------------------------------------------------------------------------------|-----------------------------------|
| MXF (.mxf), Matroska (.mkv), MPEG-4 (.mp4, .m4a, .m4v, …), MPEG-2 (.mpg, .mpeg, .m2v, .mpg2, …) | AVI (.avi), QuickTime (.mov, .qt) |

#### CAD (Computer-Aided Design)

| Preferred                                  | Non-Preferred                                        |
|--------------------------------------------|------------------------------------------------------|
| AutoCAD DXF R12 (ASCII) (.dxf), SVG (.svg) | AutoCAD DXF (other versions), DWG (.dwg), DGN (.dgn) |

#### GIS (Geographical Information Systems)

| Preferred                                                            | Non-Preferred                                                                                                                           |
|----------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------|
| GML (.gml), MIF/MID (.mif/.mid), GeoJSON (.json), GeoPackage (.gpgk) | Esri Shapefiles (.shp + related), MapInfo (.tab + related), KML (.kml, .kmz), Esri Geodatabase (.gdb), Project files (.mxd, .wor, .qgs) |

#### Georeferenced Images

| Preferred                                                                           | Non-Preferred        |
|-------------------------------------------------------------------------------------|----------------------|
| GeoTIFF (.tif, .tiff), TIFF World File (.tfw + .tif), JPEG World File (.jgw + .jpg) | ERDAS IMAGINE (.img) |

#### Raster GIS

| Preferred               | Non-Preferred                                                    |
|-------------------------|------------------------------------------------------------------|
| ASCII GRID (.asc, .txt) | Esri GRID (.grd), Surfer Grid (.grd, .srf), ERDAS IMAGINE (.img) |

#### 3D

| Preferred                                                                                                | Non-Preferred                                                                                                                                                           |
|----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| OBJ (.obj), PLY (.ply), X3D (.x3d), glTF 2.0 (.gltf, .glb), COLLADA (.dae), LAS (.las, .laz), IFC (.ifc) | Autodesk FBX (.fbx), Blender (.blend), glTF 1.0, 3D PDF (.pdf), Google Draco (.drc), Artec (.a3d), Agisoft Metashape (.psx, .psz), STL (.stl), VRML (.wrl, .wrz, .vrml) |

#### RDF

| Preferred                                                     | Non-Preferred |
|---------------------------------------------------------------|---------------|
| RDF/XML, Trig (.trig), Turtle (.ttl), NTriples (.nt), JSON-LD | —             |

#### CAQDAS (Qualitative Data)

| Preferred | Non-Preferred                            |
|-----------|------------------------------------------|
| REFI-QDA  | ATLAS.TI copy bundle, NVivo project file |

