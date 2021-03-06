Leaflet.Snap
============

Enables snapping of draggable markers to polylines and other layers !

Check out the [demo](http://makinacorpus.github.com/Leaflet.Snap/) !


It depends on [Leaflet.GeometryUtil](https://github.com/makinacorpus/Leaflet.GeometryUtil).

For Polyline edition snapping it also depends on [Leaflet.draw](https://github.com/Leaflet/Leaflet.draw).

If your guide layer contains several thousands for features, adding the [LayerIndex](https://github.com/makinacorpus/Leaflet.LayerIndex) is recommended, this plugin takes advantage of the spatial index if it is available.

Usage
-----

* Add ``leaflet.snap.js`` and ``leaflet.geometryutil.js`` (optionally ``leaflet.draw.js`` for polyline edition)

For markers : 

```javascript

    var guideLayer = ...;

    var marker = L.marker([48.488, 1.395]).addTo(map);
        marker.snapediting = new L.Handler.MarkerSnap(map, marker);
        marker.snapediting.addGuideLayer(guideLayer);
        marker.snapediting.enable();
```

For polylines : 

```javascript
    var polyline = L.polyline(...).addTo(map);
        polyline.snapediting = new L.Handler.PolylineSnap(map, polyline);
        polyline.snapediting.addGuideLayer(guideLayer);
        polyline.snapediting.enable();
```

Events:

**snap** ( _layer_, _latlng_ ) : fired when snapped to ``layer`` at ``latlng``

**unsnap** ( _layer_ ) : fired when unsnapped from ``layer``


TODO
----

* Add init hooks to simplify initialization

Authors
-------

[![Makina Corpus](http://depot.makina-corpus.org/public/logo.gif)](http://makinacorpus.com)
