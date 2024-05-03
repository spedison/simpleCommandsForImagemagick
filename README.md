# Simple commands for easy edition images in command line linux

### My First test.

  * I reduce the image at 25% and put 3 labels (called annotation by imagemagik). The original image has 2992x2992 size and ends with 748x748.

  ```(bash)
convert 20240503_101734.jpg -pointsize 250 -bordercolor blue -background white -annotate +1480+880 "Button 1" ./tmpfig.jpg ; 
convert ./tmpfig.jpg -pointsize 250 -bordercolor blue -background white -annotate +1480+1600 "Button 2"  ./tmpfig2.jpg; 
convert ./tmpfig2.jpg -pointsize 125 -annotate +1500+1100 "Button 3" -resize 25% 20240503_101734_a_25pc_com_label.jpg ; 
rm tmpfig*

```

  * I do it with simple step

  ```(bash)
convert 20240503_101734.jpg -pointsize 250  -annotate +1480+880 "Button 1"  \
                                            -annotate +1480+1600 "Button 2" \
                            -pointsize 125  -annotate +1500+1100 "Button 3" \
                            -resize 25% 20240503_101734_a_25pc_com_label.jpg ; 

```

### I do it with simple step with 2 labels with red font color and other with white color.

  ```(bash)
convert 20240503_101734.jpg  -font "Ubuntu-Mono-Bold" \
                            -pointsize 250  -fill red -annotate +1480+880 "Button 1"  \
                                            -fill red -annotate +1480+1600 "Button 2" \
                            -font "Ubuntu-Mono" \
                            -pointsize 125  -fill white -annotate +1500+1100 "Button 3" \
                            -resize 25% 20240503_101734_a_25pc_com_label.jpg ; 

```

### I do add 2 annotation and resize in other image

```(bash)

convert 20240503_101716.jpg -font "Ubuntu-Mono-Bold" \
                            -pointsize 170  -fill IndianRed1  -annotate +350+1380 "Button 5"  \
                            -pointsize 170  -fill IndianRed1  -annotate +1300+950 "Button 4" \
                            -resize 25% 20240503_101716_a_25pc_com_label.jpg

```

### List fonts in machine

```(bash)
  convert -list font
```

### List colors names

```(bash)
  convert -list color
```

### References

  * https://stackoverflow.com/questions/7183420/imagemagick-bold-and-italic-fonts
  * https://legacy.imagemagick.org/Usage/annotating/
  * https://imagemagick.org/Usage/text/#annotate_size


