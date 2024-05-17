# Adversarial Attack

*Synonyms*: Adversarial Input, Adversarial Example.

## In brief

An **adversarial input** is any perturbation of
the input features or observations of a system (sometimes imperceptible
to both humans and the own system) that makes the system fail or take
the system to a dangerous state. A prototypical case of an adversarial
situation happens with machine learning models, when an external
agent maliciously modify input data --often in imperceptible ways--
to induce them into misclassification or incorrect prediction. For
instance, by undetectably altering a few pixels on a picture, an
adversarial attacker can mislead a model into generating an incorrect
output (like identifying a panda as a gibbon or a 'stop' sign as a
'speed limit' sign) with an extremely high confidence. While a good
amount of attention has been paid to the risks that adversarial attacks
pose in deep learning applications like computer vision, these kinds of
perturbations are also effective across a vast range of machine learning
techniques and uses such as spam filtering and malware detection. A
different but related type of adversarial attack is called {doc}`data_poisoning`, but this involves a malicious
compromise of data sources (used for training or testing) at the point
of collection and pre-processing.


## More in detail

The vulnerabilities of AI systems to adversarial examples have
serious consequences for AI safety. The existence of cases where subtle
but targeted perturbations cause models to be misled into gross
miscalculation and incorrect decisions have potentially serious safety
implication for the adoption of critical systems like applications in
autonomous transportation, medical imaging, and security and
surveillance.

To get an idea of what adversarial examples look like, consider the
example in Fig. {numref}`{number} <fig:AdvEx>`  shown in {cite}`goodfellow2014explaining`: starting
with an image of a panda from ImageNet  {cite}`russakovsky2015imagenet`, the
attacker adds a imperceptibly perturbation (i.e., an small vector whose
elements are equal to the sign of the elements of the gradient of the
cost function with respect to the input), to make the image be
recognised as a gibbon with high confidence by a particular deep neural
net (GoogLeNet  {cite}`szegedy2015going`). Also, recent research has shown
that even in physical world scenarios, machine learning systems are
vulnerable to adversarial examples:  {cite}`kurakin2018adversarial` shows how
printed adversarial images (with modifications imperceptible to the
human eye) obtained from a cell-phone camera are not correctly
classified by the models. In general, adversarial examples have the
potential to be dangerous. For example, attackers could target
autonomous vehicles by using stickers or paint to create an adversarial
stop sign that the vehicle would interpret as a 'yield' or other sign,
as discussed in  {cite}`papernot2017practical`.

```{figure} ./adversarial_img_1.png
---
name: fig:AdvEx
width: 600px
align: center
---
An adversarial input, overlaid on a typical image, can cause a
classifier to miscategorise a panda as a gibbon. Adapted from  {cite}`goodfellow2014explaining`.
```

In response to concerns about the threats posed to a safe and trusted
environment for AI technologies by adversarial attacks a field called
adversarial machine learning has emerged over the past several years.
Work in this area focuses on securing systems from disruptive
perturbations at all points of vulnerability across the AI pipeline. One
of the major safety strategies that has arisen from this research is an
approach called model hardening, which has advanced techniques that
combat adversarial attacks by strengthening the architectural components
of the systems. Model hardening techniques may include adversarial
training, where training data is methodically enlarged to include
adversarial examples. Other model hardening methods involve
architectural modification, regularisation, and data pre-processing
manipulation. A second notable safety strategy is runtime detection,
where the system is augmented with a discovery apparatus that can
identify and trace in real-time the existence of adversarial examples. A
valuable collection of resources to combat adversarial attack can be
found at <a href="https://github.com/IBM/adversarialrobustness-toolbox" target=_blank>this link</a>.



## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was readapted from *Leslie David. Understanding artificial intelligence ethics and safety. The Alan Turing Institute, https://doi.org/10.5281/zenodo.3240529, 2019* by Jose Hernandez-Orallo, Fernando Martinez-Plumed, Santiago Escobar, and Pablo A. M. Casares.
