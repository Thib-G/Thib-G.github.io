# [thib.goelff.be](https://thib.goelff.be)
A few demos.

## Demos on Github Pages

* [Level crossing animation (animation passage à niveau)](https://thib.goelff.be/pn-anim/#/chart): simulate a level crossing
with data coming from IoT during one hour.
* [Electathon 2019](https://thib.goelff.be/electathon19-app/#/seats): results of 2019 Belgian elections with data provided by [Open Knowledge Belgium](https://elections.openknowledge.be/) (THE API IS DEAD)
* [Coronavirus map](https://thib.goelff.be/coronavirus/): map with a little animation of confirmed, recovered and (sadly) deaths using data from [Johns Hopkins CSSE](https://github.com/CSSEGISandData/COVID-19/). [Incidence map](https://thib.goelff.be/coronavirus/#/belgium) for Belgium using data from [Sciensano](https://epistat.wiv-isp.be/covid/).
* I made a geographical plugin for Yasgui (Yet another SPARQL GUI). You can find it on [this GitHub repo](https://github.com/Thib-G/yasgui-geo-tg) or try it yourself [here](https://linked-data.goelff.be/yasgui/#query=PREFIX%20geo%3A%20%3Chttp%3A%2F%2Fwww.opengis.net%2Font%2Fgeosparql%23%3E%0APREFIX%20wgs%3A%20%3Chttp%3A%2F%2Fwww.w3.org%2F2003%2F01%2Fgeo%2Fwgs84_pos%23%3E%0APREFIX%20rdfs%3A%20%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0APREFIX%20era%3A%20%3Chttp%3A%2F%2Fdata.europa.eu%2F949%2F%3E%0APREFIX%20country%3A%20%3Chttp%3A%2F%2Fpublications.europa.eu%2Fresource%2Fauthority%2Fcountry%2F%3E%0A%0ASELECT%20DISTINCT%20%3Fsol%20%3FsolLabel%20%3FopStartLabel%20%3FopEndLabel%20%3Fcountry%20%3Fwkt%0AWHERE%20%7B%0A%20%20%3Fsol%20a%20era%3ASectionOfLine%20%3B%0A%20%20%20%20%20%20%20era%3AinCountry%20%3Fcountry%20%3B%0A%20%20%20%20%20%20%20era%3AopStart%20%3FopStart_canonical%20%3B%0A%20%20%20%20%20%20%20era%3AopEnd%20%3FopEnd_canonical%20%3B%0A%20%20%20%20%20%20%20rdfs%3Alabel%20%3FsolLabel%20.%0A%0A%20%20%3FopStart%20era%3AcanonicalURI%20%3FopStart_canonical%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20wgs%3Alocation%20%3FopStartLocation%20.%0A%20%20%0A%20%20%3FopStart_canonical%20rdfs%3Alabel%20%3FopStartLabel%20.%0A%0A%20%20%3FopStartLocation%20wgs%3Alat%20%3FopStartLat%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20wgs%3Along%20%3FopStartLng%20.%0A%0A%20%20%3FopEnd%20era%3AcanonicalURI%20%3FopEnd_canonical%20%3B%0A%20%20%20%20%20%20%20%20%20wgs%3Alocation%20%3FopEndLocation%20.%0A%20%20%0A%20%20%3FopEnd_canonical%20rdfs%3Alabel%20%3FopEndLabel%20.%0A%0A%20%20%3FopEndLocation%20wgs%3Alat%20%3FopEndLat%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20wgs%3Along%20%3FopEndLng%20.%0A%0A%20%20FILTER(%3Fcountry%20%3D%20country%3ABEL)%0A%0A%20%20%23%20Create%20WKT%20string%20with%20CRS%0A%20%20BIND(%0A%20%20%20%20CONCAT(%0A%20%20%20%20%20%20%22%3Chttp%3A%2F%2Fwww.opengis.net%2Fdef%2Fcrs%2FOGC%2F1.3%2FCRS84%3E%20LINESTRING(%22%2C%0A%20%20%20%20%20%20STR(%3FopStartLng)%2C%20%22%20%22%2C%20STR(%3FopStartLat)%2C%20%22%2C%20%22%2C%0A%20%20%20%20%20%20STR(%3FopEndLng)%2C%20%22%20%22%2C%20STR(%3FopEndLat)%2C%0A%20%20%20%20%20%20%22)%22%0A%20%20%20%20)%20AS%20%3FwktString%0A%20%20)%0A%0A%20%20%23%20Cast%20to%20geo%3AwktLiteral%0A%20%20BIND(STRDT(%3FwktString%2C%20geo%3AwktLiteral)%20AS%20%3Fwkt)%0A%7D%0A&endpoint=https%3A%2F%2Fdata-interop.era.europa.eu%2Fapi%2Fsparql&requestMethod=POST&tabTitle=Query%201&headers=%7B%7D&contentTypeConstruct=application%2Fn-triples%2C*%2F*%3Bq%3D0.9&contentTypeSelect=application%2Fsparql-results%2Bjson%2C*%2F*%3Bq%3D0.9&outputFormat=geo).

## Demos on other sites

* [Infrabel railway locator](https://railbe-lrs.kediss.eu/): find your nearest kilometer pole and find route to level crossing in Belgium.
* [Infrabel open-data sandbox](https://infrabel-opendata.goelff.be/): playing with some Infrabel open-data datasets.
* [UFO sightings](https://ufo.kediss.eu/): data visualization project for Certificate in Data Science Namur 2018-2019.
* [Local currency map (Carol’or)](https://carolor.org/map/): map of Carol’Or partners, the local currency in Charleroi (Belgium).
* [Mobilive](https://mobilive.maww.be): show travel time in train and car from main train stations in Belgium, using iRail API and Google Maps Distance Matrix API.
* [Pas Evident.be](https://pasevident.be): demotivational quotes in French -- phrases démotivationnelles en Français (laisser défiler).
* `DEPRECATED` [Local currency map](https://carolor-map.kediss.eu/): a Leaflet map with a GeoDjango back-end (FAKE DATA). The real site is [here](https://www.carolor.org/).
* 

## Contact
Thibaut Goelff

* Twitter: [@tgoelff](https://twitter.com/tgoelff)
* [LinkedIn](https://www.linkedin.com/in/thibautgoelff/)
