---
title: "Maps R MarkDown - Leaflet"
author: "Freddy Espinoza"
date: '2022-06-26'
output: html_document
---

## R Markdown Maps

```{r}
library(leaflet)
iconPlaza <- makeIcon(
  iconUrl = "https://img.icons8.com/ios-filled/32/000000/church.png"
)

datframe <- data.frame(
  lat=c(-33.4374154, -33.438366, -33.438839, -33.447261, -33.435827, -33.420319, -33.437936, -33.430562, -33.423929, -33.438358, -33.436175),
  lng=c(-70.6512777, -70.646864, -70.641366, -70.656456, -70.65033, -70.606163, -70.65865, -70.647658,-70.644375, -70.685847, -70.629942)
)

popupOpt <- c(
  "Catedral de Santiago.<br><a href='https://www.iglesiadesantiago.cl/centros-eclesiasticos/catedral-de-santiago/catedral-de-santiago'>Más Detalles</a>",
  "Basílica de la Merced.<br><a href='https://es.wikipedia.org/wiki/Bas%C3%ADlica_de_la_Merced_(Santiago_de_Chile)'>Más Detalles</a>",
  "Iglesia de la Veracruz.<br><a href='https://es.wikipedia.org/wiki/Iglesia_de_la_Veracruz_(Santiago_de_Chile)'>Más Detalles</a>",
  "Iglesia de San Ignacio.<br><a href='https://es.wikipedia.org/wiki/Iglesia_de_San_Ignacio_(Santiago_de_Chile)'>Más Detalles</a>",
  "Iglesia de Santo Domingo.<br><a href='https://es.wikipedia.org/wiki/Iglesia_de_Santo_Domingo_(Santiago_de_Chile)'>Más Detalles</a>",
  "Iglesia Divina Providencia.<br><a href='https://es.wikipedia.org/wiki/Iglesia_de_la_Divina_Providencia'>Más Detalles</a>",
  "Iglesia Santa Ana.<br><a href='https://es.wikipedia.org/wiki/Iglesia_de_Santa_Ana_(Santiago_de_Chile)'>Más Detalles</a>",
  "Iglesia y Convento de la Recoleta Franciscana.<br><a href='https://es.wikipedia.org/wiki/Iglesia_de_la_Recoleta_Franciscana'>Más Detalles</a>",
  "Iglesia y Convento Recoleta Dominica.<br><a href='https://es.wikipedia.org/wiki/Iglesia_de_la_Recoleta_Dominica'>Más Detalles</a>",
  "Santuario y Basílica de Lourdes.<br><a href='https://es.wikipedia.org/wiki/Bas%C3%ADlica_de_Nuestra_Se%C3%B1ora_de_Lourdes_(Santiago_de_Chile)'>Más Detalles</a>",
  "Templo Parroquial de los Santos Ángeles Custodios.<br><a href='https://es.wikipedia.org/wiki/Iglesia_de_los_Santos_%C3%81ngeles_Custodios_(Santiago_de_Chile)'>Más Detalles</a>"
)

datframe %>%
  leaflet() %>%
  addTiles() %>%
  addMarkers(icon = iconPlaza, popup = popupOpt, clusterOptions = markerClusterOptions())

```




