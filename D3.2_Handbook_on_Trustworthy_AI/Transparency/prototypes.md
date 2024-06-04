# Prototypes

*Synonyms:* Exemplars.

<!-- TODO: add resources or remove duplicate paragraph! -->

## In Brief

**Prototype-based explanation** methods return as explanation a selection of particular instances of the dataset for locally explaining the behavior of the AI system {cite}`molnar2020interpretable_50`.

## More in details

Prototypes (or exemplars) make clear to the user the reasons for the AI system’s decision. In other words, prototypes are used as a foundation of representation of a category, or a concept {cite}`frixione26`. A concept is represented through a specific instance. Prototypes help humans in constructing mental models of the black box model and of the training data used. Prototype-based explainers are generally local methods that can be used independently for tabular data, images, and text. Obviously, prototype-based explanations only make sense if an instance of the data is humanly understandable and makes sense as an explanation. Hence, these methods are particularly useful for images, short texts, and tabular data with few features.

In {cite}`bien13`, prototypes are selected as a minimal subset of samples from the training data that can serve as a condensed view of a data set. Naive approaches for selecting prototypes use the closest neighbors from the training data with respect to a predefined distance function, or the closest centroids returned by a clustering algorithm {cite}`tan2006introduction_71`. In {cite}`li2018deep_43`, authors designed a sophisticated model-specific explanation method that directly encapsulates in a deep neural network architecture an autoencoder and a special prototype layer, where each unit of that layer stores a weight vector that resembles an encoded training input. The autoencoder permits to make comparisons within the latent space and to visualize the learned prototypes such that, besides accuracy and reconstruction error, the optimization has a term that ensures that every encoded input is close to at least one prototype. Thus, the distances in the prototype layer are used for the classification such that each prediction comes with an explanation corresponding to the closest prototype. In {cite}`chen18`, prototypical parts of images are extracted by a ProtoPNet network, such that each classification is driven by prototypical aspects of a class.

Although prototypes are representative of all the data, sometimes they are not enough to provide evidence for the classification without instances that are not well represented by the set of prototypes {cite}`molnar2020interpretable_50`. These instances are named criticisms and help to explain what is not captured by prototypes. In order to aid human interpretability, in {cite}`kim2016examples_37` prototypes and criticisms are selected by means of the Maximum Mean Discrepancy (mmd): instances in highly dense areas are good prototypes, instances which are in regions that are not well explained by the prototypes are selected as criticisms. Finally, the abele method {cite}`guidotti2019latent_31` enforces the saliency map explanation with a set of exemplar and counter-exemplar images, i.e., images similar to the one under investigation classified for which the same decision is taken by the AI, and images similar to the one explained for which the black box of the AI returns a different decision. The particularity of abele is that it does not select exemplars and counter-exemplars from the training set, but it generates them synthetically exploiting an adversarial autoencoder used during the explanation process {cite}`lampridis2020explaining_40`. An example of exemplars (left) and counter-exemplars (right) is shown in Figure {numref}`{number} <fig:prototypes>.


```{figure} ./prototypes.png
---
name: fig:prototypes
width: 600px
align: center
---
Example of exemplars (left) and counter-exemplars (right) returned by <span style="font-variant:small-caps;">abele</span>. On top of each (counter-)exemplar is reported the label assigned by the black box model *b* of the AI system {cite}`Guidotti2021`.
```




## Bibliography

<!-- :style: unsrtalpha -->

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was readapted from *Guidotti, Monreale, Pedreschi, Giannotti. Principles of Explainable Artificial Intelligence. Springer International Publishing (2021)* by Francesca Pratesi.

