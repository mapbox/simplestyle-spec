# simplestyle-spec

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT",
"SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in
this document are to be interpreted as described in RFC 2119.

## 1. Purpose

This specification attempts to create a standard for styling
geospatial data that can be shared across clients.

## 2. File format

`simplestyle` is a set of agreed-upon 'special values' in
the pre-existing [GeoJSON](http://geojson.org/) data standard that
define styles. As such, files implementing `simplestyle` are by
definition valid GeoJSON files and valid [JSON](http://json.org/) files.

```javascript
// COLOR RULES
// Colors can be in short form:
//   "#ace"
// or long form
//   "#aaccee"
// But other color formats or named colors
// are not supported
{
    "type": "FeatureCollection",
    "features": [{ "type": "Feature",
        "geometry": {
            "type": "Point",
            "coordinates": [0, 0]
        },
        "properties": {
            // OPTIONAL: default ""
            // A title to show when this item is clicked or
            // hovered over
            "title": "A title",

            // OPTIONAL: default ""
            // A description to show when this item is clicked or
            // hovered over
            "description": "A description",

            // OPTIONAL: default "medium"
            // specify the size of the marker. sizes
            // can be different pixel sizes in different
            // implementations
            // Value must be one of
            // "small"
            // "medium"
            // "large"
            "marker-size": "medium",

            // OPTIONAL: default ""
            // a symbol to position in the center of this icon
            // if not provided or "", no symbol is overlaid
            // and only the marker is shown
            // Allowed values include
            // - Icon ID from the Maki project at http://mapbox.com/maki/
            // - An integer 0 through 9
            // - A lowercase character "a" through "z"
            "marker-symbol": "bus",

            // OPTIONAL: default "7e7e7e"
            // the marker's color
            //
            // value must follow COLOR RULES
            "marker-color": "#fff"

            // OPTIONAL: default "f0f0f0"
            // the color of a line as part of a polygon, polyline, or
            // multigeometry
            //
            // value must follow COLOR RULES
            "stroke": "#f0f0f0"

            // OPTIONAL: default 0.6
            // the opacity of the line component of a polygon, polyline, or
            // multigeometry
            //
            // value must be a floating point number greater than or equal to
            // zero and less or equal to than one
            "stroke-opacity": 0.6

            // OPTIONAL: default 2
            // the width of the line component of a polygon, polyline, or
            // multigeometry
            //
            // value must be a floating point number greater than or equal to 0
            "stroke-width": 2

            // OPTIONAL: default "f0f0f0"
            // the color of the interior of a polygon
            //
            // value must follow COLOR RULES
            "fill": "#f0f0f0"

            // OPTIONAL: default 0.6
            // the opacity of the interior of a polygon
            //
            // value must be a floating point number greater than or equal to
            // zero and less or equal to than one
            "fill-opacity": 0.6
        }
    }]
}
```
