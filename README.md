
![KatanaSlicer-Logo](https://github.com/3DXTech/Katana/assets/84088636/68a67604-c33f-4aef-9a4e-b18379b09c9d)


# Katana

Prebuilt Windows, OSX and Linux binaries are available through the [git releases page](https://github.com/3DXTech/Katana/releases).

Katana Slicer takes 3D models (STL, OBJ, AMF) and converts them into G-code
instructions for 3DXTechs Gearbox line of 3D printers, the [HT2](https://www.3dxtech.com/3d-printer-gearbox/) and [CF2](https://www.3dxtech.com/3d-printer-gearbox-cf2/). Built ready to run with select materials from [3DXTech](https://www.3dxtech.com/products/). 

Katana is based on [PrusaSlicer](https://github.com/prusa3d/PrusaSlicer), PrusaSlicer is based on [Slic3r](https://github.com/Slic3r/Slic3r) by Alessandro Ranellucci and the RepRap community.

See the [documentation directory](doc/) for more information.

### What language is it written in?

All user facing code is written in C++, and some legacy code as well as unit
tests are written in Perl. Perl is not required for either development or use
of Katana.

The slicing core is the `libslic3r` library, which can be built and used in a standalone way.
The command line interface is a thin wrapper over `libslic3r`.

### What are Katana's main features?

Key features added are:

* slicer directly tailored to the HT2 and CF2
* chamber temperature control in filament settings
* added annealing feature
* extruder identity
* temperature limitations per filament
* XY compensation can be applied per filament


### Development

If you want to compile the source yourself, follow the instructions on one of
these documentation pages:
* [Linux](doc/How%20to%20build%20-%20Linux%20et%20al.md)
* [macOS](doc/How%20to%20build%20-%20Mac%20OS.md)
* [Windows](doc/How%20to%20build%20-%20Windows.md)

### Can I help?

Sure! You can do the following to find things that are available to help with:
* Add an [issue](https://github.com/3DXTech/Katana/issues) to the github tracker if it isn't already present.

### What's Katana license?

Katana is licensed under the _GNU Affero General Public License, version 3_.
The Katana Slicer is based on PrusaSlicer, PrusaSlicer is originally based on Slic3r by Alessandro Ranellucci.
