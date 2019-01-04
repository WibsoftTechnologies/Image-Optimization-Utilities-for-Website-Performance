## Image-Optimization-Utilities-for-Website-Performance
Today everyone may find himself in need of rapidly optimzing batch of images in your website. There are useful utility libraries that can help you reduce image sizes with simple shell commands in the terminal. The following list show some of the best tools available and also recommended by Google:

### Tools and parameter tuning (Libraries available for both Windows & Linux)

<strong>gifsicle</strong> 	create and optimize GIF images<br />
<strong>jpegtran</strong> 	lossless optimize JPEG images<br />
<strong>jpegoptim</strong>       lossy optimize JPEG images<br />
<strong>optipng</strong> 	lossless PNG optimization<br />
<strong>pngquant</strong> 	lossy PNG optimization<br />

### Lossless vs lossy image compression

Image is processed with a "lossless" filter that compresses the pixel data and when Image is processed with a "lossy" filter that eliminates some pixel data.

Lossy image will lose some quality like we can set quality to 85 0r 75 which will reduce size with no visual or visible difference in the image with original when seen with an human eye.

### Installing on Mac

brew install optipng<br />
brew install jpegoptim<br />
brew install gifsicle<br />

### Installing on Linux

sudo apt-get install optipng<br />
sudo apt-get install jpegoptim<br />
sudo apt-get install gifsicle<br />

### Command Line Examples:

> jpegtran lib for lossles image optimization<br />
jpegtran -copy none -optimize -progressive -outfile testimage-output.jpg testimage.jpg

> jpegoptim lib for lossy image optimization<br />
jpegoptim --strip-all -m 90 testimage.jpg

> optipng for PNG<br />
optipng -o7 testimage.png

> gifsicle for PNG<br />
gifsicle --batch -V -O2 testimage.gif

### Optimize images from shell:
Recursively optimizing images in current directory, case insensitive search of files using -iname

### Jpegoptim
find -type f -iname "*.jp*g" -exec jpegoptim --strip-all {} \;

### OptiPNG
find -type f -iname "*.png" -exec optipng -o7 {} \;

#### GifSicle
find -type f -iname "*.gif" -exec gifsicle --batch -V -O2 {} \;

### Example to search a specific folder with relative path
find 07/ -type f -iname "*.jp*g" -exec jpegoptim --strip-all {} \;

### Example to search a specific folder with full path
find /var/www/vhosts/website.com/httpdocs/wp-content/uploads/2019 -type f -iname "*.jp*g" -exec jpegoptim --strip-all {} \;


### Shell Command Aliases
Here are some aliases to keep commands nearby for fast run on the active directory images.

alias compress_png="optipng -o7 *.png"<br />
alias compress_jpg="jpegoptim -m80 *.jpg"<br />
alias compress_gif="gifsicle --batch -V -O2 *.gif"<br />
