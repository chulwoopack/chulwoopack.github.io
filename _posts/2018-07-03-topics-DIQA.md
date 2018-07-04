---
title: Document Image Quality Assesment (DIQA)
categories: topics
tags: featured
excerpt: Survey
---

## Introduction
Degradations may result in a significant drop in the performance of Optical Character Recognition (OCR), as well as affect the performance of document image retrieval, layout analysis and other document analysis tasks. Document image quality studies are necessary ingredients in developing restoration and enhancement algorithms. It is important to understand the various types of degradations that may effect document images and develop reliable methods for estimating levels of degradations [1].

## Challenging issues
DIQA may be performed with respect to OCR accuracy instead of human perception. Therefore methods developed for natural scene images may not be directly applied to document images. Furthermore, for the DIQA problem, non-distorted reference images are usually not available so quality assessment has to be performed in a `no-reference` fashion [1].

## Main artifacts [1]
### Stroke level
(1) Touching characters
(2) Broken characters
(3) Additive noise: small speckle close to text and irregular binarization patterns.

### Line level
(1) Touching, skewed or curved lines 
(2) Line inconsistency

### Page level
(1) Background noise: margin noise, salt-and-pepper, ruled line, clutter, show through &amp; bleed through or complex background binarization patterns.
(2) Geometric deformation: warping, curling, skew or translation.

<hr/>
## Reference
[1] Peng 2013, "Document Image Quality Assessment: A Brief Survey".