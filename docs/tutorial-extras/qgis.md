---
sidebar_position: 1
---

# QGIS integration

Plot ST2 SensorThing locations directly in QGIS

1. add a new vector layer
2. Check Protocol is set to HTTP(s),cloud,etc
3. Set Type to "GeoJSON"
4. Set URI to ```https://st2.newmexicowaterdata.org/FROST-Server/v1.1/Locations?$filter=properties/agency eq 
   'NMBGMR'&$resultFormat=geojson```



