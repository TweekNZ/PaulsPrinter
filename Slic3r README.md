Slic3r Settings Cheatsheet
==========================
Check out the full [online manual](https://manual.slic3r.org/) for an explanation of all settings
## Configuration Wizard
On first install, Slic3r will run through a print configuration wizard to setup for your printer.
The values you should use are:
* G-Code Flavour: `RepRap (Marlin/Sprinter)`
* Bed Size: x: `190` y: `190` mm
* Nozzle Diameter: `0.4` mm
* Filament Diameter: `1.75` mm
* Extrusion Temperature: `180` °C
* Bed Temperature: `60` °C

## Print Settings
### Layers and Perimeters
* Layer height
  * Lower number (0.1, 0.15) = finer detail but longer print
  * Higher number (0.2, 0.3) = less fine detail but quicker prints
  * I print most things at 0.2
  * Check out the [adaptive layer height setting](https://manual.slic3r.org/expert-mode/variable-layer-height). Haven't used it myself but am keen to try it
* Horizontal shells is the number of solid layers on the top and bottom of the print
  * I tend to leave these as default
* Veritcal shells is the number of side walls - I normally use:
  * 2 by default
  * 4 if it's a part I know I am going to sand and paint

### Infill
* I very rarely change this from the default 20%

### Skirt and Brim
* Pays to always print with skirt to prime the nozzle at the start of a print

### Support Material
* Useful when there is an overhang of greater than 45°
* Can sometimes be more useful to re-orient or cut up the part so there's no overhang
* Can be helpful to add a raft when the model has minimal contact with the print bed

## Filament Settings
### Filament
* Extruder Temp
  * Default 180° for PLA
  * Can tweak for specific rolls of filament (e.g. if there's excessive stringing)
    * Only tweak a couple of degrees at a time
    * If you drop the temp too much you risk clogging the nozzle
* Bed Temp
  * Default 60-65° for PLA
### Cooling
* set the max part-fan speed



**IMPORTANT** If the model has details that are finer than the nozzle diameter (on the horizontal place) or the layer height (on the vertical plane) then the slicer will know it can't print it so ignores it completely!  It pays to check the preview before sending to printer