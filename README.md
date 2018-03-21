# d3-docs


ogr2ogr -f <format> <output> <input>

ogr2ogr -f GeoJSON -where "gu_a3 = 'USA'" states.json ne_10m_admin_0_countries_lakes.shp

geo2topo --id-property adm1_cod_1 -p name -o states_usa.topo.json states_usa.json

geo2topo counties.json > us_counties_topo.json


geo2topo --id-property adm1_cod_1 -p name -o states_usa.topo_q.json counties.json


Geo API Explorer: Earth
https://www.flickr.com/places/info/1

ogr2ogr 
	-f GeoJSON //Output format
	states.json //output file
	ne_10m_admin_0_countries_lakes.shp //input file
	-clipsrc -124.4096 32.5343 -114.1308 42.0095 //bounding box
	
http://bit.ly/usa-fips for fips codes	
ogr2ogr 
	-f GeoJSON //Output format
	states.json //output file
	ne_10m_admin_0_countries_lakes.shp //input file
	-where "STATEFP='06'" //Filtering
	
TopoJSON
--------	

geo2topo -o <output file> <input file>

geo2topo
	-o topo-counties.json //output file
	counties.json //input file

Projection

geo2topo
	-o topo-counties.json //output file
	--projection='width=960, height=600, d3.geo.albersUsa
	.scale(1280)
	.translate([width/2,height/2])' //d3 projection
	counties.json //input file
	
Simplifying Output

# --simplify precision thershold for Visvalingam simplification
#example : https://bost.ocks.org/mike/simplify

geo2topo
	-o topo-counties.json //output file
	--simplify=.5
	counties.json //input file
	
	
https://github.com/topojson/us-atlas
