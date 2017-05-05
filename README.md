# Leaflet.draw-extension
Add a "shapefile" and "geojson" button to the leaflet draw toolbar. "geojson" is not yet implemented.

## [Demo](https://ahalota.github.io/Leaflet.draw-extension/demo.html)

Example:

```
	drawLayers = new L.FeatureGroup();
	drawControl = new L.Control.DrawPlus({
		position: 'topright',		
		draw: {
			circle: false,
			polyline: false,
			shapefile: {
				shapeOptions:{
			    	color: 'black',
			    	weight: 3,
			    	opacity: 1,
			    	fillOpacity: 0					
				}
		    }, //Turn on my custom extension
		},
		edit: {
			featureGroup: drawLayers,
			edit: false
		}
	});
```

To Do: I really want this to work as an added feature to the Draw control, not needing to be an extended class. Please tell me how to do this if you know!

Tool will fire one L.Draw.CREATED event for each unique Polygon in the imported shapefile. Multipolygons will be one single event.

Requires [Leaflet.draw](https://github.com/Leaflet/Leaflet.draw), [leaflet-shapefile](https://github.com/calvinmetcalf/leaflet.shapefile), and [shapefile-js](https://github.com/calvinmetcalf/shapefile-js) plugins. Versions used when I wrote this plugin are included in this repository for convenience. If you put everything into a 'lib' folder in your final project you will have to copy the 'images' file into there too. The picture should be transparent but right now has a white background, I'll fix it some day.
