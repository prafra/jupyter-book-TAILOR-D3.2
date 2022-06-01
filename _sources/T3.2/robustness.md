# Robustness

*Synonyms*: Brittleness.

## In brief

**Robustness** is the degree in which an AI
system functions[^robustness] reliably and accurately *under harsh conditions.*
These conditions may include adversarial intervention, implementer
error, or skewed goal-execution by an automated learner (in
reinforcement learning applications). The measure of robustness is
therefore the strength of a system's integrity and the soundness of its
operation in response to difficult conditions, adversarial attacks,
perturbations, data poisoning, and undesirable reinforcement learning
behaviour.

## More in detail

**Robustness** is a broad term that usually
encompasses many problems that can affect the stability and good
behaviour of an AI system. However, it does not cover the failure of a
system under normal operation, attrition or obsolescence, issues that
are covered by the related term of
{doc}`reliability`. Robustness is also closely
related to {doc}`security`, as in both cases the
system must withstand (adversarial) attacks. However, robustness does
not usually cover elements such as unauthorised access that compromises
[privacy](../T3.5.md), but only those that can lead to
operational failure or damage.

**Robustness** can be ensured by *prevention* or
by *recovery* procedures. The prevention aspect of robustness has to do
with preventive testing of the functioning of the AI System under
uncommon or stressful conditions. This has been argued by the European
Commission as a key piece to ensure the trustworthiness of AI systems
{cite}`EU_whitepaper`, and is similar to the testing any software would
undergo before taking decisions in the real world, from aircraft control
systems to banking web pages. Testing for robustness not only considers
attrition over time, covered by {doc}`reliability`,
but especially in abnormal working mode, such as for example when human
users make mistakes. An example of this is the automatic brake system
cars introduce: in normal conditions the human will be in charge of
braking. However, since the car is designed with collision prevention in
mind, it should also be robust to human errors.

The *recovery* procedure, on the other hand, ensures that even if the AI
system is not able to prevent the failure, it will limit the amount of
damage produced. For example, if a conversational AI support system is
unsure how to respond to specific queries, it may still have the safe
policy of deferring to a human agent.

**Robustness** is compromised when systems are
brittle to unfamiliar events and scenarios. They may make unexpected and
serious mistakes, because they have neither the capacity to
contextualise the problems they are programmed to solve nor the
common-sense ability to determine the relevance of new 'unknowns'. This
fragility or brittleness can have especially significant consequences in
safety-critical applications like fully automated transportation and
medical decision support systems where undetectable changes in inputs
may lead to significant failures. Alternatively,
**robustness** might also be critical in
situations where it is very hard for a human to intervene and manually
recover from the error, such as for instance, in a space mission.


## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

---
 
This entry was written by Jose Hernandez-Orallo, Fernando Martinez-Plumed, Santiago Escobar, and Pablo A. M. Casares.

---

[^robustness]: From here the definition is taken from {cite}`david2019understanding` under Creative Commons Attribution License 4.0.
