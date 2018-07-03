---
title: AIDA - Page-level analysis
excerpt: Analyzing page-level characteristics of newspaper pages
categories: works
background-image: works-sample.png
tags:
  - Image processing
  - Zoning
  - Image enhancement
---

## TODO
Specifically the section "More APIs for working with images.", explore this and see if it will be possible to use the IIIF API to retrieve newspaper images, that seems like an important first step, in addition to our collectively thinking about what we will want to evaluate (and in what order).

## Introduction
### Purpose
The purpose it will be useful for is better understanding of the papers/images for improving our approaches. In addition, it will also be of interest to those who study historical newspapers, for example if we are able to something about complexity of pages across various datasets. In addition, it will also be of interest to those developing such digital collections and in literature around keeping and preserving historical newspapers.

### Starting point
We are imagining doing this study across ALL images in Chronicling America. Then we could also add the Burney Collection as a comparison. Our emphasis is not on building a generalizable tool for studying these features but rather on studying the features and analyzing them--to be able to say something useful about these collections now, as a primary focus.

### Characteristics
* Contrast (inc. illumination gradient)
* Density of text
* Complexity of layout
* Washed out images
* How noisy the image is
* Potentially (because useful for zoning): Characters clean or broken (some concern about focusing on this as a first step, because it seems like it will be very slow going, but it will be good to discuss more)
* Global skew seems like low-hanging fruit that, even if not that significant for some of our processes is something meaningful in other contexts.
* "Warpedness" of images (as opposed to skew)

### Tools
[Chronicling America Images API](https://github.com/LibraryOfCongress/data-exploration/blob/master/Accessing%20images%20for%20analysis.ipynb): Python script for building a master manifest of images and retrieving them.





