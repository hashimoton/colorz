*******
Colorz
*******

Complex domain coloring

.. image:: https://raw.githubusercontent.com/wiki/hashimoton/colorz/images/z.png

=============
Introduction
=============

Complex domain coloring (or "Domain Coloring") a color map of functions of a complex variable.


========
Setup
========

1. Copy colorz into your convenient directory.

  - Windows users need to copy colorz.bat into the same directory.
  - *nix users may need to give executable permission (chmod +x colorz). 
  
2. Add the directory into PATH environment.

========
Usage
========

::
  
  $ colorz -h
  Complex domain coloring
  Usage: colorz [options] FUNCTION
  
  Options:
      -i, --input-file=INPUT_FILE      file path of ruby script for a complex function
      -o, --output-file=OUTPUT_FILE    file path of output image
      -r, --range=MIN,MAX              coloring range (e.g. -r=-2-2i,+2+2i)
      -s, --size=WxH                   size(width=W, height=H) of the output image
      -t, --tile                       the right/bottom edge shows slightly inner values than the maximum

