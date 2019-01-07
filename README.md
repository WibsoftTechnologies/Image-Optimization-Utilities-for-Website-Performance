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
> find -type f -iname "\*.jp\*g" -exec jpegoptim --strip-all {} \;

#### OptiPNG
> find -type f -iname "\*.png" -exec optipng -o5 {} \;

#### GifSicle
> find -type f -iname "\*.gif" -exec gifsicle --batch -V -O3 {} \;

### Search & optimize images in a specific folder with relative path
> find wp-content/uploads/2019/ -type f -iname "\*.jp\*g" -exec jpegoptim --strip-all {} \;

### Search & optimize images in a specific folder with full path
> find /home/user/httpdocs/wp-content/uploads/2019/ -type f -iname "\*.jp\*g" -exec jpegoptim --strip-all {} \;


### Shell Command Aliases
Here are some aliases to keep commands nearby for fast run on the active directory images.

> alias compress_png="optipng -o5 \*.png"

> alias compress_jpg="jpegoptim -m85 \*.jp\*g"

> alias compress_gif="gifsicle --batch -V -O3 \*.gif"

### Libraries Reference Sites

https://github.com/kohler/gifsicle

https://www.lcdf.org/gifsicle/

https://github.com/tjko/jpegoptim

http://optipng.sourceforge.net/

https://github.com/XhmikosR/jpegoptim-windows
