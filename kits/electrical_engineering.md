# Pop!\_OS Electrical Engineering Kit

## Hardware

- System76 Oryx Pro - https://system76.com/laptops/oryx

## Packages

- avrdude - http://savannah.nongnu.org/projects/avrdude/
- KiCad - http://kicad-pcb.org/
- libc-avr - https://www.nongnu.org/avr-libc/
- Arduino IDE - https://www.arduino.cc/en/Main/Software
- *PROPOSED BY A USER, NEEDS DISCUSSION* - Eagle - https://www.autodesk.com/products/eagle/blog/how-to-install-autodesk-eagle-on-windows-mac-and-linux/
- Digi-Key KiCAD part library: https://github.com/digikey/digikey-kicad-library/

## Example Project

- System76 Thelio Io - https://github.com/system76/thelio-io, maintained by Jeremy Soller - https://github.com/jackpot51

## Notes

*Regarding libraries in KiCAD*
you would have to add the
libraries to the global symbol[1] and footprint library[2] tables that
get installed with KiCad.  Out of the box, the global symbol and
footprint only support the libraries provided by the KiCad project.
Otherwise users will have to do it themselves in order to use the
libraries.  I haven't looked but if the Digi-Key libraries include 3D
models for the footprints, that requires a custom configuration unless
you install the models in the same path as the 3D models that are
provided by KiCad.

[1]: https://github.com/KiCad/kicad-symbols/blob/master/sym-lib-table
[2]: https://github.com/KiCad/kicad-footprints/blob/master/fp-lib-table

Libraries are going to be the most challenging issue.  I know there are
some good videos about setting up KiCad on YouTube which may be helpful
and the KiCad user forum (https://forum.kicad.info/) may also be helpful.
