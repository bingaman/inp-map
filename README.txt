# MapboxGL map for Friends of Illinois Nature Preserves

This uses mapboxGL to load two external geojson files, one with polygons for Illinois Nature Preserves and one with the centroids of the preserve outlines and fades between them.

Using the centroids at low zoom levels and gradually fading them to the shapes as you zoom in hopefully keeps some of the smaller preserves from being lost.

Because some of the preserves are carved up into many polygons I had to do some processing of the dataset I started with. First I made an aggregate based on the inpc number, then had to manually fix the names while leaving the shapes grouped. Then I found the centroids of the grouped shapes. It might be possible to write a program to do this if the data is changing a lot or maybe generate the centroids on the fly.

Loading the shapes as geojson is a little slower than using a map style but allows the data to be updated separately from the code. Switching between map and satellite requires loading the layers again.

Search is just a placeholder for now. More information could pop up into that sidebar.

Mapbox is definitely the smoothest way to serve maps online but they start charging $3 per 1000 mapviews after the first 50,000. I don't think this would be a problem for the Friends site. Mapbox also offers discounts for nonprofits https://www.mapbox.com/community/

Take whatever pieces you feel would be useful

Todos:
* Show labels at high zoom - while having them look good
* Probably could remove more stuff from the base style
* Differentiate between NP and LWR by color - waiting for updated data before attempting this
* Toggle layers
* Search and filter - this is a bigger project - either search the geojson itself or have two datasets that need to be kept in parallel. Probably the first one but that probably means putting a lot more data tables into the geojson as well as writing something to do it. And you probably want to have the map update. I could see this working like a directory.