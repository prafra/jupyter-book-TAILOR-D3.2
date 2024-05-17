# Alignment

*Synonyms*: (Mis)directed, (Un)intended behaviour

## In brief

The goal of AI **alignment** is to ensure that AI
systems are aligned with human intentions and values. This first
requires determining the normative question of what values or principles
we have and what humans really want, collectively or individually, and
second, the technical question of how to imbue AI systems with these
values and goals.

## More in detail

The concept of **alignment** has been mostly
covered at the philosophical and ethical levels, because the normative
question involves fundamental issues about human behaviour and ethics,
and goes beyond the related concept of
**validity**. Also, the technical question is
hard to solve even if the normative question is clear, because it
depends on a very diverse collection of paradigms about what an AI
system is and what it is expected to be, in terms of techniques and
capabilities.

Let us start with the normative question. Following Gabriel (2020) {cite}`gabriel2020artificial`,
there is no consensus of what alignment means: 
> "there are significant differences between AI that aligns with instructions, intentions, revealed preferences, ideal preferences, interests and values". 

In particular, these six different perspectives can be summarised as follows:

-   "Instructions: the agent does what I instruct it to do".

-   "Expressed intentions: the agent does what I intend it to do."

-   "Revealed preferences: the agent does what my behaviour reveals I
    prefer."

-   "Informed preferences or desires: the agent does what I would want
    it to do if I were rational and informed."

-   "Interest or well-being: the agent does what is in my interest, or
    what is best for me, objectively speaking."

-   "Values: the agent does what it morally ought to do, as defined by
    the individual or society."

None of these interpretations fully captures what alignment should be,
and some of them may lead to important problems and paradoxes. As said
before, even in those cases where there could be some agreement and
disambiguation in clear cases, the technical question is also fraught
with difficulties. One general technical problem of aligning AI systems
is that it is hard to say what the system has to do, but it is much
harder to specify what the system should not do, mostly because this is
taken for granted or appeals to "common" sense, which machines lack
today.

Then, many specific problems manifest differently depending on the
particular AI paradigm. For instance, in reinforcement learning (RL),
"the learner system actively solves problems by engaging with its
environment through trial and error. This exploration and
'problem-solving' behaviour is determined by the objective of maximising
a reward function that is defined by its designers. \[\...\] An RL
system, which is operating in the real-world without sufficient
controls, may determine a reward-optimising course of action that is
optimal for achieving its desired objective but harmful to people."
{cite}`david2019understanding`. A significant research and philosophical effort about the
AI systems of the future has been framed as a RL problem.

Other kinds of systems show different problems. For instance, digital
assistants are commanded by natural language. As a result, alignment
problems can come from misunderstanding of the commands, given the
ambiguity of natural language. For instance, after the command "prepare
something proteic for dinner" a digital robotic assistant may put the
cat in the oven. Even non-agential systems such as a simple supervised
model may end up terribly misaligned with human values by being trained
by biased or narrow datasets. For instance, a self-driving car with a
pedestrian recognition system may fail to detect a group of people being
disguised at a carnival. These are examples of three kinds of AI systems
(*reinforcement learning*, *digital assistants*, and *object recognition
systems*) that have been around for some time, and we still face many
safety and robustness issues with them. The problems with new paradigms,
such as language models, are still being recognised.

Overall, AI alignment is a critical and fundamental open problem that
requires philosophical, ethical and technical progress. The progress so
far is not keeping up with the developments of AI as a field.

## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was written by Jose Hernandez-Orallo, Fernando Martinez-Plumed, Santiago Escobar, and Pablo A. M. Casares.
