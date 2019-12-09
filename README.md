# Virtuoso Docker Image
It is build from the develop/7 branch

To pull and run the docker image:
```bash
$ docker login dockerhub.fokus.fraunhofer.de:5000
$ docker run -ti -p 1111:1111 -p 8890:8890 dockerhub.fokus.fraunhofer.de:5000/viaduct/piveau-virtuoso 
```
## Mounting a db volume
```bash
$ copy virtuoso.ini.template /path/to/local/virtuoso/db/virtuoso.ini
```
After editing the virtuoso.ini, run the image as follows:
```bash
$ docker login dockerhub.fokus.fraunhofer.de:5000
$ docker run -v /path/to/local/virtuoso/db:/opt/virtuoso-opensource/var/lib/virtuoso/db -ti -p 1111:1111 -p 8890:8890 dockerhub.fokus.fraunhofer.de:5000/viaduct/piveau-virtuoso 
```
Any exisiting database in the folder will be ued, oherwise a new database will be initialized.