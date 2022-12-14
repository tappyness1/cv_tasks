



| No. | image\_path (test images) | image\_height | image\_width | image\_channel | image\_format | pixel\_dtype | pixel\_max | pixel\_mean | pixel\_min |
| -- | ------------------------- | ------------- | ------------ | -------------- | ------------- | ------------ | ---------- | ----------- | ---------- |
| 0  | laptop\_jpg\_100kb.jpg    | 700           | 1050         | 3              | .jpg          | uint8        | 255        | 164.86      | 0          |
| 1  | laptop\_jpeg\_100kb.jpeg  | 700           | 1050         | 3              | .jpeg         | uint8        | 255        | 164.86      | 0          |
| 2  | laptop\_png\_500kb.png    | 566           | 850          | 3              | .png          | uint8        | 255        | 164.85      | 0          |
| 3  | 4\_png\_128kb.png         | 2000          | 2000         | 4              | .png          | uint8        | 255        | 16.77       | 0          |
| 4  | laptop\_webp\_50kb.webp   | 700           | 1050         | 3              | .webp         | uint8        | 255        | 165.01      | 0          |
| 5  | cells\_tif\_304kb.tif     | 480           | 640          | 3              | .tif          | uint8        | 254        | 76.56       | 15         |
| 6  | laptop\_tiff\_1mb.tiff    | 434           | 650          | 4              | .tiff         | uint8        | 255        | 185.41      | 0          |

Note: The shape of an image is accessed by OpenCV img.shape which returns a tuple of the image's height, width and channels (in that order if the image is color).



# Image Formats Supported by Pillow 9.1.1 and OpenCV 4.6.0-dev




| No. | Extension                          | Desc                                                | Pillow 9.1.1 | OpenCV 4.6.0-dev | Remark                         |
| --- | ---------------------------------- | --------------------------------------------------- | ------------ | ---------------- | ------------------------------ |
| 1   | .blp                               | BLP                                                 | TRUE         |                  |                                |
| 2   | .bmp                               | BMP image/bmp                                       | TRUE         | TRUE             |                                |
| 3   | .bufr                              | BUFR                                                | TRUE         |                  |                                |
| 4   | .cur                               | CUR                                                 | TRUE         |                  |                                |
| 5   | .dcx                               | DCX                                                 | TRUE         |                  |                                |
| 6   | .dds                               | DDS                                                 | TRUE         |                  |                                |
| 7   | .dib                               | DIB image/bmp                                       | TRUE         | TRUE             |                                |
| 8   | .eps, .ps                          | EPS application/postscript                          | TRUE         |                  |                                |
| 9   | .fit, .fits                        | FITS                                                | TRUE         |                  |                                |
| 10  | .flc, .fli                         | FLI                                                 | TRUE         |                  |                                |
| 11  | .ftc, .ftu                         | FTEX                                                | TRUE         |                  |                                |
| 12  | .gbr                               | GBR                                                 | TRUE         |                  |                                |
| 13  | .gif                               | GIF image/gif                                       | TRUE         |                  |                                |
| 14  | .grib                              | GRIB                                                | TRUE         |                  |                                |
| 15  | .h5, .hdf                          | HDF5                                                | TRUE         |                  |                                |
| 16  | .icns                              | ICNS image/icns                                     | TRUE         |                  |                                |
| 17  | .ico                               | ICO image/x-icon                                    | TRUE         |                  |                                |
| 18  | .im                                | IM                                                  | TRUE         |                  |                                |
| 19  | .iim                               | IPTC                                                | TRUE         |                  |                                |
| 20  | .jfif, .jpe, .jpeg, .jpg           | JPEG image/jpeg                                     | TRUE         | TRUE             | OpenCV: .jpeg, .jpg, .jpe only |
| 21  | .j2c, .j2k, .jp2, .jpc, .jpf, .jpx | JPEG2000 image/jp2                                  | TRUE         | TRUE             | OpenCV: .jp2 only              |
| 22  | \-                                 | MCIDAS                                              | TRUE         |                  |                                |
| 23  | .mpeg, .mpg                        | MPEG video/mpeg                                     | TRUE         |                  |                                |
| 24  | .msp                               | MSP                                                 | TRUE         |                  |                                |
| 25  | .pcd                               | PCD                                                 | TRUE         |                  |                                |
| 26  | .pcx                               | PCX image/x-pcx                                     | TRUE         |                  |                                |
| 27  | .pxr                               | PIXAR                                               | TRUE         |                  |                                |
| 28  | .apng, .png                        | PNG image/png                                       | TRUE         | TRUE             | OpenCV: .png only              |
| 29  | .pbm, .pgm, .pnm, .ppm             | PPM image/x-portable-anymap                         | TRUE         | TRUE             | OpenCV: also supports .pxm     |
| 30  | .psd                               | PSD image/vnd.adobe.photoshop                       | TRUE         |                  |                                |
| 31  | .bw, .rgb, .rgba, .sgi             | SGI image/sgi                                       | TRUE         |                  |                                |
| 32  | \-                                 | SPIDER                                              | TRUE         |                  |                                |
| 33  | .ras                               | SUN                                                 | TRUE         | TRUE             | OpenCV: also supports .sr      |
| 34  | .icb, .tga, .vda, .vst             | TGA image/x-tga                                     | TRUE         |                  |                                |
| 35  | .tif, .tiff                        | TIFF image/tiff                                     | TRUE         | TRUE             |                                |
| 36  | .webp                              | WEBP image/webp                                     | TRUE         | TRUE             |                                |
| 37  | .emf, .wmf                         | WMF                                                 | TRUE         |                  |                                |
| 38  | .xbm                               | XBM image/xbm                                       | TRUE         |                  |                                |
| 39  | .xpm                               | XPM image/xpm                                       | TRUE         |                  |                                |
| 40  | \-                                 | XVTHUMB                                             | TRUE         |                  |                                |
| 41  | .pfm                               | PFM files                                           |              | TRUE             |                                |
| 42  | .exr                               | OpenEXR Image files                                 |              | TRUE             |                                |
| 43  | .pic                               | Radiance HDR                                        |              | TRUE             |                                |
| 44  | \-                                 | Raster and Vector geospatial data supported by GDAL |              | TRUE             |