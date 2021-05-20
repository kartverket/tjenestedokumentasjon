# WFS

## Generell informasjon

#### WFS-tjenester
I motsetning til WMS, som leverer et kartbilde, leverer WFS (Web Feature Service) objektene som vektordata. Grensesnittet muliggjør søking etter innhold i datasettet ved å angi søkekriterier i et filter. Filterspørringene er beskrevet med et standardisert spørrespråk, ISO 19143 Filter Encoding/OGC FES 2.0

Det er først og fremst tre forespørsler/kall som brukes:
- GetCapabilities - henter metadata om tjenesten, for eksempel hvilke objekttyper som tilbys, hvilke type forespørsler og filtre tjenesten tilbyr.\
- DescribeFeatureType - henter beskrivelse av datainnholdet i form av et XML skjema (XSD).\
- GetFeature - henter selve datainnholdet/objekter med tilhørende egenskaper.

#### Eksempler på WFS-tjenester:
Administrative enheter: https://wfs.geonorge.no/skwms1/wfs.administrative_enheter?&service=WFS&acceptversions=2.0.0&request=GetCapabilities 

Stedsnavn: https://wfs.geonorge.no/skwms1/wfs.stedsnavn?request=GetCapabilities&service=WFS

#### Eksempler på tjenestekall:
[Administrative grenser, for en kommune (Nes i Viken)](http://wfs.geonorge.no/skwms1/wfs.stedsnavn?VERSION=2.0.0&SERVICE=WFS&srsName=EPSG:25833&REQUEST=GetFeature&TYPENAME=Sted&resultType=results&Filter=%3CFilter%3E%20%3CPropertyIsEqualTo%3E%20%3CValueReference%20xmlns:app=%22http://skjema.geonorge.no/SOSI/produktspesifikasjon/StedsnavnForVanligBruk/20181115%22%3Eapp:kommune/app:Kommune/app:kommunenummer%3C/ValueReference%3E%20%3CLiteral%3E3034%3C/Literal%3E%20%3C/PropertyIsEqualTo%3E%20%3C/Filter%3E)
[Valgkretser](https://wfs.geonorge.no/skwms1/wfs.valgkretser?service=WFS&version=2.0.0&request=GetFeature&typeName=app:Valgkrets&srsName=EPSG:25832&bbox=579696.241756056,6634682.47493626,590641.156708419,6648681.78475905,EPSG:25832)

####URL-mønster:
https://wfs.geonorge.no/skwms1/wfs.valgkretser?service=WFS&version=2.0.0&request=GetFeature&typeName=app:Valgkrets&srsName=EPSG:25832&bbox=579696.241756056,6634682.47493626,590641.156708419,6648681.78475905,EPSG:25832
