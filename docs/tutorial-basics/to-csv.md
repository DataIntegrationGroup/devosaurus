# Write to CSV  
In this section we will demonstrate how to write data to a csv file.

```python

def write_to_csv(json_data, output):
    header='name,description,latitude,longitude,agency'
    with open(output, 'w') as wfile:
        wfile.write(header)
        for li in json_data['values']:

            row = ','.join([str(v) for v in make_location_row(li)])
            wfile.write(f'{row}\n')

def make_location_row(location)
    lat = location['location']['coordinates'][1]
    lon = location['location']['coordinates'][0]
    return [location['name'], location['description'], lat, lon, location['properties']['agency']]


```
Used in conjunction with our <code>get_locations</code> function our complete script might look something like
```python
import requests
def get_locations(agency=None):

    url = "https://st2.newmexicowaterdata.org/FROST-Server/v1.1/Locations"

    if agency:
        url = f"{url}?$filter=properties/agency eq '{agency}'"
    resp = requests.get(url)
    if resp.status_code==200:
        return resp.json()

def write_to_csv(json_data, output):
    header='name,description,latitude,longitude,agency'
    with open(output, 'w') as wfile:
        wfile.write(header)
        for li in json_data['values']:

            row = ','.join([str(v) for v in make_location_row(li)])
            wfile.write(f'{row}\n')

def make_location_row(location)
    lat = location['location']['coordinates'][1]
    lon = location['location']['coordinates'][0]
    return [location['name'], location['description'], lat, lon, location['properties']['agency']]

if __name__=='__main__':
    locations = get_locations(agency='EBID')
    write_to_csv(locations, 'EBID_locations.csv')
```
