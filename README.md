## Image Optimization Utilities for Website Performance
Today everyone may find himself in need of rapidly optimzing batch of images in your website. There are useful utility libraries that can help you reduce image sizes with simple shell commands in the terminal. The following list show some of the best tools available and also recommended by Google:

### Tools and parameter tuning (Libraries available for both Windows & Linux)

<strong>gifsicle</strong> 	create and optimize GIF images<br />
<strong>jpegtran</strong> 	lossless optimize JPEG images<br />
<strong>jpegoptim</strong>  lossy optimize JPEG images<br />
<strong>optipng</strong>    lossless PNG optimization<br />
<strong>pngquant</strong> 	lossy PNG optimization<br />

### Lossless vs lossy image compression

Image is processed with a "lossless" filter that compresses the pixel data and when Image is processed with a "lossy" filter that eliminates some pixel data.

Lossy image will lose some quality like we can set quality to 85 0r 75 which will reduce size with no visual or visible difference in the image with original when seen with an human eye.

### Installing on Mac

> brew install optipng

> brew install jpegoptim

> brew install gifsicle

### Installing on Linux

> sudo apt-get install optipng

> sudo apt-get install jpegoptim

> sudo apt-get install gifsicle

### Command Line Examples:

jpegtran lib for lossles image optimization<br />
> jpegtran -copy none -optimize -progressive -outfile testimage-output.jpg testimage.jpg

jpegoptim lib for lossy image optimization<br />
> jpegoptim --strip-all --all-progressive -m85 testimage.jpg<br />
> jpegoptim --strip-all --all-progressive -m85 -S50% .\testimage1.jpg (Reduce size by 50%)

optipng for PNG<br />
> optipng -o5 testimage.png

gifsicle for PNG<br />
> gifsicle --batch -V -O3 testimage.gif

### Optimize images from shell:
Recursively optimizing images in current directory, case insensitive search of files using -iname

#### Jpegoptim
<pre>> find -type f -iname "*.jp*g" -exec jpegoptim --strip-all {} \;</pre>

#### OptiPNG
<pre>> find -type f -iname "*.png" -exec optipng -o5 {} \;</pre>

#### GifSicle
<pre>> find -type f -iname "*.gif" -exec gifsicle --batch -V -O3 {} \;</pre>

### Search & optimize images in a specific folder with relative path
<pre>> find wp-content/uploads/2019/ -type f -iname "*.jp*g" -exec jpegoptim --strip-all {} \;</pre>

### Search & optimize images in a specific folder with full path
<pre>> find /home/user/httpdocs/wp-content/uploads/2019/ -type f -iname "*.jp*g" -exec jpegoptim --strip-all {} \;</pre>


### Shell Command Aliases
Here are some aliases to keep commands nearby for fast run on the active directory images.

<pre>> alias compress_png="optipng -o5 *.png"</pre>

<pre>> alias compress_jpg="jpegoptim -m85 *.jp*g"</pre>

<pre>> alias compress_gif="gifsicle --batch -V -O3 *.gif"</pre>

### Libraries Reference Sites

https://github.com/kohler/gifsicle

https://www.lcdf.org/gifsicle/

https://github.com/tjko/jpegoptim

http://optipng.sourceforge.net/

https://github.com/XhmikosR/jpegoptim-windows

http://xhmikosr.1f0.de/tools/image-tools/

### Resize Images using ImageMagick Library
Example command below resize all images above 1920px width in a directory to 1920px width

<pre>find -type f -iname "*.jp*g" -exec convert "{}" -resize '1920>' "{}" \;</pre>

https://imagemagick.org/

#### Resizeing command line parameter options for -resize parameter:

<pre>
scale%               Height and width both scaled by specified percentage.
scale-x%xscale-y%    Height and width individually scaled by specified percentages.
                     (Only one % symbol needed.)
width                Width given, height automagically selected to preserve aspect ratio.
xheight              Height given, width automagically selected to preserve aspect ratio.
widthxheight         Maximum values of height and width given, aspect ratio preserved.
widthxheight^        Minimum values of width and height given, aspect ratio preserved.
widthxheight!        Width and height emphatically given, original aspect ratio ignored.
widthxheight>        Shrinks an image with dimension(s) larger than the corresponding
                     width and/or height argument(s).
widthxheight<        Enlarges an image with dimension(s) smaller than the corresponding
                     width and/or height argument(s).
</pre>
