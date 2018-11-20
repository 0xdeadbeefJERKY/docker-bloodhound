# BloodHound Docker Ready to Use

## Build Image
### Build
`docker build . -t bloodhound`

### Build with example data
`docker build . -t bloodexample --build-arg data=example`
### Optional Arguments
- **neo4j** version
- **bloodhound** version

`docker build . -t bloodhound --build-arg neo4j=3.4.8 --build-arg bloodhound=2.0.4`

## Run
```
docker run -it \
  -p 7474:7474 \
  -e DISPLAY=unix$DISPLAY \
  -v /tmp/.X11-unix:/tmp/.X11-unix \
  --device=/dev/dri:/dev/dri \
  -v ~/Desktop/bloodhound/data:/data \
  --name bloodhound bloodhound
```
### Run with example data
```
docker run -it \
  -e DISPLAY=unix$DISPLAY \
  -v /tmp/.X11-unix:/tmp/.X11-unix \
  --device=/dev/dri:/dev/dri \
  -v ~/Desktop/bloodhound/data:/data \
  --name bloodexample bloodexample
```

### Start container
```
docker start bloodhound
```

## Use
Login:
- **Database URL:** bolt://localhost:7687
- **DB Username:** neo4j
- **DB Password:** blood

There is a `bloodhound/data` folder in your Desktop with the Ingestors.
data folder is also mounted as volume, use it to drop your data and load it in  BloodHound GUI.

## Documentation
https://github.com/BloodHoundAD/BloodHound/wiki
