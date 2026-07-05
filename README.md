# 3Dprinting
a quick tutorial/workflow for 3D printing with Prusa slicer and Monoprice MP10

3D printing workflow - Prusa Slicer -> Monoprice MP10

## Create (or download) 3D model: STL / STEP / 3MF file
- STL "stereo lithography" = standard file format used in 3D printing & CAD. It represents 3D surfaces as a mesh of triangles
- STEP files contain exact mathematical equations, curves, and solid volumes, allowing for infinitely smooth curves and highly accurate measurements.
- Use STEP when downloading models to customize, sharing files with engineers across different software, or sending CAD models to manufacturers.
- Use STL (or its modern equivalent, 3MF) when you are ready to send a sliced file directly to a 3D printer

## Launch Prusa Slicer

A slicer is software that converts a digital 3D model into machine-readable instructions. It cuts the 3D object into thousands of flat horizontal layers and generates the exact G-code instructions your printer needs to print the object line by line.
	
Prusa slicer tutorials: 
- https://help.prusa3d.com/article/first-print-with-prusaslicer_1753
- https://blog.prusa3d.com/slic3r-prusa-edition-beginners-guide_7527/
- https://www.youtube.com/watch?v=_kIqMPNQNSw
- https://www.youtube.com/watch?v=g144-QQt_N4


## Import STL/STEP/3MF file
	Prusa Slicer -> File/Import
      or
	Prusa Slicer/Finder -> drag file onto open Prusa Slicer window
      or
	Finder -> drag file onto Prusa Slicer icon

## Configure settings
### Plater tab

position object on plate
 - check that bottom sits flat on the build plate
   - use "Place on Face" if necessary
 - rotate, scale, cut, duplicate, paint supports or seams, add text, etc

#### Print Settings: Monoprice MP10 mini
- Filament: Hatchbox PLA
- Printer: Monoprice MP10 mini

- Supports: none (unless necessary)
- Infill: 10-15%
- Brim: yes, always!

### Print Settings tab

Layers and perimeters
			Layer height: 0.2mm (sufficient for most) - use 0.1mm for extra fine detail (and 2x print time)
			First layer height: 0.25mm (sufficient for most)

			Vertical Shells
			Perimeters: 2-4 (sufficient for most)
				this sets the minimum number of layers to print on all outside vertical surfaces
				increase perimeters for strength, watertightness, weight, etc

			Horizontal Shells
			Perimeters: 2-4 (sufficient for most)
				this sets the minimum number of layers to print on all outside horizontal surfaces
				increase perimeters for strength, watertightness, weight, etc

			Seam position: to taste...

		Infill
			Fill density: 10-15%
				this sets the amount of inner support insde the perimeter shells
			Fill pattern: Gyroid
				Gyroid preferred for faster printing and less wear on motors
				Lightning for super fast printing and minimal support

			Top fill pattern: to taste...
				mostly a matter of aesthetics, this determines the surface pattern of the top layer
			Bottom fill pattern: 
				shouldn't matter as the build plate will give texture to the bottom layer

		Skirt and brim
			Loops: 0-2 
				use this to purge old filament and get filament flowing before the actual printing starts
			
			Brim: 0-8mm
				recommended to ALWAYS print a brim!
				brim helps to adhere the print to the build plate
				brim prevents model edge warping on long/hot prints
				brim is easily removed after printing

		Support material
			Generate support material: only if neccessary. 
				Ideally -> design or position models to not require supports

			Raft: only if neccessary. 

	Print Settings tab - adjust these based on the filament specifications and experience
		Temperature
			Nozzle: 
				First layer: 210°C	Other layers: 205°C  <- I generally set the first layer 5° under maximum and subsequent layers 5° less
			Bed: 
				First layer: 60°C	Other layers: 60°C <- hotter improves adhesion? but also increase chaces of warping?

Double Check Settings

	pro move - start 3D printer preheat here

Slice now - bottom right hand corner
	double check settings
	inspect layers, brim, support, etc
	note print time - bottom right hand corner

Export G-code - bottom right hand corner
	save file with meaningful file name
		no spaces or punctuation
		nothing but letters, numbers, or underscores
		append settings and print time to end of file
			there is a way to do this programatically...
		shorter is better, long filenames get truncated on 3D printer screen
		example: TTmotorMount_1h26m.gcode 


micro SD Card
Copy G-code file to microSD card 
	use micro-> SD card adaptor
	Ensure readability
		copy another random file to the drive (SD card)
		delete that random file
		empty trash
	Eject drive (SD card)

Monoprice MP10 printer
insert microSD card into 3D printer 
	upside down!

PRINT!
	navigate to "Print"
	navigate to file
	PRINT!

WAIT
	wait for nozzle and bed to heat to temp
	wait for auto-bed leveling sequence

WATCH
	watch loop & brim printing
	ensure that nozzle distance is correct (adjust if necessary)
	ensure that lines are adhering to the bed
		if not: clean bed or adjust settings
	ensure that first layer prints well <- this is the most common failure point
	watch the first few layers print
		if all looks good, remain vigilant, but not obsessive.
	

		
	
	
	



	




