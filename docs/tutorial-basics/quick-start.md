# Quick Start

This is a simple tutorial to demonstrate how to get all the Locations for a given <i>agency</i> as a <code>JSON
</code> document. This tutorial assumes basic knowledge of python.


## Get Locations
The function <code>get_locations</code> uses the <code>requests</code> package
to send a <code>HTTP GET</code> to the <b>ST2</b> endpoint. <code>get_locations</code> takes
one optional keyword argument <code>agency</code>.

```python
import requests
def get_locations(agency=None):

    url = "https://st2.newmexicowaterdata.org/FROST-Server/v1.1/Locations"

    if agency:
        url = f"{url}?$filter=properties/agency eq '{agency}"
    resp = requests.get(url)
    if resp.status_code==200:
        return resp.json()

```

## Example Response
And example response will be a <code>JSON</code> document.

```json
{
  "@iot.nextLink": "https://st2.newmexicowaterdata.org/FROST-Server/v1.1/Locations?$skip=1000&$filter=%28properties%2Fagency+eq+%27NMBGMR%27%29",
  "value": [
    {
      "description": "Location of well where measurements are made",
      "encodingType": "application/vnd.geo+json",
      "@iot.id": 5527,
      "location": {
        "type": "Point",
        "coordinates": [
          -106.41818948667888,
          33.53256431564087
        ]
      },
      "name": "BW-0505",
      "properties": {
        "WellID": "6C7183D7-387C-4870-924D-43CFD3D82A76",
        "agency": "NMBGMR",
        "PointID": "BW-0505",
        "Altitude": 5020.0,
        "geoconnex": "https://geoconnex.us/nmwdi/st/locations/5527",
        "source_id": 33657.0
      },
      "@iot.selfLink": "https://st2.newmexicowaterdata.org/FROST-Server/v1.1/Locations(5527)",
      "HistoricalLocations@iot.navigationLink": "https://st2.newmexicowaterdata.org/FROST-Server/v1.1/Locations(5527)/HistoricalLocations",
      "Things@iot.navigationLink": "https://st2.newmexicowaterdata.org/FROST-Server/v1.1/Locations(5527)/Things"
    },
    {
      "description": "Location of well where measurements are made",
      "encodingType": "application/vnd.geo+json",
      "@iot.id": 6531,
      "location": {
        "type": "Point",
        "coordinates": [
          -104.02631531212303,
          32.65869888498076
        ]
      },
      "name": "ED-0058",
      "properties": {
        "WellID": "B7C6FC70-A7B2-4E21-8A88-AC96FAAAE8D2",
        "agency": "NMBGMR",
        "PointID": "ED-0058",
        "Altitude": 3310.0,
        "geoconnex": "https://geoconnex.us/nmwdi/st/locations/6531",
        "source_id": 35045.0
      },
      "@iot.selfLink": "https://st2.newmexicowaterdata.org/FROST-Server/v1.1/Locations(6531)",
      "HistoricalLocations@iot.navigationLink": "https://st2.newmexicowaterdata.org/FROST-Server/v1.1/Locations(6531)/HistoricalLocations",
      "Things@iot.navigationLink": "https://st2.newmexicowaterdata.org/FROST-Server/v1.1/Locations(6531)/Things"
    }
  ]
}
```

If you look closely at the <code>get_locations</code> function you will see that it assembles an <code>url</code> and
then sends an
<b>HTTP GET</b> to that <code>url</code>.  For example, if you want to get all the <b>Locations</b> for <i>EBID</i>
the <code>url</code> will be
<code>https://st2.newmexicowaterdata.org/FROST-Server/v1.1/Locations?$filter=properties/agency eq
'EBID'</code>


Try it yourself! Copy the <code>url</code> into your browser address bar and you should see the 2 <b>Locations</b> for
<i>EBID</i> in the <b>ST2</b> endpoint displayed as a <code>JSON</code> document
