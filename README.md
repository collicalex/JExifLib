# JExifLib
Exif meta data extractor in Java

# Use
Designed to be used as simple as possible:
* Import the single file Exif.java into your project where you want
* Then to parse the exif metadata of a jpeg file: Exif exif = new Exif(new File(picture.jpeg));
* Then to retrieve a specific data:
  * Either you know the exif tag value: _exif.get(0x0112).getValue()_
  * Either you know the exif tag name: _exif.get("Orientation").getValue()_
* Finally the getValue() function return either a String, Integer or Rationnal value. A 'rationnal' is a new class composed by a nominator and a denominator (it's the raw float data of exif format).
  
Note: even if the tag is unknown, it will be extracted by this lib, so if you know the tag you want, just use the getter with the tag value (not name).

# List of tag
The complete list of known tag (value, name and descriptions) is available in function _initExifDatas()_.
If one is missing for your camera, feel free to contact me, and provide me an example picture.

# Known project which use this lib:
* JPEGOptimizer (https://collicalex.github.io/JPEGOptimizer/)

# Debug mode
You can activate or deactivated the debug mode, by changing the value of the private parameter '_debug' in top of the class.

#TODO:
* Decode MarkerNote tag
* Decode UserComment tag
* Decode thumbnail (on demand, as it can be time consumming).
