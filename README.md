# FLIR/DJI IR Camera Data Parser, Python Version

Parser infrared camera data as `NumPy` data.

## Usage

* If you run this project code on Linux, make sure [exiftool](https://exiftool.org/install.html) is installed first or
  run `sudo apt-get install libimage-exiftool-perl` on the console to install [exiftool](https://exiftool.org/install.html).
* Copy `thermal.py` file to project directory.
* Copy `plugins` folder to same directory.
* Try the following code:

```python
import numpy as np
from thermal import Thermal

thermal = Thermal(
    dji_sdk_filename='plugins/dji_sdk/lib/windows/release_x64/libdirp.dll',
    exif_filename='plugins/exiftool-12.35.exe',
)
temperature = thermal.parse_dirp2(image_filename='images/DJI_H20T.jpg')
assert isinstance(temperature, np.ndarray)
```

## Supported IR Camera

* DJI H20T
* DJI XT2
* DJI XTR
* DJI XTS
* FLIR
* FLIR AX8
* FLIR B60
* FLIR E40
* FLIR T640
* ~~M2EA~~ (DJI will release a new version SDK that supports M2EA in the second half of 2021.)

## References

* [Thermal Image Analysis](https://github.com/detecttechnologies/Thermal-Image-Analysis) A tool for analyzing and annotating thermal images.
* [Base codes for Thermography](https://github.com/detecttechnologies/thermal_base) A python package for decoding and common processing for thermographs / thermograms
* [thermography](https://github.com/cdeldon/thermography) This repository contains the implementation of a feasibility study for automatic detection of defected solar panel modules.