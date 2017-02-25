*******
Colorz
*******

Complex domain coloring

.. image:: https://raw.githubusercontent.com/wiki/hashimoton/colorz/images/z.png

Colorz is a fun tool that generates `domain coloring`_ for the given function of a complex variable z.

.. _domain coloring: https://en.wikipedia.org/wiki/Domain_coloring


In other words, colorz is yet another implementation of:

* http://www.jedsoft.org/fun/complex/
* http://mathematica.stackexchange.com/questions/7275/how-can-i-generate-this-domain-coloring-plot


============
Requirements
============

* Ruby 2.2 or greater
* RubyGems: ChunkyPNG_ , rgb_

.. _ChunkyPNG: https://github.com/wvanbergen/chunky_png
.. _rgb: https://github.com/plashchynski/rgb

========
Setup
========

1. Copy colorz into your convenient directory.

  - Windows users need to copy colorz.bat into the same directory.
  - \*nix users may need executable permission (chmod +x colorz). 
  
2. Include the directory in PATH.


========
Usage
========

The First Result
-----------------

Try below::
  
  $ colorz

After a few seconds, the command prints a full path to the generated PNG file and ends.

::
  
  $ colorz
  /working/dir/colorz.png
  $


The generated colorz.png is a domain coloring result of f(z) = z, where z covers from -4-4i to 4+4i.

.. image:: https://raw.githubusercontent.com/wiki/hashimoton/colorz/images/colorz.png

The color in a point represents the result value of f(z) at the corresponding point on the complex plane.
The hue represents the phase, as many other domain coloring methods do.
A white(bright) point means the magnitude is quite near one of 2^n (n: integer including negative numbers).
A black(dark) point means either the real part or the imaginary part is an integer.


Another One
------------

Try the sine function::
  
  $ colorz "sin(z)"

.. image:: https://raw.githubusercontent.com/wiki/hashimoton/colorz/images/sin_z.png


More examples are in gallery_.

.. _gallery: https://colorz-g.tumblr.com/

Options
-------------

::
  
  $ colorz -h
  Complex domain coloring
  Usage: colorz [options] FUNCTION
  
  Options:
      -d, --domain=MIN,MAX             coloring domain (e.g. -d=-2-2i,+2+2i)
      -i, --input-file=INPUT_FILE      file path of ruby script for a complex function
      -o, --output-file=OUTPUT_FILE    file path of output image
      -s, --size=WxH                   size(width=W, height=H) of the output image
      -t, --tile                       the right/bottom edge shows slightly inner values than the maximum
  
  FUNCTION:
  Ruby snipet that returns a value with a given parameter "z"


=======
Tips
=======


Get More Beautiful Image 
------------------------------

Plot twice as large as the target size.
When you want a 400x400 image of f(z) = 1/z for example::

  $ colorz -s 800x800 -o inv2.png "1/z"

Then shrink the image to the target size.
If you have ImageMagick, convert command can do that::

  $ convert -geometry 400x400 inv2.png inv.png


Don't define constant in your function
----------------------------------------

Otherwise you will see a flood of warnings "warning: already initialized constant..."



=============
Disclaimer
=============

On this tool, I prefer visual sweetness rather than the mathematical correctness.

.. EOF
