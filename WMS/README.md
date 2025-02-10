# WMS

## Generell info

#### WMS-tjenester
Når du bruker en WMS (Web Map Service) tjeneste, er det en server som på forespørsel sender brukeren kartutsnitt i form av rasterfiler (PNG  eller JPEG). Det kan den gjøre enten direkte i nettleseren, i en webapplikasjon eller en desktopapplikasjon. Tjenestene basert på WMS-spesifikasjonen er fleksible og gir mange muligheter. Du kan for eksempel:

- Velge hvilket koordinatsystem kartbildet skal produseres i
- Skru av eller på kartlag i tjenesten. For eksempel kan du velge at bare veier og vann skal tegnes opp (og alt annet utelates)
- Velge målestokken selv
- Velge bakgrunnsfarge, eventuelt sette denne til transparent
- Velge hvilket bildeformat som skal produseres
- Hente ut tegnforklaring for de ulike kartlagene
- Hente enkel informasjon om objekter i kartbildet, som for eksempel bygninger, veier og eiendommer

Det finnes flere desktop- og webklienter som er i stand til å kommunisere med en WMS-tjeneste uten at man må utvikle kode selv, for eksempel Qgis og ArcGis.

Qgis brukermanual viser deg hvordan du åpner en WMS i QGIS.  Esris brukerveiledning viser hvordan du åpner en WMS i ArcMap. NB: Etter å ha åpnet WMS-en i ArcMaps, må du aktivere alle lagene du er interessert i, ellers vises ikke noe.

#### Tjenesteoversikt
Geonorge har en oversikt som viser våre WMStjenester [som ligger her](https://kartkatalog.geonorge.no/?type=service&organization=Kartverket&DistributionProtocols=WMS-tjeneste)

#### Eksempel tjeneste metadata:
Topografisk Norgeskart: http://wms.geonorge.no/skwms1/wms.topo?service=WMS&request=getcapabilities

Topografisk Norgeskart gråtone: http://wms.geonorge.no/skwms1/wms.topograatone?service=WMS&request=getcapabilities


#### Eksempler på tjenestekall:
[Topografisk Norgeskart](https://wms.geonorge.no/skwms1/wms.topo?service=WMS&request=GetMap&version=1.3.0&BGCOLOR=0xFFFFFF&crs=EPSG:25833&bbox=223832.52544569733,6598137.714134729,249316.94658206098,6611253.526634729&layers=topo_WMS&width=1605&height=827&format=image/png)\
[Topografisk Norgeskart gråtone](https://wms.geonorge.no/skwms1/wms.topo.graatone?service=WMS&request=GetMap&version=1.3.0&BGCOLOR=0xFFFFFF&crs=EPSG:25833&bbox=205250.6736350475,6657973.483797799,289901.233005172,6707898.1894429615&layers=topograatone_WMS&width=1684&height=994&format=image/png)\


#### URL-mønster:
https://wms.geonorge.no/skwms1/wms.topo?service=WMS&request=GetMap&version=1.3.0&BGCOLOR=0xFFFFFF&crs=EPSG:25833&bbox=223832.52544569733,6598137.714134729,249316.94658206098,6611253.526634729&layers=topo&styles=&width=1605&height=827&format=image/png





