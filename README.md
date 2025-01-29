# Fusion 360 to URDF Exporter for ROS 2

## Overview
This repository is initially forked from [dheena/fusion2urdf-ros2]([https://github.com/dheena/fusion2urdf-ros2)](https://github.com/dheena2k2/fusion2urdf-ros2) and has been modified to export a robot description package suited for ROS 2 using the `ament_python` build type.

For users looking to convert Fusion 360 models to URDF for ROS 1, please check out [syuntoku14/fusion2urdf](https://github.com/syuntoku14/fusion2urdf).

## Features
- Exports Fusion 360 models as a ROS 2-compatible robot description package.
- Supports `ament_python` build system.
- Includes necessary modifications to ensure compatibility with ROS 2.

## Installation & Usage
### Prerequisites
Ensure you have the following dependencies installed:
- ROS 2 (Humble, Foxy, or later)
- Python 3
- Autodesk Fusion 360 with API support

### Fix for `distutils` ModuleNotFoundError
If you encounter the following error:

```python
Traceback (most recent call last):
  File "C:/Users/psdhu/AppData/Roaming/Autodesk/Autodesk Fusion 360/API/Scripts/URDF_Exporter_Ros2/URDF_Exporter_Ros2.py", line 7, in <module>
    from .utils import utils
  File "C:/Users/psdhu/AppData/Roaming/Autodesk/Autodesk Fusion 360/API/Scripts/URDF_Exporter_Ros2/utils/utils.py", line 12, in <module>
    from distutils.dir_util import copy_tree
ModuleNotFoundError: No module named 'distutils'
```

You can resolve it by installing `setuptools`:

```bash
pip install setuptools
```

Alternatively, modify the script to use `shutil` instead of `distutils`:

```python
from shutil import copytree
```

## Contributing
Feel free to submit issues and pull requests if you find any bugs or have feature improvements.

## Credits
- Forked from [dheena/fusion2urdf-ros2](https://github.com/dheena/fusion2urdf-ros2)
- Inspired by [syuntoku14/fusion2urdf](https://github.com/syuntoku14/fusion2urdf)

## License
This project is licensed under the  License.

