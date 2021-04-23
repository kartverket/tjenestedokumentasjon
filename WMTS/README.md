# WMTS (cache)

## Generell informasjon

Cache-tjenester fungerer ganske likt en WMS, men er basert på et hurtiglager med pregenererte kartbilder eller fliser ("tiles" på engelsk) på 256x256 pixler i predefinerte målestokker (zoomnivåer). En cache-tjeneste leverer ikke kartbilder i fritt valgt målestokk, men kun i de forhåndsdefinerte målestokkene som er definert i tjenesten. Cache-tjenestene er mindre fleksible, men raskere enn WMS og vel egnet til bruk på nettsider. Google Maps eller Bing Maps er kjente tjenester som er bygd opp på denne måten

[Informasjon om cache tjenester fra Kartverket](https://kartkatalog.geonorge.no/?type=service&DistributionProtocols=WMTS-tjeneste&organization=Kartverket)

## Protokoller
Tjenestene fra Kartverket støtter fire ulike protokoller som gjør dem svært anvendbare i webapplikasjoner: WMTS,  Google Maps API, Bing Maps API og WMS-C.

Cache-tjenestene bygger på underliggende WMS-tjenester og er innholdsmessig identisk med disse. For dokumentasjon av cache-tjenestene henvises det til tilhørende WMS-tjenester.

URL til WMTS: https://opencache.statkart.no/gatekeeper/gk/gk.open_wmts? ... [GetCapabilities](https://opencache.statkart.no/gatekeeper/gk/gk.open_wmts?Version=1.0.0&service=wmts&request=getcapabilities "GetCapabilities - teknisk informasjon")

### WMTS

'A Web Map Tile Service is a standard protocol for serving pre-rendered or run-time computed georeferenced map tiles over the Internet. The specification was developed and first published by the Open Geospatial Consortium in 2010' [wikipedia](https://en.wikipedia.org/wiki/Web_Map_Tile_Service)

[Introduksjon til WMTS spesifikasjonen](http://opengeospatial.github.io/e-learning/wmts/text/main.html)

[WMTS - Operasjoner](http://opengeospatial.github.io/e-learning/wmts/text/operations.html)

URL til WMTS: https://opencache.statkart.no/gatekeeper/gk/gk.open_wmts? ... [GetCapabilities](https://opencache.statkart.no/gatekeeper/gk/gk.open_wmts?Version=1.0.0&service=wmts&request=getcapabilities "GetCapabilities - teknisk informasjon")

#### Eksempel kall

[WMTS](https://opencache.statkart.no/gatekeeper/gk/gk.open_wmts?&layer=topo4&style=default&tilematrixset=EPSG%3A25833&Service=WMTS&Request=GetTile&Version=1.0.0&Format=image%2Fpng&TileMatrix=EPSG%3A25833%3A4&TileCol=7&TileRow=6)

[Google Maps](https://opencache.statkart.no/gatekeeper/gk/gk.open_gmaps?layers=topo4&zoom=7&x=67&y=37&format=image/png)

[Bing Maps]

[WMS-C](https://opencache.statkart.no/gatekeeper/gk/gk.open?LAYERS=topo4&SERVICE=WMS&VERSION=1.1.1&REQUEST=GetMap&STYLES=&FORMAT=image%2Fjpeg&SRS=EPSG%3A3857&BBOX=626172.13571241,8140237.7642584,1252344.2714246,8766409.8999705&WIDTH=256&HEIGHT=256)

#### Klient eksempler

[openlayers](./openlayers/ol-med-cache.html)

#include "/openlayers/ol-med-cache.html"

{% include_relative ./openlayers/ol-med-cache.html %}

### WMS-C

URL til WMS-C: https://opencache.statkart.no/gatekeeper/gk/gk.open? ... (GetCapabilities)
URL til Google Maps: http://opencache.statkart.no/gatekeeper/gk/gk.open_gmaps?layers=[Tjenestenavn i cache]&zoom={Z}&x={X}&y={Y}
URL til Bing Maps: http://opencache.statkart.no/gatekeeper/gk/gk.open_ve?layers=[Tjenestenavn i cache]&quadkey=[keynr]&format=image/png
Cache-serverne opencache2.statkart.no og opencache3.statkart.no kan brukes til lastbalansering og for å få webklienter til å sende flere samtidige forespørsler. Kartverkets åpne cache-tjenester kan brukes i flere applikasjoner ved hjelp av Leaflet. 

For å åpne en WMTS på desktop-applikasjon som QGIS:

Velg «add WMS» og "Ny"
Gi et navn og lim inn http://opencache.statkart.no/gatekeeper/gk/gk.open_wmts?
Klikk "OK", "Connect" og velg de lagene du ønsker (vi tilbyr .jpeg og .png in ulike koordinatsystemer).
