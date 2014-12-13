# Mapbox

In den Head Bereich einer HTML Datei muss einfach die CSS- und JS-Files von Mapbox eingefügt werden.

	<script src='https://api.tiles.mapbox.com/mapbox.js/v2.0.1/mapbox.js'></script>
	<link href='https://api.tiles.mapbox.com/mapbox.js/v2.0.1/mapbox.css' rel='stylesheet' />

## Geojson

Wer Konzepte mit Geodaten macht sollte sich GeoJSON angucken.

Um eine GeoJSON-Datei auszulesen muss man nur den folgenden Code nutzen.

	<script>
	L.mapbox.accessToken = 'YOURACCESTOKEN';
	var map = L.mapbox.map('map', ‚YOURMAPID)
	.setView([52.5033, 13.3497], 15);
	var featureLayer = L.mapbox.featureLayer()
	.loadURL('/data/all_polygons.geojson')
	.addTo(map);
	featureLayer.on('ready', function() {
	// featureLayer.getBounds() returns the corners of the furthest-out markers,
	// and map.fitBounds() makes sure that the map contains these.
	map.fitBounds(featureLayer.getBounds());
	})
	</script>

Eine GeoJSON Datei ist folgendermaßen aufgebaut:
	
	{ "type": "Polygon",
	"coordinates": [
	  [ [100.0, 0.0], [101.0, 0.0], [101.0, 1.0], [100.0, 1.0], [100.0, 0.0] ]
	  ]
	}

Mehr zu GEOSJON findest du auf [geojson.org][1].

[1]:	http://geojson.org/