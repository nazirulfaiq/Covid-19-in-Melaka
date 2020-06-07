# Covid-19-in-Melaka
<!DOCTYPE html>
<html>
<head>
<meta charset=utf-8 />
<title>Single marker</title>
<meta name='viewport' content='initial-scale=1,maximum-scale=1,user-scalable=no' />
<script src='https://api.mapbox.com/mapbox.js/v3.3.0/mapbox.js'></script>
<link href='https://api.mapbox.com/mapbox.js/v3.3.0/mapbox.css' rel='stylesheet' />
<style>
  body { margin:0; padding:0; }
  #map { position:absolute; top:0; bottom:0; width:100%; }

.legend {
background-color: #fff;
border-radius: 3px;
bottom: 30px;
box-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
font: 12px/20px 'Helvetica Neue', Arial, Helvetica, sans-serif;
padding: 10px;
position: absolute;
right: 10px;
z-index: 1;
}
 
.legend h4 {
margin: 0 0 10px;
}
 
.legend div span {
border-radius: 50%;
display: inline-block;
height: 10px;
margin-right: 5px;
width: 10px;
}

</style>
</head>
<body>

<div id="map"></div>
 
<div id="state-legend" class="legend">
<h4>Total Covid-19 Cases updated in Melaka on 6 May 2020</h4>

<div><span style="background-color: #e62828"></span>76 cases</div>
<div><span style="background-color: #e68728"></span>57 cases</div>
<div><span style="background-color: #f2ef50"></span>31 cases</div>
</div>
 


<script>
L.mapbox.accessToken = 'pk.eyJ1IjoiZmFpcWFsaSIsImEiOiJja2I0OWtmbnowZGtlMnpvNnhlempvZG93In0.D4NrgCXDcK8PPCTEtCT2pQ';
var map = L.mapbox.map('map')
    .setView([ 2.313934,102.321096], 11)
    .addLayer(L.mapbox.styleLayer('mapbox://styles/faiqali/ckb3x6m0f1bpv1imv7g2zqbtc'));
	
var zoomThreshold = 4;	

L.mapbox.featureLayer({
    // this feature is in the GeoJSON format: see geojson.org
    // for the full specification
    type: 'Feature',
    geometry: {
        type: 'Point',
        // coordinates here are in longitude, latitude order because
        // x, y is the standard for GeoJSON and many formats
        coordinates: [
          102.321096, 2.313934
          
        ]
    },
    properties: {
        title: 'Universiti Teknikal Malaysia Melaka',
        description: 'Covid-cases = zero',
        // one can customize markers by adding simplestyle properties
        // https://www.mapbox.com/guides/an-open-platform/#simplestyle
        'marker-size': 'large',
        'marker-color': '#BE9A6B',
        'marker-symbol': 'building'
    }
}).addTo(map);
</script>

</body>
</html>
