---
layout: post
title: Bài 3 - Image Classification Basics
categories : Computer-Vision
author: Nguyen Quoc Khanh
---

<br>

Image classification is a very large field of study, encompassing a wide variety of techniques –
and with the popularity of deep learning, it is continuing to grow.

Image classification and image understanding are currently (and will continue to be) the most
popular sub-field of computer vision for the next ten years. In the future, we’ll see companies
like Google, Microsoft, Baidu, and others quickly acquire successful image understanding startup
companies. We’ll see more and more consumer applications on our smartphones that can understand
and interpret the contents of an image. Even wars will likely be fought using unmanned aircrafts
that are automatically guided using computer vision algorithms.

Inside this chapter, I’ll provide a high-level overview of what image classification is, along with
the many challenges an image classification algorithm has to overcome. We’ll also review the three
different types of learning associated with image classification and machine learning.

Finally, we’ll wrap up this chapter by discussing the four steps of training a deep learning
network for image classification and how this four step pipeline compares to the traditional, hand-engineered feature extraction pipeline
# **1. What Is Image Classification?**
Image classification, at its very core, is the task of assigning a label to an image from a predefined
set of categories.

Practically, this means that our task is to analyze an input image and return a label that
categorizes the image. The label is always from a predefined set of possible categories.
For example, let’s assume that our set of possible categories includes:

<p style="text-align: center;font-weight:bold;">categories = {cat, dog, panda}</p>

Then we present the following image (Figure 4.1) to our classification system:

{% include image.html url="\images\less3\figure41.png" description="Figure 4.1: The goal of an image classification system is to take an input image and assign a label
based on a pre-defined set of categories."%}

Our goal here is to take this input image and assign a label to it from our categories set – in
this case, dog.

Our classification system could also assign multiple labels to the image via probabilities, such
as dog: 95%; cat: 4%; panda: 1%.

More formally, given our input image of *W × H* pixels with three channels, Red, Green, and
Blue, respectively, our goal is to take the *W × H × 3 = N* pixel image and figure out how to correctly
classify the contents of the image.
## **1.1. A Note on Terminology**
When performing machine learning and deep learning, we have a dataset we are trying to extract
knowledge from. Each example/item in the dataset (whether it be image data, text data, audio data,
etc.) is a data point. A dataset is therefore a collection of data points.

Our goal is to apply a machine learning and deep learning algorithms to discover underlying
patterns in the dataset, enabling us to correctly classify data points that our algorithm has not
encountered yet. Take the time now to familiarize yourself with this terminology:

1. In the context of image classification, our dataset is a collection of images.
2. Each image is, therefore, a data point.

I’ll be using the term image and data point interchangeably throughout the rest of this blog, so
keep this in mind now.
### **1.2. The Semantic Gap**
Given that all a computer sees is a big matrix of pixels, we arrive at the problem of the semantic
gap. The semantic gap is the difference between how a human perceives the contents of an image
versus how an image can be represented in a way a computer can understand the process.

How do we go about encoding all this information in a way that a computer can understand it?
The answer is to apply feature extraction to quantify the contents of an image. Feature extraction is
the process of taking an input image, applying an algorithm, and obtaining a feature vector (i.e., a
list of numbers) that quantifies our image.

To accomplish this process, we may consider applying hand-engineered features such as HOG,
LBPs, or other “traditional” approaches to image quantifying. Another method is to apply deep learning to automatically learn a set of features that can be used to
quantify and ultimately label the contents of the image itself.


### **1.3. Challenges**
# **2. Types of Learning**
# **2.1. Supervised Learning**
# **2.2. Unsupervised Learning**
# **2.3. Semi-supervised Learning**
# **3. The Deep Learning Classification Pipeline**
# **3.1. A Shift in Mindset**
# **3.2. Step #1: Gather Your Dataset**
# **3.3. Step #2: Split Your Dataset**
# **3.4. Step #3: Train Your Network**
# **3.5. Step #4: Evaluate Your Network**
# **3.6. Feature-based Learning versus Deep Learning for Image Classification**
# **3.7. What Happens When my Predictions Are Incorrect?**
# **4. Summary**