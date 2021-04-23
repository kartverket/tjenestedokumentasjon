# WMTS (cache)

## Generell informasjon

Cache-tjenester fungerer ganske likt en WMS, men er basert på et hurtiglager med pregenererte kartbilder eller fliser ("tiles" på engelsk) på 256x256 pixler i predefinerte målestokker (zoomnivåer). En cache-tjeneste leverer ikke kartbilder i fritt valgt målestokk, men kun i de forhåndsdefinerte målestokkene som er definert i tjenesten. Cache-tjenestene er mindre fleksible, men raskere enn WMS og vel egnet til bruk på nettsider. Google Maps eller Bing Maps er kjente tjenester som er bygd opp på denne måten


## Protokoller
Tjenestene fra Kartverket støtter fire ulike protokoller som gjør dem svært anvendbare i webapplikasjoner: WMTS,  Google Maps API, Bing Maps API og WMS-C.

Cache-tjenestene bygger på underliggende WMS-tjenester og er innholdsmessig identisk med disse. For dokumentasjon av cache-tjenestene henvises det til tilhørende WMS-tjenester.

URL til WMTS: https://opencache.statkart.no/gatekeeper/gk/gk.open_wmts? ... [GetCapabilities](https://opencache.statkart.no/gatekeeper/gk/gk.open_wmts?Version=1.0.0&service=wmts&request=getcapabilities "GetCapabilities - teknisk informasjon")

URL til WMS-C: https://opencache.statkart.no/gatekeeper/gk/gk.open? ... (GetCapabilities)
URL til Google Maps: http://opencache.statkart.no/gatekeeper/gk/gk.open_gmaps?layers=[Tjenestenavn i cache]&zoom={Z}&x={X}&y={Y}
URL til Bing Maps: http://opencache.statkart.no/gatekeeper/gk/gk.open_ve?layers=[Tjenestenavn i cache]&quadkey=[keynr]&format=image/png
Cache-serverne opencache2.statkart.no og opencache3.statkart.no kan brukes til lastbalansering og for å få webklienter til å sende flere samtidige forespørsler. Kartverkets åpne cache-tjenester kan brukes i flere applikasjoner ved hjelp av Leaflet. 

For å åpne en WMTS på desktop-applikasjon som QGIS:

Velg «add WMS» og "Ny"
Gi et navn og lim inn http://opencache.statkart.no/gatekeeper/gk/gk.open_wmts?
Klikk "OK", "Connect" og velg de lagene du ønsker (vi tilbyr .jpeg og .png in ulike koordinatsystemer).
