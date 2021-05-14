# WMTS (cache)

>## Generell informasjon

>Cache-tjenester fungerer ganske likt en WMS, men er basert på et hurtiglager med pregenererte kartbilder eller fliser ("tiles" på engelsk) på 256x256 pixler i predefinerte målestokker (zoomnivåer). En cache-tjeneste leverer ikke kartbilder i fritt valgt målestokk, men kun i de forhåndsdefinerte målestokkene som er definert i tjenesten. Cache-tjenestene er mindre fleksible, men raskere enn WMS og vel egnet til bruk på nettsider. Google Maps eller Bing Maps er kjente tjenester som er bygd opp på denne måten

>[Informasjon om cache tjenester fra Kartverket](https://kartkatalog.geonorge.no/?type=service&DistributionProtocols=WMTS-tjeneste&organization=Kartverket)

-## Protokoller
-Tjenestene fra Kartverket støtter fire ulike protokoller som gjør dem svært anvendbare i webapplikasjoner: WMTS,  Google Maps API, Bing Maps API og WMS-C.

-Cache-tjenestene bygger på underliggende WMS-tjenester og er innholdsmessig identisk med disse. For dokumentasjon av cache-tjenestene henvises det til tilhørende WMS-tjenester.

-URL til WMTS: https://opencache.statkart.no/gatekeeper/gk/gk.open_wmts? ... [GetCapabilities](https://opencache.statkart.no/gatekeeper/gk/gk.open_wmts?Version=1.0.0&service=wmts&request=getcapabilities "GetCapabilities - teknisk informasjon")

nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;### WMTS

nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'A Web Map Tile Service is a standard protocol for serving pre-rendered or run-time computed georeferenced map tiles over the Internet. The specification was developed and first published by the Open Geospatial Consortium in 2010' [wikipedia](https://en.wikipedia.org/wiki/Web_Map_Tile_Service)

nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Introduksjon til WMTS spesifikasjonen](http://opengeospatial.github.io/e-learning/wmts/text/main.html)

nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[WMTS - Operasjoner](http://opengeospatial.github.io/e-learning/wmts/text/operations.html)

nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;URL til WMTS: https://opencache.statkart.no/gatekeeper/gk/gk.open_wmts? ... [GetCapabilities](https://opencache.statkart.no/gatekeeper/gk/gk.open_wmts?Version=1.0.0&service=wmts&request=getcapabilities "GetCapabilities - teknisk informasjon")

#### Eksempel kall

[WMTS](https://opencache.statkart.no/gatekeeper/gk/gk.open_wmts?&layer=topo4&style=default&tilematrixset=EPSG%3A25833&Service=WMTS&Request=GetTile&Version=1.0.0&Format=image%2Fpng&TileMatrix=EPSG%3A25833%3A4&TileCol=7&TileRow=6)

URL Mønster:
https://opencache.statkart.no/gatekeeper/gk/gk.open_wmts?REQUEST=GetTile&SERVICE=WMTS&VERSION=1.0.0&LAYER={lagnavn}&STYLE=&TILEMATRIXSET={EPSG:####}&TILEMATRIX={EPSG:####{z}}&TILECOL={x}&TILEROW={y}&Format={image type}


#### Klient eksempler

[openlayers](../openlayers/ol-med-cache.html)


### WMS-C

WMS-C (WMS tile caching) er en gammel spesifikasjon som er erstatett av WMTS, men fremdeles brukes i mange klienter. Fordelen med denne protokollen er at mønsteret på kallene er identisk med WMS, som mange er kjent med. 

URL til WMS: https://opencache.statkart.no/gatekeeper/gk/gk.open? ... [GetCapabilities](https://opencache.statkart.no/gatekeeper/gk/gk.open?SERVICE=WMS&VERSION=1.1.1&REQUEST=getcapabilities&TILED=true "GetCapabilities - teknisk informasjon")

#### Eksempel kall

[WMS-C](https://opencache.statkart.no/gatekeeper/gk/gk.open?LAYERS=topo4&SERVICE=WMS&VERSION=1.1.1&REQUEST=GetMap&STYLES=&FORMAT=image%2Fjpeg&SRS=EPSG%3A3857&BBOX=626172.13571241,8140237.7642584,1252344.2714246,8766409.8999705&WIDTH=256&HEIGHT=256)

URL Mønster:
https://opencache.statkart.no/gatekeeper/gk/gk.open?LAYERS={lagnavn}&SERVICE=WMS&VERSION=1.1.1&REQUEST=GetMap&STYLES=&FORMAT={format}&SRS={EPSG:####}&BBOX={bbox}&WIDTH=256&HEIGHT=256

#### Klient eksempler

[openlayers](../openlayers/ol-med-cache.html)

### Google Maps

'Google was one of the first major mapping providers to adopt the tiled web maps. Others, like Bing and OpenStreetMap, followed the same practice. GIS software vendors, like Esri and Oracle, provide functionality for map tiling and caching of both vector layers and raster images.'

Denne protokollen bruker en enkel z,x,y mønster som betyr at tjenester er enkel å bruke i applikasjoner, men en ulemper er at denne protokollen støtter kun google web mercator projeksjonen (EPSG:900913/3857).

URL til WMS: https://opencache.statkart.no/gatekeeper/gk/gk.open? ... [GetCapabilities](https://opencache.statkart.no/gatekeeper/gk/gk.open?SERVICE=WMS&VERSION=1.1.1&REQUEST=getcapabilities&TILED=true "GetCapabilities - teknisk informasjon")

#### Eksempel kall

[Google Maps](https://opencache.statkart.no/gatekeeper/gk/gk.open_gmaps?layers=topo4&zoom=9&x=271&y=148&format=image/png)

URL Mønster:
https://opencache.statkart.no/gatekeeper/gk/gk.open_gmaps?layers={lagnavn}&zoom={z}&x={x}&y={y}&format={format}

#### Klient eksempler

[openlayers](../openlayers/ol-med-cache.html)

### Bing Maps

Bing Maps protokollen (https://docs.microsoft.com/en-us/bingmaps/#pivot=main&panel=BingMapsAPI) var tidligere kjent som VE (virtual Earth) or brukes ikke mye utenfor Bing applikasjoner.

Denne protokollen bruker en quadkey for å kode informasjonen om hvilken tile som skal returneres, og i likhet med Google maps er en ulemper at denne protokollen støtter kun web mercator projeksjonen (EPSG:900913/3857).

Informajson om Bing maps protokollen og quadkey: [Bing Maps Tile System](https://docs.microsoft.com/en-us/bingmaps/articles/bing-maps-tile-system)

#### Eksempel kall

[Bing Maps](https://opencache.statkart.no/gatekeeper/gk/gk.open_ve?layers=topo4&quadkey=12002131012&format=image/png)

URL Mønster:
http://opencache.statkart.no/gatekeeper/gk/gk.open_ve?layers={lagnavn}&quadkey={keynr}&format={format}

#### Klient eksempler

[openlayers](../openlayers/ol-med-cache.html)
