This is an attempt at getting the xf86 imx video driver working with X.Org R7 (the current version in buildroot).

This is a slightly modified version of the code as published by Amazon in their 5.4.3.2 source code release:

https://kindle.s3.amazonaws.com/Kindle_src_5.4.3.2_2317380003.tar.gz

The amazon-releasd imx video driver was tagged with the date 2011-04-11.

A different version is floating around online at:

https://gitorious.org/xf86-video-imx/xf86-video-imx/

but that version hasn't been updated since 2010-08-16.

For a version with no modification from the original amazon-released version (other than the addition of a README file) check out the version tagged with "amazon-release".

# xorg.conf

The driver looks for "imx" sections in xorg.conf and for each section looks for an "fbdev" option which should be set to the frame buffer device name.

Apparently DirectColor is only supported at up to 8bpp, but TrueColor is supported at higher color depths.

The frame buffer device is then opened by the driver.

# Other drivers

There seems to be another driver available here:

https://github.com/plasticlogic/mod_plepaper/blob/master/mod_plepaper_imx/epdc-imx.c

