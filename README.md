# S15-A
## Data set of 100 backgroung images of streets and roads   
https://drive.google.com/open?id=1nc1Yi_p7G7qDY8Gsl42keVgg6t-AQyGh    
Background images were downloaded and resized to 224* 224 uing GIMP
![Image](https://github.com/DrVenkataRajeshKumar/S15-A/blob/master/9.png)


## Data set of 100 foreground images of cars   
https://drive.google.com/open?id=1WFGmx-W2OBwhcEuqEANuUtc5JnRvtKA9   
car images were downloaded, backgrounds were deleted uing 3Dpaint and car images with tranparent background were created.
 *Regreted this step in later stages of creating depth images- as it created blur margins
 
 ![Image](https://github.com/DrVenkataRajeshKumar/S15-A/blob/master/97.png)




## Data set of 100 foreground masks
Tried using 3Dpaint and GIMP for creating masks of foreground images
![Image](https://github.com/DrVenkataRajeshKumar/S15-A/blob/master/masks.png)





## Data set of 400k overlay images of fg on bg (https://drive.google.com/drive/folders/1c8tO4rYzJtpDFUu5bJ0XBE9uvtl6ZWzH?usp=sharing)  
Tried different approaches for overlay of foreground on background images.  
Tried GIMP- water mark tool. managed to create 1000 images at a time.  
In search of better approach used Photoshop. Recorded actions and implemented in scripts for automation for working on multiple sets of images. Managed to create 10000 images at a time i.e. placing one foreground image at 10 different places on all background images. Problem with this approach was it took almot 1hour for creating implementations and scripts and generating 10000 images. And more frustrating part is, have to creat scripts for new foreground each and every time. That means have to work 100 hour to implement with 100 foreground images.  
Finally understood the value of coding and loop implementation. 

Started coding in colab. 
Next problem encountered was to handle large number of images generated in colab.
Used zip folder, to flush, generated images into zipfile.
Finally after several attempts able to generate 400k fgbg and fgbg_mask images in jest 1 hour 30 minutes and able to store them in zip file with-out colapsing the drive.
![Image](https://github.com/DrVenkataRajeshKumar/S15-A/blob/master/fgbg.png)


## Depth estimation of 400k overlay images   
Tried the Depth model reference given (https://github.com/ialhashim/DenseDepth/blob/master/DenseDepth.ipynb) and with few modifications able to implement nyu-h5 on the overlay bg-fg images.  
Depth predictions were not prominent. Tried other options for better predictions.
Tried KITTI ICCV (https://github.com/nianticlabs/monodepth2) and foundout better depth predictions than nyu-h5. My intusion for poor depth prediction of few fg images is (*As menctioned erlier) becaue of poor selection of foregroung images i.e with some what blur margins
![Image](https://github.com/DrVenkataRajeshKumar/S15-A/blob/master/depth.png)
