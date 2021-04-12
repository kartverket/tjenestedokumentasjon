# WFS

## Generell informasjon

I motsetning til WMS, som leverer et kartbilde, leverer WFS (Web Feature Service) objektene som vektordata. Grensesnittet muliggjør søking etter innhold i datasettet ved å angi søkekriterier i et filter. Filterspørringene er beskrevet med et standardisert spørrespråk, ISO 19143 Filter Encoding/OGC FES 2.0

Det er først og fremst tre forespørsler/kall som brukes:

GetCapabilities - henter metadata om tjenesten, for eksempel hvilke objekttyper som tilbys, hvilke type forespørsler og filtre tjenesten tilbyr. Se eksempler på GetCapabilities - kall her
DescribeFeatureType - henter beskrivelse av datainnholdet i form av et XML skjema (XSD). Se eksempler på DescribeFeatureType
GetFeature - henter selve datainnholdet/objekter med tilhørende egenskaper. Se eksempler på GetFeature.


## Eksempler på WFS-tjenester: