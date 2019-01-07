jpegoptim v1.2.2  Copyright (c) Timo Kokkonen, 1996,2002.
Usage: jpegoptim [options] <filenames>

  -d<path>, --dest=<path>
                  specify alternative destination directory for
                  optimized files (default is to overwrite originals)
  -f, --force     force optimization
  -h, --help      display this help and exit
  -m[0..100], --max=[0..100]
                  set maximum image quality factor (disables lossless
                  optimization mode, which is by default on)
  -n, --noaction  don't really optimize files, just print results
  -o, --overwrite overwrite target file even if it exists
  -p, --preserve  preserve file timestamps
  -q, --quiet     quiet mode
  -t, --totals    print totals after processing all files
  -v, --verbose   enable verbose mode (positively chatty)
  -V, --version   print program version

  --strip-all     strip all (Comment & Exif) markers from output file
  --strip-com     strip Comment markers from output file
  --strip-exif    strip Exif markers from output file