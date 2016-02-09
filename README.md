#Purpose
This is a simple downloader for Sentinel-2 products from Amazon Web Services (AWS).
The reason of creating this downloader: AWS stores the elements of an S2 product (granules, metadata files) in a way
different from the official SAFE format. Therefore, if you want to use it with tools like Sentinel-2 Toolbox 
(homepage: https://sentinel.esa.int/web/sentinel/toolboxes/sentinel-2) , you have to download it in a suitable format.

#Features
1. Can perform filter on tiles (i.e. download only tiles of interest from a product to save space) either by supplying
a tile list on the command line, or by putting tiles in a dedicated file which is supplied as argument.
2. Can download products / tiles from an area of interest (given a closed linear ring - sequence of <lon lat> pairs,
supplied either as a list of comma-separated pairs of coordinates as argument, or in a file given as argument.
3. Can download products / tiles given a list of products.
4. Can download only products / tiles whose cloud coverage is below a given threshold.

#How to use it with Git and Maven:
1. Locally clone the repository
    git clone https://github.com/kraftek/awsdownload.git
2. Build and package the project:
    mvn clean package -DskipTests=true
3. The folder "lib" and the generated jar should be placed on the same folder. Then:
    java -jar AWSS2ProductDownload-0.1.jar
   for a list of supported command line arguments.

A simple example:
    java -jar AWSS2ProductDownload-0.1.jar --out D:\Products --tiles 34TFQ 35TNL --products S2A_OPER_PRD_MSIL1C_PDMC_20160103T183955_R064_V20160103T085753_20160103T085753