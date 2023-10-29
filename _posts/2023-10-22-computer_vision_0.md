---
title: Computer Vision Notes 0
date: 2023-10-29 10:00:00 -0400
categories: [Computer Vision, Machine Learning]
tags: [introduction, vision] # TAG names should always be lowercase
---

## Introduction

General Definition: Computer Vision uses light information (ie. pictures, infared scan, etc) into meaning (ie. geometric model, natural language).

## Relation with Computer Graphics

Computer graphics is the inverse process of computer vision:
+ For computer graphics, we are given the 3D scene, for example the object model, the camera pose, and material information, and we render the corresponding 2D image.
+ For computer vision, we are only given the 2D image(s), and we need to extract information from such limited information.

![Computer Vision and Graphics](/assets/img/2023-10-22-computer_vision_0/Graphics2Vision.png){: width="300" height="400" style="border-radius:5%" .normal}

## Why is Computer Vision Hard?

Many different 3D scenes can yield the same 2D image. Therefore additional constraint/assumptions about the scene is required.
