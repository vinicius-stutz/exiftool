# exiftool
Comandos para exiftool.

## Bulk join json with image from Google Takeout
Copy all the data from the JSON to the files, modifying the original files (2020):

`exiftool -r -d %s -tagsfromfile "%d/%F.json" "-GPSAltitude<GeoDataAltitude" "-GPSLatitude<GeoDataLatitude" "-GPSLatitudeRef<GeoDataLatitude" "-GPSLongitude<GeoDataLongitude" "-GPSLongitudeRef<GeoDataLongitude" "-Keywords<Tags" "-Subject<Tags" "-Caption-Abstract<Description" "-ImageDescription<Description" "-DateTimeOriginal<PhotoTakenTimeTimestamp" -ext {IMAGE TYPE HERE} -overwrite_original {PATH HERE}`

Ex.:

```
exiftool -r -d %s -tagsfromfile "%d/%F.json" "-GPSAltitude<GeoDataAltitude" "-GPSLatitude<GeoDataLatitude" "-GPSLatitudeRef<GeoDataLatitude" "-GPSLongitude<GeoDataLongitude" "-GPSLongitudeRef<GeoDataLongitude" "-Keywords<Tags" "-Subject<Tags" "-Caption-Abstract<Description" "-ImageDescription<Description" "-DateTimeOriginal<PhotoTakenTimeTimestamp" -ext jpg -overwrite_original ./
```

Ref.: https://stackoverflow.com/questions/42024255/bulk-join-json-with-jpg-from-google-takeout

## Copy metadata to another image
`exiftool -TagsFromFile srcimage.jpg "-all:all>all:all" targetimage.jpg`

Ex.:

```
exiftool -TagsFromFile IMG-20230105-WA0009.jpg "-all:all>all:all" IMG-20230105-WA0009-edited.jpg
```

Ref.: https://exiftool.org/forum/index.php?topic=3440.0
