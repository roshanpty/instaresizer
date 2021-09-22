### Instaresizer

#### Description

Instagram only allows images between aspect ratios 16:9 (landscape) and 4:5 (portrait) to be uploaded. Images that are wider than 16:9 or taller than 4:5 are not supported by Instagram for uploads. Instaresizer is an image resizer that can be used to convert images of any aspect ratio to instagram supported aspect ratios. This resizer converts the image to optimal dimensions depending on the original image's orientation. If the image is too wide, it fills transparent pixels on top and bottom to bring the image to the supported aspect ratio of 16:9. Similarly if the image is too tall, it fills in the left and right of the image with transparent pixels to bring the aspect ratio to 4:5. 

Instaresizer supports two methods. `instasize.resize_remote()` can be used to supply an image URL whereas `instasize.resize_image()` can be used to supply a PIL image object. Both methods return resized PIL Image object which then can be saved to file system or perform other operations as necessary.

#### Usage

##### Installation

```
pip install instaresizer
```

##### Example

###### Importing the library
```
#!/usr/bin/env python3
from instaresizer import instasize
```
###### Usage - resizing remote image file supplied via a URL. 

This is useful if the image is publicly accessible with no additional authentication requirements. 
```
image_url = 'https://s3.amazonaws.com/images.seroundtable.com/30th-anniversary-of-the-world-wide-web-google-1552390014.gif'
img = instasize.resize_remote(image_url)
img.save('resized_file.png', 'PNG')
```
###### Usage - resizing local image file. 
```
image = Image.open("test_image.jpeg")
img = instasize.resize_image(image)
img.save('resized_file.png', 'PNG')
```
