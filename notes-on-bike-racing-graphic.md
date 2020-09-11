notes-on-bike-racing-graphic.md
Last modified: Fri Sep 11, 2020  06:50PM


# Notes on bike racing graphic
--------------------------------------------------------------------------------

## Other things to consider adding:
* From reddit:
	* Other Tour de France elements that might be helpful to explain to a beginner - time trial stages - green and polka dot jersey competitions - why the overall winner is determined before the last stage
		* [You could use the Comet jersey photo of Taylor that Noway uploaded to and photoshop jerseys onto him]
	* It would be interesting to get into some of the strategy, like how teams will try to trick other riders into depleting their batteries too soon.
	* My brother explains it to non-fans this way: it's like NASCAR, boxing, and chess all together
* Think about doing a video version
	* Where you remove the text, and read it out loud instead. 
	* Use the black arrows to point to what you are talking about. 
	* This shouldn't be too hard.

## Which files are which:
* Bike-racing-draft_graphics-in-place.svg
	* Is the first-draft Inkscape file laid out vertically
* Bike-racing-draft_horizontal.svg
	* Is the second-draft Inkscape file laid out horizontally
* elements
	* Contains the graphics pieces that make up the figures in the illustrations are made from
* MTvariants
	* Contains the assembled illustrations I made using elements.


## Trying to create web-graphics version:
* Some instructions for outputting web-ready svg here:
	* http://techdatadigest.blogspot.com/2014/03/creating-svg-from-inkscape-to-use-on.html
		* This first one seems more useful
		* Note "Vacuum Defs" which this sites recommend seems to be deprecated.
		* Had to install python-lxml and scour for Inkscape to be able to save an optimized svg
		* On exporting, it complained that browsers don't know how to render flow text
			* So if you were to do this, you'd have to figure out how change all the flow text boxes to static or whatever they should be
			* Testing in firefox, it does look like it drops the flow text boxes
	* http://techdatadigest.blogspot.com/2014/03/creating-svg-from-inkscape-to-use-on.html
* While those instructions might be helpful in a different circumstance, trying to save as an svg is overthinking the problem.
	* Instead, just save it as a png, and figure out how to html to force the png to the size you want.


## Command to reduce pdf file size:
gs -dNOPAUSE -dBATCH -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/ebook -sOutputFile=output.pdf ./input.pdf
or (with filenames in place):
gs -dNOPAUSE -dBATCH -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/ebook -sOutputFile=Bike-racing-draft_horizontal_sm.pdf ./Bike-racin
g-draft_horizontal_2020update.pdf

Other -dPDFSETTINGS options are: /screen /ebook /printer and /prepress




