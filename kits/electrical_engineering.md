# Pop!\_OS Electrical Engineering Kit

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

**Regarding libraries in KiCAD**

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

**Regarding packaging KiCAD**

In the short term, the best possible KiCad experience for your users is
going to be had by providing a wxWidgets 3.0.4 package built against
gtk2 and a wxPython package built against the same wxWidgets package if
possible.  It may not build against 3.0.4 and you may have to fall back
to 3.0.3 which I believe is built by default when building wxPython.
You will get a warning about the wxWidgets mismatch when running kicad
from the command line but most users wont ever see it. This works on Ubuntu
17.10 with GNOME as a desktop environment. 

Most distros are starting to distribute wxWidgets 3.0.4 built against
gtk3 which effectively makes the current stable release (5.0.1)
unusable. KiCAD are working to rectify this issue. This will
be released as version 5.1 hopefully before FOSDEM 2019.  Unfortunately,
the new wxPython project (Phoenix) decided to change from SWIG to SIP as
it's scripting generation language which means it may be some time
before we can support Phoenix as all of the scripting language
generation code in kicad uses SWIG which may not work with Phoenix.


The longer you can stick with gtk2 builds of wxWidgets and wxPython, the
better off your users will be.  Once 5.1 is released, you should be able
to convert over to gtk3 version of wxWidgets and wxPython.  As for
supporting Phoenix, that's anyone's guess at this point.  Also, you will
have to continue to distribute python2 because wxPython does not build
against python3.
