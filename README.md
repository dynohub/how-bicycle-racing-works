README.md
Last modified: 2022-12-31 16:05



# How Bicycle Racing Works
--------------------------------------------------------------------------------
Bicycle racing, particularly Grand Tours, is very complicated. But it is one of the most exciting of televised sports. To help folks get into following it, I created this graphic that explains with simple and fun graphics the basics of how it works.

## Which files are which:
* Bike-racing-draft_graphics-in-place.svg
	* Is the first-draft Inkscape file laid out vertically
* Bike-racing-draft_horizontal.svg
	* Is the second-draft Inkscape file laid out horizontally
	* Bike-racing-draft_horizontal_2020update.svg 
		* Is updated for 2020. 
	* Bike-racing-draft_horizontal_2020update_sm.pdf
		* Is a pdf reduced in size. See notes below on gs command to do this.
* elements
	* Contains the graphics pieces that make up the figures in the illustrations are made from
* MTvariants
	* Contains the assembled illustrations I made using elements.
* [notes-for-a-bike-racing-video-game](notes-for-a-bike-racing-video-game.md)

## Other things to consider adding:
* Update URL to point to grannycart.net
* From reddit:
	* Other Tour de France elements that might be helpful to explain to a beginner - time trial stages - green and polka dot jersey competitions - why the overall winner is determined before the last stage
		* [You could use the Comet jersey photo of Taylor that Noway uploaded to and photoshop jerseys onto him]
	* It would be interesting to get into some of the strategy, like how teams will try to trick other riders into depleting their batteries too soon.
	* My brother explains it to non-fans this way: it's like NASCAR, boxing, and chess all together
* Add a panel that points out that any random group of riders becomes a self-sufficient machine:
	* the more riders, the more powerful the machine is because they can keep swapping someone to the front while others take a break
	* so a big group of riders becomes a more powerful machine working together to "chase down" a smaller group.
	* more weaker riders can overpower a few strong riders like this.
	* (This is such a strong idea, it might need its own graphic, borrowing the drafting panel as a starting place)
* Bike racing is basically the same thing as Deadliest Catch:
	* Both put people in survival situations as a generative way create stories.
	* (Some other sports do this to: football, for instance --- though in that case the greatest generative story might end up being the negative health impacts bringing an end to the popularity of the sport. Other sports focus more on astonishing feats of athleticism --- neat to see, but not as interesting as a story of triumph.)
* Think about doing a video version
	* Remove the text, and read it out loud instead. 
	* Use the black arrows to point to what is being talking about. 
	* This shouldn't be too hard!
	* For a video version, switch to git lfs (large file storage)
* Consider redoing it in a clean all-vector style with Futura type
	* People might like that more



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







