---
sidebar_position: 1
---

# Intro
**Who**: Welcome to the New Mexico Water Data Documentation site

**What**: This site contains information and links on the data services provided by New Mexico Water Data Initiative

**Where**: This site is maintained and hosted by the New Mexico Water Data Initiative

**Why**: The purpose of this site is to provide a comprehensive and sensible set of documentation to help guide users in
accessing and finding water data

**How**: This site was developed by the NM WDI Implementation Team



## Getting Started

Lets not mess around. Just show me how to retrieve data via the API


The following snippet shows how to retrieve Locations associated with NMBGMR in the ST2 service.
```python
import requests
url = "https://st2.newmexicowaterdata.org/FROST-Server/v1.1/Locations?$filter=properties/agency eq 'NMBGMR'"
resp = requests.get(url)
if resp.status_code==200:
    print(resp.json())
```


## Links
### API User
* <a href="https://github.com/NMWDI">NMWDI Project</a> - Link to the NMWDI GitHub Organization page
* <a href="https://developers.sensorup.com/">SensorThings Developer Center</a>
* <a href="https://developers.sensorup.com/docs/#introduction">SensorThings Documentation</a>
* <a href="https://fraunhoferiosb.github.io/FROST-Server/">FROST Server</a> - An implementation of the
   SensorThings specification
* <a href="https://github.com/FraunhoferIOSB/FROST-Python-Client">FROST Python Client</a> - A python client
   for interacting with a FROST server

### Non-API User
* <a href="https://newmexicowaterdata.org">New Mexico Water Data Home Page</a>
* <a href="https://catalog.newmexicowaterdata.org">New Mexico Water Data Catalog</a>