# Evaluation

*Synonyms*: Assessment, Testing, Measurement.

## In brief

**AI measurement** is any activity that estimates
attributes as *measures*--- of an AI system or some of its components,
abstractly or in particular contexts of operation. These attributes, if
well estimated, can be used to explain and predict the *behaviour* of
the system. This can stem from an engineering perspective, trying to
understand whether a particular AI system meets the specifications or
the intention of their designers, known respectively as
**verification** and **validation**. Under this perspective, AI
measurement is close to computer systems
**testing** (hardware and/or software) and other
evaluation procedures in engineering. However, in AI there is an
extremely complex *adaptive* behaviour, and in many cases, with a lack
of a written and operational specification. What the systems has to do
depends on some constraints and utility functions that have to be
optimised, is specified by example (from which the system has to learn a
model) or ultimately depends on feedback from the user or the
environment (e.g., in the form of rewards).

## More in detail


AI **measurement** has been taken place since the
early days of AI and has framed the discipline very significantly.
Actually, one of the foundational ideas behind AI is the famous
imitation game {cite}`turing1950computing`, which ---somewhat misleadingly---
is usually referred to as the Turing *test*. However, this initial
emphasis on evaluation, albeit mostly philosophical, did not develop
into technical AI evaluation as an established subfield in AI, in the
same way the early {doc}`reliability` and
{doc}`robustness` problems in software engineering
led to the important areas of software validation, verification and
testing, today using both theoretical and experimental approaches
{cite}`musa1990software,adrion1982validation`. Still, there are some recent
surveys and books covering the problem of AI evaluation, and giving
comprehensive or partial views of AI measurement, such as
{cite}`hernandez2017evaluation,moam2017,hernandezCosmos2017,welty2019metrology,flach2019performance,flach2019b,guillaume2019,hernandez2020ai,martinezdual,hernandez2021identifying,orallo2022`.

The tradition in AI measurement turns around the concept of
'task-oriented evaluation'. For instance, given a scheduling problem, a
board game or a classification problem, systems are evaluated according
to some metric of *task performance*. To standardise the comparisons
among systems, there are datasets and benchmarks that are used for
evaluating these systems, so that evaluation data is not cherry-picked
by the AI designers. We find a myriad of examples of the latter in
PapersWithCode[^PwC] (PwC), an open-source, community-centric platform
which offers researchers access to hundreds of benchmarks and thousands
of results from associated papers, with an emphasis on machine learning.
PwC collects information about the performance of different AI systems
during a given period, typically ranging from the introduction of the
benchmark to the present day.
Figure {numref}`{number} <fig:PWCimagenet>` shows an example of the evolution of
results for ImageNet{cite}`deng2009imagenet`.

```{figure} ./PwC.png
---
name: fig:PWCimagenet
width: 800px
align: center
---

State-of-the-Art for the image classification task using the benchmark ImageNet. The points represent the accuracy of all the attempts from 2011 to 2022. The connected points on the Pareto front are shown in blue. Chart from
<https://paperswithcode.com/sota/image-classification-on-imagenet>

```

However, the focus on particular benchmarks (which are known by the
researchers in advance) and the power of machine learning techniques has
led to a problem of benchmark specialisation, a phenomenon that is
related to issues such as "teaching to the test\" (students prepare for
the test but do not know how to solve cases that differ slightly from
those of the exam) or Goodhart's or Campbell's laws (optimising to the
indicator may lead to the metric not measuring what it measured
originally, with possibly some other side effects). One clear
manifestation of this phenomenon is the 'challenge-solve-and-replace'
evaluation dynamics {cite}`schlangen2019language` or a
'dataset-solve-and-patch' adversarial benchmark co-evolution
{cite}`zellers2019hellaswag`, which means that as soon as a benchmark is
released, performance grows quickly because researchers specialise the
design and training of the system to the benchmark, but not to the
general task {cite}`hernandez2020ai`. Ultimately the benchmark needs to be
replaced by another one (usually more complex or adversarially
designed), in a continuous cycle.

This task-oriented evaluation has been blamed for some of the failures
or narrowness of AI in the past ---lack of common sense, of generality,
of adaptability to new contexts and distributions. As we said, since the
beginning of the discipline, other approaches for AI measurement have
been used or proposed. These include the Turing test, and endless
variants {cite}`oppydowe2011,hernandez2020twenty`, the use of human tests,
from science exams {cite}`mihaylov2018can` to psychometric tests
{cite}`BringsjordSchimanski2003,IQnotmachines2012computermodels-iq2015`,
the adaptation of psychophysics {cite}`leibo2018psychlab` or item response
theory {cite}`martinez2019item`, the use of collections of video games
{cite}`bellemare2013arcade`, the exploration of naive physics
{cite}`bakhtin2019phyre`, or the adaptation of tests from animal cognition
{cite}`beyret2019animal`. All these approaches attempt to measure
intelligence more broadly, some general cognitive abilities or at least
skills that could be applied to a range of different tasks. Accordingly,
these fall under the paradigm of 'capability-oriented evaluation'
{cite}`hernandez2017evaluation`.

The key difference between performance and capability is that
performance is affected by the distribution, while capability is not.
For instance, the same individual (an AI system or a human) can have
different degrees of performance for the same task or set of tasks if we
change the distribution of examples (e.g., by including more difficult
examples), but the capability should be the same, since it should be a
property of an individual. If a person or computer has the capability of
resolving simple negation, this *capability* is not changed by including
many double negations in the dataset, even if this decreases
performance. However, identifying and estimating the level for different
capabilities is much more challenging than measuring performance. Also,
drawing conclusions about the cognitive abilities of AI systems requires
caution, even from the most-well designed experiments. But this is also
true even when performance is used as a proxy for capability
{cite}`ijcai2022-not-a-number`.




## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

---
 
This entry was written by Jose Hernandez-Orallo, Fernando Martinez-Plumed, Santiago Escobar, and Pablo A. M. Casares.

---

[^PwC]: [paperswithcode.com](paperswithcode.com)
