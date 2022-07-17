# Reliability

*Synonyms*: Dependability.

## In brief

The objective of **reliability** [^robustness] is that an
AI system behaves exactly as its designers intended and anticipated,
*over time*. A reliable system adheres to the specifications it was
programmed to carry out at any time. Reliability is therefore a measure
of consistency of operation and can establish confidence in the safety
of a system based upon the dependability with which it operationally
conforms to its intended functionality.


## More in detail


The usual definition of **reliability** is the
probability of a system performing its intended functions under expected
conditions. Reliability is closely related to
{doc}`robustness` and resilience, but the focus is
on the time dimension, which is different from other safety
considerations. That is, the system can perform its designed
functionality for the intended period of time. Hardware reliability is
in general well studied, or there are mature methods for testing and
assessing hardware reliability. Thus, the focus of AI reliability,
different from traditional reliability studies, is on the software
system. Compared to hardware reliability, software reliability is
typically more difficult to test, which brings challenges to the
research and development of reliable AI systems.

Kaur and Bahl {cite}`kaur2014software` defined the reliability of software as
"the probability of the failure-free software operation for a specified
period of time in a specified environment\". There are thus three key
elements in the definition of reliability, "failure", "time" and
"environment" (or "operational profile\"). Failure means that in some
way the software has not functioned according to the customer's
requirements {cite}`rushby1988quality`. The failure events of an AI system
can be mostly related to software errors, in addition to the failure of
hardware. For hardware failures, {cite}`hanif2018robust` discussed that AI
hardware failures are related to software errors, aging, process
variation, and temperature. Software failures, understood as a departure
of the external behavior of the program from the user's requirements,
are usually related to software errors and interruptions. For example,
the occurrence of a disengagement event is considered as a failure of
the system for autonomous vehicles {cite}`hong2021reliability`). Note also
the related term of software "fault\", which refers to a defect in a
program that, when executed under certain conditions, causes a
failure---that is, what is generally called a "bug". The time scale in
AI reliability can be different for different structure levels or AI
applications (e.g., calendar time, cycles, calls, etc., to AI
algorithms, or, miles driven for autonomous vehicles or the length of a
conversation between a customer and an AI chatbot, when analysing
particular applications). Finally, the operating environment includes
both the physical environment for hardware systems (e.g., compute,
temperature, humidity, etc.), and non-physical for software systems
(e.g., data, libraries, meta-settings, etc.).

Software reliability is not only one of the most important and immediate
attributes of software quality, it is also the most readily quantified
and measured. From the basic notion of reliability, many different
measures can be developed to quantify the occurrence of failures in
time. Some of the most important of these measures, and their
interrelationships are summarised below (adapted from {cite}`rushby1988quality`):

-   **Hazard Rate**, denoted by $z(t)$, is the conditional failure
    density at time $t$, given that no failure has occurred up to that
    time. That is, $z(t) = f(t)/R(t)$, where $f(t)$, is the probability
    density for failure at time t, and $R(t)$ is the probability of
    failure-free operation up to time $t$. Reliability and hazard rate
    are related by $R(t) = e^{-\int_{0}^{t} z(x) dx}$.

-   **Mean Value Function**, denoted by $\mu(t)$, is the mean number of
    failures that have occurred by time $t$.

-   **Failure Intensity**, denoted by $\lambda(t)$, is the number of
    failures occurring per unit time at time $t$. This is related to the
    mean value function by $\lambda(t) = \frac{d}{dt} \mu(t)$. The
    number of failures expected to occur in the half open interval
    $(t,t + \delta t]$ is $\lambda(t) \dot \delta  t$.

Failure intensity is the measure most commonly used in the
quantification of software reliability {cite}`rushby1988quality`. Software
reliability models have appeared as people try to understand the
features of how and why software fails, and attempt to quantify software
reliability. Given that the quantities associated with reliability are
usually random variables (due to of the complexity of the factors
influencing the occurrence of a failure), reliability models follow the
form of random stochastic processes defining the behaviour of software
failures to time. Over 200 models have been established since the early
1970s (see {cite}`musa1990software` for a survey of software reliability
models). Since the number of faults in a program generally changes over
time (as they are usually repaired when they appear), the probability
distributions of the components of a reliability model vary with time
and, thus, reliability models are based on nonhomogeneous random
processes.

Finally, it should be stressed that, when people desire extremely high
reliability because of the critical nature of a particular application,
e.g. for autopilot software, they often use formal logical systems to
maximise their certainty of implementation correctness
{cite}`latham1986department,russell2015unifying`.

While many of the concepts in software reliability apply to artificial
intelligence, some approaches are not directly applicable because the
lack of a clear specification, and accordingly there are many other
sources of faults that are not software 'bugs' or hardware errors.


## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was written by Jose Hernandez-Orallo, Fernando Martinez-Plumed, Santiago Escobar, and Pablo A. M. Casares.

[^robustness]: Definition taken from {cite}`david2019understanding under Creative Commons Attribution License 4.0.

