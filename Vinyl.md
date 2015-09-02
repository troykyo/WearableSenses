#Vinyl cutting from OSX
Gcc Expert no longer supports software for the Expert 24" cutter, but thankfully fabmodules from the [Fab Academy](http://www.fabacademy.org/) does.  I am working on a Windows solution.  If you are working on a Unix system follow the instructions on installing [InkCut](http://inkcut.sourceforge.net/). Special thanks to FabModules manager Fiore Basile for helping me solve this one.  

##Setup:
You'll need to enable a Raw CUPS printer to send the design to the cutter.  First we will need to enable the web interface of CUPS.  Open Terminal (/Applications/Utilities/Termnial.app) and type

cupsctl WebInterface=yes

This will enable the web interface that we can now browse by going to [CUPS 2.0.2](http://127.0.0.1:631) or by typing http://127.0.0.1:631.   If it askes for a user name and password use the current user login.

Next, Click on [Administration](http://127.0.0.1:631/admin) and add a printer.  

With the USB cable attached to the computer you should see **unknown**  or **unnamed printer** under Local Printers.  If unsure unplug the printer and refresh the website.   This is the Expert Vinyl Cutter.

Name it vinyl and add the lab name if you like.
When asked for drivers say Raw and Raw.

Reboot your machine.  

From the Terminal type 
  *lpstat -p -d*
you should see your printer listed here. 

or point your browser to [Printers - CUPS 2.0.0](http://localhost:631/printers/)

##Creating your file

[Fab Modules](http://fabmodules.org/) is the website created by Neil Gershenfeld and Fiore Basile for the FabAcademy course on Digital Fabrication.  

1. Click on Input Format and select the format of the file (.svg or .png usually)
2. Select Roland vinyl (.camm) as your **output format**
3.  Select cut vinyl as your **process**
4. in the right hand column click **calculate**
5. Press **save** and save it to your local machine

Tip: If the quality is low raise the dpi (I like 600 dpi) of your original and try again.

##Cutting

Load your material and adjust the feet to make sure it will grip the entire piece with cutting.  Remember that the cutter starts from the front right of the piece.
Run a test cut by removing the cutting blade and running the file to make sure all is well (this will save tons of waste material.)

From the command line navigate the folder, usually *cd Downloads/*
The syntax to print is 
  lp -d *printer name* *filename*
so in this case we send the command 
  *lp -d vinyl lilians.camm*



1. Make sure the Vinyl Cutter is ready to print 
2. Navigate to [Jobs - CUPS 2.0.0](http://localhost:631/jobs?which_jobs=all) and **Reprint Job** (On my mac I always have to do this the very first time and then it runs well)
3. Make sure you know the orientation of your print. Mine rotates 90 degrees.  Anything wider than 60cm will not print. 
4. Go back to [Fab Modules](http://fabmodules.org/) and regenerate the files. (I have to do this nearly every time.)

Thanks to:
Fiore Basile for maintaining [Fab Modules](http://fabmodules.org/) and helping personally to make Fab Modules work for the Expert 24".
[Raw Printing For Mac OSX | PrintNode](https://www.printnode.com/docs/raw-printing-for-osx/) for the detailed instruction on Raw Printers.  They have a Windows page as well if anyone wants to try and make this work on the other side.  
