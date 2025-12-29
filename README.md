# SeeStar-Processing-Guide
A beginners guide to processing images from the SeeStar. 

- SeeStar Settings
- - Save frames
  - Exposure times
  - EQ Mounting
  - Planning
  - Mosaics
- Processing Software Installation
- - Siril
  - GraXpert
  - StarNet++
  - Cosmic Clarity
  - GIMP
- Workflow

Astrophotography Processing Workflow

Finder:
Folder name "Catalogue Object [Mosaic] RAW FITs Month Year"
Extract lights to "lights" directory

Siril 1.4:
Set home directory to "Catalogue Object [Mosaic] RAW FITs Month Year"

Normal Stack
Run SeeStar Stacking Script

Mosaic Stack
Run DSA SeeStar Mosaic Stacking Script

Drizzle Stack
Create process directory
Set home to process directory
Conversion Tab
Add lights
Sequence Name -> lights
Convert
Registration Tab
Output Registration -> Reciprocal -> Scaling=2x/PixelSize=0.5
Go Register
Stacking Tab
Output Normalization checked
RGB Equalization checked
Start Stacking

Preprocess
Open processed file
View in autostretch mode
Run background extraction (Built In or GraXpert Script)
Plate solve (Tools -> Astrometry -> Image Plate Solver)
Spectrophotometric Color Calibration -> Set SeeStar S50 Sensor
Remove stars with starnet

Autostretch
Switch to linear
Use VeraLUX auto stretch script
Set SeeStar S50 Sensor
Autocalculate Log D


Denoise
Sharpen
Star Recomposition VeraLUX -> Background is starless, foreground is starmask -> stretch in stars
Run GraXpert AI denoise again if needed
Sharpen if needed
Histogram stretch move darks to make darker

Save

GIMP:
Watermark

TODO: 
Work on drizzle
