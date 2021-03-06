# water-diviner
An AR app to guide users to the nearest water source
## Devpost
[Click here](https://devpost.com/software/water-diviner) to see our Devpost submission for the hackathon.

# Geolocated Data
## OpenStreetMaps
We found the OpenStreetMaps has the [largest catalog of drinking water sources](https://wiki.openstreetmap.org/wiki/Tag:amenity%3Ddrinking_water). The ESRI folks helped us find a [site](http://overpass-turbo.eu/) that searches for OSM layers based on a simple search, and allows you to download that as GeoJSON, KML, and other formats.
We [posted a call](https://www.reddit.com/r/openstreetmap/comments/846gnf/creating_reality_vr_hackathon_ar_water_map/) for support on the OSM redit, but haven't heard anything back yet. 

## NASA-GRACE
[GLDAS Land Water Content (monthly)](https://grace.jpl.nasa.gov/data/get-data/land-water-content/)
- A GRACE-independent forward simulation of monthly land water storage changes (currently using soil moisture, snow, and canopy water). Can be used for comparison and residual groundwater studies.
- The grids of total water content every 3 hours were averaged over nominal months. The time-averaged grid Jan-2003 to Dec-2007 was then subtracted from all the individual monthly grids. The data are available in ASCII format (one file per month), in NetCDF format (one file for the whole time period), and as GIF images and animations.

[Interactive GRACE Data Browsers](https://grace.jpl.nasa.gov/data/get-data/interactive-browsers/)
- These links to data browser allow the interactive retrieval of GRACE Land data over river basins, as well as the evaluation of long-term trends and mean seasonal amplitudes. Interactive data browsers that allow users to explore and download grid-point to basin-level GRACE data.

## Hardware
We currently have a Meta 2 headset that I was able to lean from MetaVision. Then HP loaned us a backpack workstation that can run VR,
so we're thinking of a AR experience that uses those in combo.

# Initial Approach
## Plan A: ArcGIS Mapping Engine
ArcGIS is one of the Gold Sponsors of the Creating Reality hackathon, and they are offering a $2500 prize for building something either 
with their new AR Runtime SDK (preferrably), or some of their API's. Issue currently is their new SDK doesn't work with Unity. 
We've talked through a couple of ways to hack it to work with the OpenVR SDK though, we just need to get the ArcGIS SDK (.NET) to talk
with the OpenVR standard (C++).  
https://github.com/ValveSoftware/openvr/tree/master/samples
https://github.com/Esri/hololens-terrain-viewer/blob/master/README.md
- [ ] Dig through OpenVR Standard and get a basic understanding of it:  
http://devcenter.metavision.com/get-started/software-setup/installing-the-openvr-sdk/ https://steamcommunity.com/app/358720/discussions/0/142260895142733091/
- [x] Join the ArcGIS AR Runtime SDK Private Beta program
- [x] Get ArcGIS VR Runtime SDK working
- [ ] Dig through ArcGIS AR Runtime SDK

## Plan B: Mapbox + Unity with ArcGIS API calls
Our alternative approach is to use Mapbox's Unity SDK. Our team is generally much more familiar with Unity, and I've worked with 
Mapbox in Unity before several times. If we go this route we could make something similar to Pokemon Go style, and spend more time working on gamifying the experience, playing with the dynamics of a reputation system for discovering/auditing drinkable water sources, and so on.

## Plan C: AR Core
We also have a Google Pixel, and ArcGIS Runtime SDK works with Android, so a simpler route might be to build a phone AR based experience.

# Tuesday Night Decision
## Unity + Mapbox + AR Core
We spent much of yesterday looking into the opposing frameworks for the project. We really wanted to find a way to use ESRI in order to
get the most of our access to the ESRI team, and learn both more about the tools they offered, as well as the OpenVR framework. After hours of debate and trial & error, our team decided that working with Unity and Mapbox was the path of least resistance. So moving forward we are developing with Plan C: the AR Core Mapbox Unity Build.
