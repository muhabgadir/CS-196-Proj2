## Fun With Filters and Frequencies!

Author: Muhab Abdelgadir
 | UC Berkeley
 | CS 194-26


For this project, we are intended to understand the information that is embedded in each image. Therefore, we learn to manipulate this information in order to contort the image in some form. Overall, we utilize derivative filters, and Gaussian kernels to produce our results. 


### 1.1 Finite Difference Operator

Given in the project's specs, we utilize humble difference operators to manipulate the cameraman picture. These operators take in pixel value in relation to a previous pixel. 

![bears](https://preview.redd.it/e4rxex4f9fp51.jpg?width=512&format=pjpg&auto=webp&s=c2e9187441def9fe14c17a2620ab272219ee988a)

![bears](https://preview.redd.it/oive7l5f9fp51.jpg?width=513&format=pjpg&auto=webp&s=ad27f1de2dd93bfc11b10ce6a36e2a0eeb9b17f3)

This transformation creates a border image that contains a lot of noise within its contents, therefore we must remove it. 

### 1.2 Derivative of Gaussian (DoG) Filter

We want to remove the noise from the previous image, therefore we apply a Gaussian filter: 

![bears](https://i.redd.it/lh0pkilhafp51.jpg)

As one can see, the noise within the image is gone, and the borders become smoothed. This is due to the Gaussian filter removing higher frequencies that create noise in details of the image. 

### 1.3 Image Straightening

In order to straighten an image, one can utilize a derivative map to locate angles perpendicular to the axes. Therefore, once there is a count of perpendicular axes, we can deduce angles that maximize them. We must crop borders in order to process the contents of the images when doing this, consequently. 

![bears](https://preview.redd.it/we1l1dn3efp51.jpg?width=3799&format=pjpg&auto=webp&s=c40cb9723a70f3d0d613f1032278000e272b3b2e)
![bears](https://preview.redd.it/p44wmbn3efp51.jpg?width=3896&format=pjpg&auto=webp&s=a4ed5782d1f68c46ddfc2ce13f79321c2371f49a)
![bears](https://preview.redd.it/3dbh6bn3efp51.png?width=640&format=png&auto=webp&s=cec7d67560c4c3097d6058409b0e57c94d2bc0d8)
![bears](https://preview.redd.it/iiuh1drodfp51.jpg?width=678&format=pjpg&auto=webp&s=4bdb7056b26bab2072e665bb0281a5d95f951b87)
![bears](https://preview.redd.it/z2ka2brodfp51.jpg?width=764&format=pjpg&auto=webp&s=b02a2d750283642e35128500cbee71d4a0fab848)
![bears](https://preview.redd.it/7jqw3drodfp51.png?width=640&format=png&auto=webp&s=fa8d92bf68b2a51ae0ac2f7b98719f123177c5f8)
![bears](https://preview.redd.it/r7u21kemefp51.jpg?width=259&format=pjpg&auto=webp&s=4edb05b26be0efa9b28090ea99e7278f0e92bccf)
![bears](https://preview.redd.it/u9ks5jemefp51.jpg?width=324&format=pjpg&auto=webp&s=dee757285752a32ab6246f896479c25816010531)
![bears](https://preview.redd.it/jiz3gjemefp51.png?width=640&format=png&auto=webp&s=5a771fae17c38ed6a73a2da83103706898b93e9b)
![bears](https://preview.redd.it/nqhfpjrsefp51.jpg?width=976&format=pjpg&auto=webp&s=2c70c3faa1e3c09dedb120ee9dd0342c2946f04b)
![bears](https://preview.redd.it/q413ahrsefp51.jpg?width=1162&format=pjpg&auto=webp&s=f2ff6c8937349676a2491fea4d08949dab371259)
![bears](https://preview.redd.it/zb9wijrsefp51.png?width=640&format=png&auto=webp&s=afb9e58a9ebb9b3674db17115581661c8f1a0aed)
![bears](https://preview.redd.it/s6lbaq33ffp51.jpg?width=730&format=pjpg&auto=webp&s=51140783b705898bcfe2eb71272aed9fa61adcec)
![bears](https://preview.redd.it/20e3ko33ffp51.jpg?width=865&format=pjpg&auto=webp&s=7756a4b248f8e0b30d1fb0e177599d65e4ae989e)
![bears](https://preview.redd.it/ngv9mp33ffp51.png?width=640&format=png&auto=webp&s=4bf7f81ca1c75e1461c4a257707e37317f94a1dc)


This algorithm is very straightforward, as almost all the results are straightened. In images that are fairly large, the straightened image for almost all the results, there are less perpendicular values than regular values, as apparent in the histograms, such as facade.jpg. This is because when we calculate the horizontal and vertical axes, we crop borders. 

### 2.1 Image Sharpening

In order to sharpen images, we calculate lower frequencies to find high frequencies, and add them to the image. We do this by creating Laplacians of Gaussian kernels:

![bears](https://preview.redd.it/1mbfcijegfp51.jpg?width=300&format=pjpg&auto=webp&s=72f3606389cd50e606ff0c869d1aa7b4bd77a809)
![bears](https://preview.redd.it/sodneniegfp51.jpg?width=300&format=pjpg&auto=webp&s=2d04bec027b29bd8a878c6fdc6b531d492ac1540)
![bears](https://preview.redd.it/24e99oiegfp51.jpg?width=730&format=pjpg&auto=webp&s=19aa30d560b9ccf27a1bc96c6ee3c7665f8d8c53)
![bears](https://preview.redd.it/p65jmoiegfp51.jpg?width=730&format=pjpg&auto=webp&s=15c2704ad4a13dd195ec1c1bb30f4e2a28dc9295)
![bears](https://preview.redd.it/elb0nniegfp51.jpg?width=500&format=pjpg&auto=webp&s=db5a89f6b6da6db744ad385d086396b863a9379d)
![bears](https://preview.redd.it/cyq4uniegfp51.jpg?width=500&format=pjpg&auto=webp&s=5f932a5b48681bcbdb4319f312e33ef29ea35b23)
![bears](https://preview.redd.it/2nbp6oiegfp51.jpg?width=500&format=pjpg&auto=webp&s=f2212f60c94f75763a9c925b3505306681d90bfc)
![bears](https://preview.redd.it/goe2oniegfp51.jpg?width=500&format=pjpg&auto=webp&s=27fcb468100a0f8a0fb5bde73a85dae5f3202347)
![bears](https://preview.redd.it/8umxmmiegfp51.jpg?width=500&format=pjpg&auto=webp&s=67f2cb2af1c701cfeb7202953bd9a2c388f05893)

It is apparent that the images simply only have less color, and this is due to images being normalized as saved, and since they have larger absolute values, the lower frequency values are normalized to smaller intervals. Also, since we sharpened the wave image multiple times, we simply only see borders now. 

### 2.2 Hybrid Images

To create hybrids, we must align pictures and add one's low frequencies with other high frequencies. 

![bears](https://preview.redd.it/lbykg28xhfp51.jpg?width=745&format=pjpg&auto=webp&s=b1193eef0e6a3e4fcf977dea44dd2f391928d56c)
![bears](https://preview.redd.it/3n4v2y7xhfp51.jpg?width=640&format=pjpg&auto=webp&s=8dd965c2f40b0d9d258715d402ff64b68234a864)
![bears](https://preview.redd.it/dlkmnz7xhfp51.jpg?width=1402&format=pjpg&auto=webp&s=5ab574e352c2b842a7719caeee628561487f1625)
![bears](https://preview.redd.it/6edb2y7xhfp51.jpg?width=552&format=pjpg&auto=webp&s=a7d9c394521c18d5bf866cf039faf11b8d121045)

### 2.2 Hybrid COLOR Image

A quick trial using color proved successful, however, errored out for every other picture besides this:

![bears](https://preview.redd.it/rz28dy7xhfp51.jpg?width=745&format=pjpg&auto=webp&s=9dfaea5dd183c3938509f935b4227eebb7f8208f)

### 2.3 Gaussian and Laplacian Stacks

After utilizing the Gaussian filters, we can create stacks as shown in the lecture. The Gaussian stack from the first filtered image the level 6 filtered image and the Laplacian stack go from the first Gaussian filtered image to the difference on the bottom of the Gaussian stack images. (TOP -> BOTTOM)

![bears](https://preview.redd.it/6m6q8eddjfp51.jpg?width=2340&format=pjpg&auto=webp&s=caa042b4a1de8325f65bdc2c632d7eb6e84b797b)
![bears](https://preview.redd.it/rhejhdddjfp51.jpg?width=2340&format=pjpg&auto=webp&s=690611e928bd96add902970806e404e94dfa6941)
![bears](https://preview.redd.it/4wa4udddjfp51.jpg?width=390&format=pjpg&auto=webp&s=4f64c784614fd033d88b4a00d008971311ea5395)
![bears](https://preview.redd.it/a60gpznqjfp51.jpg?width=3312&format=pjpg&auto=webp&s=c3cab0444d48bf5f489e9221dedd1346310bce58)
![bears](https://preview.redd.it/iuz080oqjfp51.jpg?width=3312&format=pjpg&auto=webp&s=2129776aaf43f893fe09975ebfedab4ce0b2cfba)
![bears](https://preview.redd.it/wl6kiynqjfp51.jpg?width=552&format=pjpg&auto=webp&s=7cf461afca6cb248914e2319341d57702b29d568)
![bears](https://preview.redd.it/ibx9nzayjfp51.jpg?width=4470&format=pjpg&auto=webp&s=be319f85548f4c613368fbd8530131a627254187)
![bears](https://preview.redd.it/vfek6abyjfp51.jpg?width=4470&format=pjpg&auto=webp&s=2d57a14126fd581ce17cd9229cbc72bb9f278940)
![bears](https://preview.redd.it/wpumt2byjfp51.jpg?width=745&format=pjpg&auto=webp&s=ec1a4d7abd0aba68a82b1e8201e5010020b2f0fb)

These filters and stacks demonstrate what image is more predominantly seen through Gaussian Stacks and Laplacian stacks. 

### 2.4 Multiresolution Blending

Given two images and a mask, we join these images in Laplacian levels using Low Pass filtered masks. I utilized Photoshop to create these masks to help my model. 

![bears](https://preview.redd.it/jaz3u6z1mfp51.jpg?width=300&format=pjpg&auto=webp&s=0777e44d266fe23994d0767ddd974d0c52ab90cf)
![bears](https://preview.redd.it/0fb8lqytmfp51.jpg?width=300&format=pjpg&auto=webp&s=d379fd592cf50e0a40f75853cf79cd22f2346ed4)
![bears](https://preview.redd.it/3tf9s6fumfp51.jpg?width=300&format=pjpg&auto=webp&s=4a197e112fa16f619aad7726bb83ecc74a9a2554)
![bears](https://preview.redd.it/4l3bx6z1mfp51.jpg?width=300&format=pjpg&auto=webp&s=f6bd4aa7f2751e9ea577de403065192b6a329eba)
![bears](https://preview.redd.it/tt1lw7hanfp51.jpg?width=300&format=pjpg&auto=webp&s=cee6624749f0da36d4e2b018bdf9f4f07c1b439a)
![bears](https://preview.redd.it/4swk2yzanfp51.jpg?width=300&format=pjpg&auto=webp&s=04f56aa62e4d3877ce78f41feeba232459f31c65)
![bears](https://preview.redd.it/rta237z1mfp51.jpg?width=300&format=pjpg&auto=webp&s=e708e9e29d09c8cae20b62a1a7f5a7c54ab5e599)
![bears](https://preview.redd.it/7m4zhbzbnfp51.jpg?width=300&format=pjpg&auto=webp&s=b7f689f60fb7b2825a739c123b08b2a93752be02)
![bears](https://preview.redd.it/32ei3zcbnfp51.jpg?width=300&format=pjpg&auto=webp&s=2f72ac36c5a188e1307b7263a74bf75339720d99)
![bears](https://preview.redd.it/c2d5p6z1mfp51.jpg?width=300&format=pjpg&auto=webp&s=2894717bd21a42f7cf781c88813933ad2b99da4a)

### WITH COLOR:

![bears](https://preview.redd.it/nb7942r2mfp51.jpg?width=300&format=pjpg&auto=webp&s=102aa860ff6b674cc43f9a8d07682462c507ee6e)
![bears](https://preview.redd.it/gu8ec5r2mfp51.jpg?width=300&format=pjpg&auto=webp&s=e1da498365145d6f94554a06c654a12288190e3f)
![bears](https://preview.redd.it/eabi35r2mfp51.jpg?width=300&format=pjpg&auto=webp&s=2b75aa8d6b7adcafea29a24e24bb8bc7768d9fc8)

### UNIQUE MASKS:
![bears](https://preview.redd.it/rw5u0x5wnfp51.jpg?width=300&format=pjpg&auto=webp&s=c47b5efa9fe5fc1dc455ac7a57d708e902051e5e)
![bears](https://preview.redd.it/hukimy5wnfp51.jpg?width=300&format=pjpg&auto=webp&s=856e95d5b9e8a1f98cbcff24738d84c35d38c7d9)
![bears](https://preview.redd.it/rkiwjy5wnfp51.jpg?width=300&format=pjpg&auto=webp&s=14722856ff868ef264bd5e6353c87bed10abd953)
![bears](https://preview.redd.it/661g5x5wnfp51.jpg?width=300&format=pjpg&auto=webp&s=7fb993ce9cd266d8c8ff20d4517cbb581109475b)


![bears](https://preview.redd.it/g4y1deg9ofp51.jpg?width=300&format=pjpg&auto=webp&s=0129e3bcd6bf383e66ec0d273ddac9a140318988)
![bears](https://preview.redd.it/nynw3ig9ofp51.jpg?width=300&format=pjpg&auto=webp&s=861513cf9d24bd47c0e7233f6da9f72097a2fa95)
![bears](https://preview.redd.it/dirmdjg9ofp51.jpg?width=300&format=pjpg&auto=webp&s=67a6f2310bb329ec567e65a13d55829c322e52c1)
![bears](https://preview.redd.it/r3o3khg9ofp51.jpg?width=300&format=pjpg&auto=webp&s=58c2ced893afd04007ff886f0ee472ce13c49a29)

### Interesting Project Parts

This project had various aspects that one could explore. Using our concepts of image frequencies and signals, we are able to manipulate them to create something that looks very different from the original image. Specifically, I thought Hybrid images and Multiresolution blending were the most interesting aspects because I had the most success and coolest looking images with them. 
