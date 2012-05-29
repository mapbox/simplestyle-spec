# simplestyle-style

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
{
    "type": "FeatureCollection",
    "features": [{ "type": "Feature",
        "geometry": {
            "type": "Point",
            "coordinates": [0, 0]
        },
        "properties": {
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
            // - A lowercase charecter "a" through "z"
            "marker-symbol": "bus",

            // OPTIONAL: default "7e7e7e"
            // the color or the marker is by default
            // a color to which the graphic is tinted
            //
            // marker-color must be a valid hex color
            // it can be in short form:
            //   marker-color: "#ace"
            // or long form
            //   marker-color: "#aaccee"
            // But other color formats or named colors
            // are not supported
            "marker-color": "#fff"
        }
    }]
}
```
