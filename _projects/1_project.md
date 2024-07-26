---
layout: page
title: project 1
description: Compartmental models in mathematical epidemiology
img: assets/img/12.jpg
importance: 1
category: work
related_publications: true
---


## Introduction

It will be better if we define some terminologies in epidemiology before we start modeling. Even though there are many things to consider when it comes to the concepts of epidemiology, I will give necessary definitions that are needed to understand the modeling covered in this paper. Let us start with a word from the title of the talk. What is epidemiology? Epidemiology is the study of the determinants, occurrence, and distribution of health and disease in a defined population. Note that here the terminology is used for the human population. If a defined population is animal populations, then the study is called epizootiology (or epizoology). Here, we are going to consider an epidemic; therefore, let us give a definition. According to the Cambridge Dictionary, an epidemic is the appearance of a particular disease in a large number of people at the same time (epizootic for animal populations). We will examine the mathematical modeling of infectious diseases, so there are certain words to know the meanings, allowing us to understand the assumptions made for the models.  The following meanings for words are taken from 'A Dictionary of Epidemiology' by Miquel Porta, the only dictionary I found for Epidemiology. A host is a person or other living animal, including birds and arthropods, that provides subsistence or lodgment to an infectious agent under natural conditions. A susceptible is a member of a population who is at risk of becoming infected by a disease. I think this is enough for an undergraduate mathematics student, like myself, at least to start the topic. Please note that as the cases become complex, more terminology will be needed, and if needed, I will add the necessary ones.

## Disease progression

In the reference book, it was stated the objective of a mathematical model of an infectious disease is to describe the transmission process of the disease. The transmission is the passage of a pathogen from an infectious individual to the population of susceptibles through modes of transmission, such as airborne, droplet transmission, and direct or indirect physical contact. We will observe that depending on the means of transmission, there will be changes in mathematical models. However, we now focus on the disease progression, one of the most important aspects to consider when mathematically modeling the disease.

![Figure 1: Disease Progression [Dobson, 2020].](https://github.com/abdanar/abdanar.github.io/_projects/project1_pictures/pic1.png)




The figure \ref{Fig1} clearly illustrates disease progression. There is no need to define the latent, incubation, and infectious periods, as they are clearly shown in the figure. Please note that the lengths of the latent, incubation, and infectious periods, as well as the ways they overlap, vary for different diseases. For example, the incubation period for ebola is shorter than the latent period, while for measles, the incubation period is longer than the latent period. (For detailed information, please refer to 'Epidemic Modelling – Some Notes, Maths, and Code' by Simon Dobson, if you are interested.) It is crucial to examine the progression of a specific disease because the model changes. For example, in some diseases where the incubation period is longer than the latent period, individuals remain asymptomatic, meaning they can infect others without showing any symptoms. It is essential to consider this scenario, as it significantly changes the model, a topic that will be discussed in more detail in the SEIR model.



Every project has a beautiful feature showcase page.
It's easy to include images in a flexible 3-column grid format.
Make your photos 1/3, 2/3, or full width.

To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images, even citations {% cite einstein1950meaning %}.
Say you wanted to write a bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
