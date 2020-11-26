---
layout: post
title:  "Picture Low Polifier"
categories: project
excerpt: An app that uses image processing to transform pictures into triangular low-poly arts
---

## Getting Started
Transfer image into low poly

Run:
```MATLAB
lp_img = lowpolify(file,edge_thresh,edge_style,...
    num_vertices,ratio,min_distance, FeatureRatio)
```
to generate low poly pictures

### Some results

Original                   |  Low polified
:-------------------------:|:-------------------------:
![](/assets/images/Picture Low Polifier/corgi.jpeg)    |  ![](/assets/images/Picture Low Polifier/CORGI.jpg)
![](/assets/images/Picture Low Polifier/Di-Caprio.jpg)    |  ![](/assets/images/Picture Low Polifier/Di-cap.png)
![](/assets/images/Picture Low Polifier/wzn.jpg)    |  ![](/assets/images/Picture Low Polifier/wzn_lp.jpg)


## Steps to get Low Poly style

### Reduce noise:
    Why: Noise will affect edge detection. Since we are reducing the precision and the level of details in the image, we want the edge lines to be as clean and simple as possible.
```
    Averaging: Good for removing grain noise (bad)
    Gaussian filters
```
### Edge detection

```
    Sobel (worse than Canny)
    Canny
    Prewitt
    Roberts
    log
    zerocross (explore)
```
### Feature extraction

It is necessary to perserve the features of the original picture.

We used Harris Features detector to achieve feature extractions (As you can see in the green crosses)

### trianglization and color

We used Delaunay triangulation to form the triangle.
The color of the center pixel of each trangle is picked, the mean or mode color will not perserve the feature correctly


## Built With

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - The web framework used
* [Maven](https://maven.apache.org/) - Dependency Management
* [ROME](https://rometools.github.io/rome/) - Used to generate RSS Feeds


## GitHub repo:

You can check out the code [Here](https://github.com/YukeLiang/LowPolyHack)


