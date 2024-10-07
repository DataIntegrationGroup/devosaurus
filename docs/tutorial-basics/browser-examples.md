# Browser Examples

## ST2 SensorThings API

### Get Locations for EBID
```http
https://st2.newmexicowaterdata.org/FROST-Server/v1.1/Locations?$filter=properties/agency eq 'EBID'
```

### Get Locations for EBID with Things
```http
https://st2.newmexicowaterdata.org/FROST-Server/v1.1/Locations?$filter=properties/agency eq 'EBID'&$expand=Things"
```

### Get all Locations and Things with a Location name that startswith 'AR-'
```http
https://st2.newmexicowaterdata.org/FROST-Server/v1.1/Locations?$filter=startswith(name,'AR-')&$expand=Things
```

### Get all Locations and Things within a given bounding box defined by latitudes and longitudes
```http
"https://st2.newmexicowaterdata.org/FROST-Server/v1.1/Locations?
$filter=st_within(location, geography'POLYGON((-106.9466 34.1201,-106.8038 34.1201,-106.8038 34.0086,-106.9466 34.0086,-106.9466 34.1201))')&
$expand=Things"
```

### Get all datastreams with name 'Groundwater level(Pressure)'
```http
https://st2.newmexicowaterdata.org/FROST-Server/v1.1/Datastreams?$filter=name eq 'Groundwater level(Pressure)'
``` 