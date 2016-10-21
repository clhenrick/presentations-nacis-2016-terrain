# Practical and Impractical Uses of Terrain Data
Stamen Design  
Chris Henrick  
NACIS 2016

## NOTES:

### About Me:

- Design Technologist at Stamen Design:

- part web developer, part Cartographer, part data wrangler, part UXer

- Started out as a cartographer & GIS specialist

- first NACIS was 2009 in Sacramento, CA & I got my start after that

- Much of this work is the result of hard work by Seth Fitzsimmons & Alan McConchie, I helped out towards the end


### About Stamen:

- Design & Technology study in San Francisco, CA

- Started in 2001 by Eric Rodenbeck following the wake of the dot com crash

- Specialize in creating highly customized data-visulizations and interactive maps

- Work with clients ranging from Toyota, UC Berkeley, NPS, & the Dali Lama


### Open Terrain

- main source of this work is from the Open Terrain project

  - started before my time at Stamen,

  - piggy backing on previous work done for Knight

  - Dot Spotting, Toner, Watercolor

- supported by a Knight News grant

- goals: catalog open terrain data, via researching & crowd sourcing

- create & document workflows using open source software for processing terrain data


#### Outcomes:

- Wiki on Github

- Terrain Classic map tiles (will talk more about that next)

- AWS Tiler (serverless map tile generation)


#### Variants:

- Humaniterrain:

  - Terrain layer to the Humanitarian OSM Map Tiles,

  - right after the 7.8 magnitude earthquake that struck Nepal

  - helped give context to the map styles, printed and used by aid workers in the field

- Toner

- Watercolor

- Darkmatter

- Positron

- Terrain Classic



### Terrain Classic

- global version of Stamen’s Terrain map tiles

- partly a style port to CartoCSS, was previously built using Cascadenik

- other tech includes: Node JS, Postgres w/ PostGIS, Mapnik, Make, Tessera

- used with AWS Lambda Tiler for background, lines, labels, & hillshades

- variants sandwiched together for main tile labels

- Terrain data sourced from Mapzen’s Elevation Data API


#### Outcomes:

- although it has terrain, it’s also a more general purpose map style then Toner, journalists in mind

- free, public tile source in the after math of Mapquest shutting down its tile service

- no API key required

- Tom Patterson's Web Shaded Relief


#### Samples:

- Kilamanjaro

- Denali

- Mt Shashta

- Grand Canyon

- Himalayas

- Alps


### AWS Tiler

- Technique created by Seth

- AWS services: Lambda, S3, EC2, API Gateway

- various ways to wrangle cloud computing

- GDAL: Raster Overviews & Warped VRTs

- use Python with rasterio & matplotlib for Tile Generation

- Docker & Apex.io

- Source data: raster or Postgres


#### Outcomes:

- very cost efficient when compared to using a map tile provider

  - pay for what you use,

  - scales down as well as up

  - only pay for what you use

- allows for maintaining ownership of your tiles

- no tile server so no server upkeep and maintenance

- works well for tiling raster data or OSM data (files many GB in size)

- can be applied to a ranged of uses: Open Aerial Map


#### Caveats:

- Set up and AWS configuration can be tricky

  - installing dependencies

  - creating IAM roles & policies

- Initial title generation is slow if seeded by users

  - little bit more time because of read & write

  - if tile doesn’t exist, create it then send it to the client

  - after tiles are created the loading is much faster


### Impractical Uses

- wouldn’t be a Stamen project if we didn’t experiment

- some triangular terrain experiments by Alan McConchie

- non-traditional representation of terrain data

- Marin County, north of San Francisco

- Washington State / Seattle area

- Seth’s Sim City isometric terrain view

- Seth’s TIN: isometric view, color to elevation & aspec


### Thank You!
