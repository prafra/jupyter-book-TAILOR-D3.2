# Saliency Maps

## In brief

Saliency maps are explanations used on image classification tasks. A **saliency map** is an image where each pixel's color represents a value modeling the importance of that pixel in the original image (i.e., the one given in input to the explainer) for the prediction.

## More in detail

The most used type of explanation for explaining AI systems working on images consists of **saliency maps**. A saliency map is an image where each pixel's color represents a value modeling the importance of that pixel for the prediction, i.e., they show the positive (or negative) contribution of each pixel to the black box
outcome. Saliency maps are a very typical example of [local explanation methods](./global_local.md) since they are tailored to the image that must be explained. 

In the literature, there exist different explanation methods locally explaining deep neural networks for image classification. The two most used model-specific techniques are *perturbation-based attribution methods* {cite}`fong23,zeiler2014visualizing_77` and
*gradient attribution methods* such as <span style="font-variant:small-caps;">sal</span> {cite}`simonyan2013deep_67`, <span style="font-variant:small-caps;">elrp</span> {cite}`bach9`, <span style="font-variant:small-caps;">grad</span> {cite}`shrikumar2016not_66`, and <span style="font-variant:small-caps;">intg</span> {cite}`sundararajan2017axiomatic_69`. 

Without entering into the details, these XAI approaches aim at attributing an importance score to each pixel in order to minimize the probability of the deep neural network (DNN) labeling the image with a different outcome when only the most important pixels are considered. Indeed, the areas retrieved by these methods are also called *attention areas*.

The aforementioned XAI methods are specifically designed for specific DNN models, i.e., they are [model-specific](./model_specific.md). 

However, relying on appropriate image transformations that take advantage of the concept of "superpixels" {cite}`ribeiro`, i.e., the results of the segmentation of an image into regions by considering proximity or similarity measures, also [model-agnostic explanation](./model_spedific.md) methods (such as <span style="font-variant:small-caps;">lime</span> {cite}`ribeiro`, <span style="font-variant:small-caps;">anchor</span> {cite}`ribeiro2018anchors_59`, and <span style="font-variant:small-caps;">lore</span> {cite}`guidotti_lore`) can be employed to explain AI working on images for any kind of black box model. 

The attention areas of explanations returned by these methods are strictly dependent on both:
- the technique used for segmenting the image to explain and
- to a neighborhood consisting of unrealistic synthetic images with "suppressed"
superpixels {cite}`guidotti2019investigating_29`.

A different approach for generating neighborhoods is introduced by the [local](./global_local.md) [model-agostic](./model_specific.md) explanation method
<span style="font-variant:small-caps;">abele</span> {cite}`guidotti2019latent_31`. This method relies on a generative model, i.e., an adversarial autoencoder {cite}`makhzani2015adversarial_46`, to produce a realistic synthetic neighborhood that allows retrieving more understandable saliency maps. 
Indeed, saliency maps returned by <span style="font-variant:small-caps;">abele</span> highlight the contiguous attention
areas that can be varied while maintaining the same classification from the black
box used by the AI system. 

Fig. {numref}`{number} <xai-saliency>` reports a comparison of saliency maps for
the classification of the handwritten digits "9" and "0" for the explanation methods
<span style="font-variant:small-caps;">abele</span> {cite}`guidotti2019factual_30,guidotti2019latent_31`, <span style="font-variant:small-caps;">lime</span> {cite}`ribeiro`, <span style="font-variant:small-caps;">sal</span> {cite}`simonyan2013deep_67`, <span style="font-variant:small-caps;">elrp</span> {cite}`bach9`, <span style="font-variant:small-caps;">grad</span> {cite}`shrikumar2016not_66`, and <span style="font-variant:small-caps;">intg</span> {cite}`sundararajan2017axiomatic_69`.

```{figure} ./saliency.png
---
name: xai-saliency
width: 600px
align: center
---
Example of saliency maps returned by different explanation methods. The first column contains the image analyzed and the label assigned by the black box model *b* of the AI system. {cite}`Guidotti2021`.
```

## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

---
 
 
This entry was readapted from *Guidotti, Monreale, Pedreschi, Giannotti. Principles of Explainable Artificial Intelligence. Springer International Publishing (2021)* by Francesca Pratesi and Riccardo Guidotti.
