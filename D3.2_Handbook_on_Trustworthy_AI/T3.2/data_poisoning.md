# Data Poisoning


## In brief

**Data poisoning** occurs when an adversary
modifies or manipulates part of the dataset upon which a model will be
trained, validated, or tested. By altering a selected subset of training
inputs, a poisoning attack can induce a trained AI system into curated
misclassification, systemic malfunction, and poor performance. An
especially concerning dimension of targeted data poisoning is that an
adversary may introduce a 'backdoor' into the infected model whereby the
trained system functions normally until it processes maliciously
selected inputs that trigger error or failure. Data poisoning is
possible because data collection and procurement often involves
potentially unreliable or questionable sources. When data originates in
uncontrollable environments like the internet, social media, or the
Internet of Things, many opportunities present themselves to
ill-intentioned attackers, who aim to manipulate training examples.
Likewise, in third-party data curation processes (such as
'crowdsourced' labelling, annotation, and content identification),
attackers may simply handcraft malicious inputs. [^def3]

## More in detail

**Data poisoning** is a security threat to AI
systems in which an attacker controls the behaviour of a system by
manipulating its training, validation or testing data
{cite}`schwarzschild2021just`. While it usually refers to the training data
for machine learning algorithms, it could also affect some other AI
systems by corrupting the testing data. Note that when the deployment
data is corrupted during operation, we are in the situation of an
{doc}`adversarial_attack`. *Data_poisoning* is related to *data
contamination*, although contamination is
usually more accidental than intentional. For instance, many language
models
{cite}`devlin2018bert,brown2020language,rae2021scaling,hendrycks2020measuring,hendrycks2021measuring,bommasani2021opportunities,ouyang2022training`.
are trained with data that is then used for test or validation, leading
to an overoptimistic {doc}`evaluation` of a system's
behaviour.

In the particular case of an attacker manipulating the training data by
inserting incorrect or misleading information, as the algorithm learns
from this corrupted data, it will draw unintended and even harmful
conclusions. This type of threat is particularly relevant for deep
learning systems because they require large amounts of data to train
which is usually extracted from the web, and, at this scale, it is often
infeasible to properly vet content. We find examples such as Imagenet
{cite}`russakovsky2015imagenet` or the Open Images Dataset
{cite}`kuznetsova2020open` containing tens or hundreds of millions of images
from a wide range of potentially insecure and, in many cases, unknown
sources. The current reliance of AI systems on such massive datasets
that are not manually inspected has led to fears that corrupted training
data can produce flawed models {cite}`jiang2018mentornet`.

According to the breadth of the attack, data poisoning attacks fall into
two main categories: attacks targeting *availability* and attacks
targeting *integrity*. Availability attacks are usually unsophisticated
but extensive, injecting as much erroneous data as possible into a
database, so that the machine learning algorithm trained with this data
will be totally inaccurate. Attacks against the integrity of machine
learning are more complex and potentially more damaging. They leave most
of the database intact, except for an imperceptible backdoor that allows
attackers to control it. As a result, the model will apparently work as
intended but with a fatal flaw. For instance, in a cybersecurity
application, a classifier could make right predictions except when
reading a specific file type, which is considered benign because
hundreds of examples were included with that labelled in the corrupted
dataset.

Depending on the timing of the attack, poisoning attacks can also be
classified into two broad categories: *backdoor* and *triggerless
poisoning attack*. The former causes a model to misclassify samples at
test time that contain a particular trigger (e.g., small patches in
images or characters sequence in text)
{cite}`chen2017targeted,dai2019backdoor,saha2020hidden,turner2018clean`.
For example, training images could be manipulated so that a vision
system does not identify any person wearing a piece of clothing having
the trigger symbol printed on it. In this case model, the attacker
modifies both the training data (placing poisons) and test data
(inserting the trigger)
{cite}`biggio2012poisoning,huang2020metapoison,zhu2019transferable`.
Backdoor attacks cause a victim to misclassify any image containing the
trigger. On the other hand, triggerless poisoning attacks do not require
modifications at the time of inference and cause a victim to misclassify
an individual sample {cite}`shafahi2018poison`.

Data poisoning attacks can cause considerable damage with minimal
effort. Their effectiveness is almost directly proportional to the
quality of the data. Poor quality data will produce subpar results, no
matter how advanced the model is. For instance, the experiment ImageNet
Roulette {cite}`crawford2019excavating` used user-uploaded and labelled
images to learn how to classify new images. Before long, the system
began using racial and gender slurs to label people. Seemingly small and
easily overlooked considerations, such as people using harmful language
on the internet, become shockingly prevalent when an AI system learns
from this data. As machine learning becomes more advanced, it will make
more connections between data points that humans would not think of. As
a result, even small changes to a database can have substantial
repercussions.

While data poisoning is a concern, companies can defend against it with
existing tools and techniques. The U.S. Department of Defense's Cyber
Maturity Model Certification (CMMC) outlines four basic cyber principles
for keeping machine learning data safe[^cmmc]: network (e.g., setting up
and updating firewalls will help keep databases off-limits to internal
and external threats), facility (e.g., restricting access to data
centres), endpoint (e.g., use of data encryption, access controls and
up-to-date anti-malware software) and people protection (e.g., user
training). However, this assumes that the data is generated inside the
limits of the organisation, but many training datasets are complemented
with sources used for research or coming from social media, which are
very difficult to vet. Also, with the current trend of using pretrained
models and tuning them with smaller amounts of particular data, the risk
is more on the data used for these pretrained models than unauthorised
access to the finetuning data. Inspecting the models once trained, using
techniques from [explainable AI](../T3.1/T3.1.md) is also
challenging, as the trapdoors may represent a very small percentage of
the behaviour of the system. Overall, **data
poisoning** is a complex problem that is closely
related to other major problems in AI safety, and will remain
problematic with the current paradigm of learning from massive amounts
of data.


## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was written by Jose Hernandez-Orallo, Fernando Martinez-Plumed, Santiago Escobar, and Pablo A. M. Casares.

[^def3]: Definition taken from {cite}`david2019understanding` under Creative Commons Attribution License 4.0.
[^cmmc]: https://cmmc-coe.org/test/
