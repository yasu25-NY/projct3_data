# TITLE  
**Can Japan’s Ports Compete on the Global Stage?**

---

## SHORT DESCRIPTION OF WHAT YOU AIMED TO ACCOMPLISH  
To examine how competitive Japan’s ports are in the global supply chain.  
Given Japan’s low self‑sufficiency in both energy and resources, port strength is closely tied to the country’s economic and national stability.  
The project aimed to quantify and visualise port performance by comparing Japanese ports with global hubs, and to communicate these findings through an interactive website.

---

## SHORT DESCRIPTION OF YOUR FINDINGS  
Despite local stakeholders claiming that Japanese ports are growing and even understaffed due to high demand, analysis revealed that they lag significantly in global competitiveness and logistics efficiency.  
Meanwhile, Busan Port in South Korea has recorded an impressive 13.5 % growth in recent years, emerging as a highly advanced global hub.  
Japan’s major ports appear to be stagnating while rival ports in East Asia continue to expand.

---

## SUMMARY OF THE DATA COLLECTION PROCESS, WITH LINKS / OVERVIEW OF THE DATA ANALYSIS PROCESS  

This project followed a multi‑stage process that involved data collection, spatial analysis, and final visualisation through an interactive website.

### Python Notebooks  
- **`scraping_TEU.ipynb`** – Scraped TEU (Twenty‑foot Equivalent Unit) data from the World Shipping Council.  
- **`add_coordinates.ipynb`** – Merged port coordinate data from Upply.  
- **`change_long.ipynb`** – Reshaped the dataset into a long format suitable for Flourish and other visualisation tools.  
- **`growthrate.ipynb`** – Calculated port‑level growth rates between 2019 and 2023.  

### Tools Used  
- **Python** (Pandas, BeautifulSoup) – for data scraping, cleaning and analysis  
- **QGIS** – to process shapefiles and extract transit ports from the World Port Index  
- **Mapbox GL JS + Scrollama** – for interactive mapping and scroll‑based storytelling  
- **Datawrapper & Flourish** – for static and animated visualisations  
- **HTML/CSS** – to assemble the final website and embed charts and maps

### Datasets  
- **`top_50_ports.csv`** – Annual TEU data for the top 50 global ports (World Shipping Council).  
- **`port_namefull.csv`** – Port names and coordinates from Upply.  
- **`top_50_ports_list.csv`** – Merged TEU and coordinate data.  
- **`top_50_ports_long_corrected.csv`** – Long‑format TEU dataset prepared for Flourish.  
- **`japan1990.csv`**, **`japan2023.csv`** – TEU data for Japanese ports extracted manually from Japan Port and Harbor Association PDFs.  
- **`port_growth_2019_2023_labeled.csv`** – TEU data aggregated and labelled with growth rates for each port.  
- **`wpi_port2.geojson`** – GeoJSON file of transit ports derived from the World Port Index (via QGIS).  
- **`busan.kml`** – Coordinates and satellite‑based verification of Busan’s new terminal.  

Primary sources included:  
- Upply (port coordinates): https://opendata.upply.com/seaports  
- World Shipping Council: https://www.worldshipping.org/  
- National Geospatial‑Intelligence Agency (World Port Index): https://msi.nga.mil/Publications/WPI  
- Japan Port and Harbor Association: https://www.phaj.or.jp/distribution/sitemap/index.html

---

## WHAT NEW SKILLS, APPROACHES, ETC. YOU USED OR WHERE YOU GREW  

- **Designing data with the end‑visualisation in mind:** Learned that structuring and naming data properly from the outset is crucial; converting datasets to a Flourish‑friendly format after the fact was time‑consuming.  
- **Exploring geospatial tools:** QGIS has a steep learning curve and runs heavily, but once mastered it opens up powerful spatial analysis possibilities, such as extracting specific types of ports from shapefiles.  
- **Appreciating the complexity of interactive storytelling:** Even with templates, integrating Mapbox, Scrollama and custom scripts was more challenging than expected. Interactivity requires careful planning and debugging.  
- **Balancing effort and impact:** Visual storytelling is compelling, but the time investment must be weighed against the benefit. Future projects will be more strategic about which interactive elements truly add value.

---

## THINGS YOU TRIED OR WANTED TO DO BUT DIDN’T HAVE TIME/SKILLS  

- Intended to analyse port congestion levels, cargo volumes, route shifts and freight‑rate spikes for each port but could not find consistent datasets.  
- Sought more historical TEU data beyond the 1990s, but sources were limited and difficult to validate.  
- Aimed to display real‑time ship movements on the website, but this proved too complex for the current scope; plans are to explore this in a future project.  

---

## WEBSITE AND REPOSITORY LINKS  

- **Published Website:** *[https://yasu25-ny.github.io/project_3/]*  
- **Analysis Repository:** *[https://github.com/yasu25-NY/projct3_data/]*  
