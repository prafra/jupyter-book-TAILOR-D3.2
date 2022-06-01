---
author:
- |
    Jose Hernandez-Orallo, Fernando Martinez-Plumed,\
    Santiago Escobar, Pablo A M Casares\
    VRAIN, Universitat Politècnica de València
bibliography:
- 'biblio.bib'
date: May 2022
title: |
    TAILOR ENCYCLOPEDIA WP3\
    T3.2 Safety and Robustness
---

\maketitle
Definition
==========

**Safety and Robustness**: The safety of an AI system refers to the
extent the system meets its intended functionality without producing any
physical or psychological harm, especially to human beings, and by
extension to other material or immaterial elements that may be valuable
for humans, including the system itself. Safety must also cover the way
and conditions in which the system ceases its operation, and the
consequences of stopping. The term robustness emphasises that safety and
---conditionally to it--- functionality, must be preserved under harsh
conditions, including unanticipated errors, exceptional situations,
unintended or intended damage, manipulation or catastrophic states.

Contents
========

In this part we will cover the main elements that define the safety and
robustness of AI systems. Some of them are common to system safety in
general, to software-hardware computer systems or to critical systems
engineering, such as [software bugs]{style="color: darkblue"}. Some
others are magnified in artificial intelligence, such as [denial of
service]{style="color: darkblue"}, a robustness issue that can appear by
inducing an AI system to unrecoverable states or by generating inputs
that collapse the system due to high computational demands. Some other
issues are more specific to AI systems, such as [reward
hacking]{style="color: darkblue"}. These new issues appear more clearly
in those systems that are specified in non-programmatic or non-explicit
ways (e.g., through a utility function to be optimised, through
examples, rewards or other implicit ways), as exemplified by systems
that operate with solvers or machine learning models. We will pay more
attention to these more AI-specific issues because they are less covered
in the traditional literature about safety in computer systems. They are
also more challenging because of their cognitive character, the
ambiguities of human intent, several ethical issues and the relevance of
long-term risks. This character and the fast development of the field
has also blurred some distinctions between safety (threats without
malicious intent) and [security]{style="color: darkblue"} (intentional
threats), especially in now popular research areas such as [adversarial
attacks]{style="color: darkblue"} and [data
poisoning]{style="color: darkblue"}, and also within data privacy (e.g.,
[information leakage]{style="color: darkblue"} by querying machine
learning models or other [side channel
attacks]{style="color: darkblue"}). In the end, protecting the
environment from the system (safety) also requires protecting the system
from the environment ([security]{style="color: darkblue"}). Taking into
account the changing character of the field, we include a taxonomic
organisation of terms in the area of AI safety and robustness and their
definition.

Motivation and background
=========================

Given the increasing capabilities and widespread use of artificial
intelligence, there is a growing concern about its risks, as humans are
progressively replaced or sidelined from the decision loop of
intelligent machines. The technical foundations and assumptions on which
traditional safety engineering principles are based are inadequate for
systems in which AI algorithms, and in particular Machine Learning (ML)
algorithms, are interacting with people and the environment at
increasingly higher levels of autonomy. There have been regulatory
efforts to limit the use of AI systems in safety-critical or hostile
environments, such as health, defense, energy, etc.
[@floridi2021european; @veale2021demystifying], but the consequences can
also be devastating in areas that were not considered high risk, just by
the scaling numbers or domino effects of AI systems. On top of the
numerous safety challenges posed by present-day AI systems, a
forward-looking analysis on more capable future AI systems raises more
systemic concerns, such as highly disruptive scenarios in the workplace,
the effect on human cognition in the long term and even existential
risks.

Guidelines
==========

Actions to ensure safety and robustness of AI systems need to take a
holistic perspective, encompassing all the elements and stages
associated with the conception, design, implementation and maintenance
of these systems. We organise[^1] the field of AI safety and robustness
into seven groups, following similar categorisations[^2]:

-   AI Safety Foundations: This category covers a number of foundational
    concepts, characteristics and problems related to AI safety that
    need special consideration from a theoretical perspective. This
    includes concepts such as uncertainty, generality or value
    alignment, as well as characteristics such autonomy levels, safety
    criticality, types of human-machine and environment-machine
    interaction. This group intends to collect any cross-category
    concerns in AI Safety and Robustness.

-   Specification and Modelling: The main scope of this category is on
    how to describe needs, designs and actual operating AI systems from
    different perspectives (technical concerns) and abstraction levels.
    This includes the specification and modelling of risk management
    properties (e.g., hazards, failures modes, mitigation measures), as
    well as safety-related requirements, training, behaviour or quality
    attributes in AI-based systems.

-   Verification and Validation: This category concerns design and
    implementation-time approaches to ensure that an AI-based system
    meets its requirements (verification) and behaves as expected
    (validation). The range of techniques covers any
    formal/mathematical, model-based simulation or testing approach that
    provides evidence that an AI-based system satisfies its defined
    (safety) requirements and does not deviate from its intended
    behaviour and causes unintended consequences, even in extreme and
    unanticipated situations (robustness).

-   Runtime Monitoring and Enforcement: The increasing autonomy and
    learning nature of AI-based systems is particularly challenging for
    their verification and validation (V&V), due to our inability to
    collect an epistemologically sufficient quantity of evidence to
    ensure correctness. Runtime monitoring is useful to cover the gaps
    of design-time V&V by observing the internal states of a given
    system and its interactions with external entities, with the aim of
    determining system behaviour correctness or predicting potential
    risks. Enforcement deals with runtime mechanisms to self-adapt,
    optimise or reconfigure system behaviour with the aim of supporting
    fallback to a safe system state from the (anomalous) current state.

-   Human-Machine Interaction: As autonomy progressively substitutes
    cognitive human tasks, some kind of human-machine interaction issues
    become more critical, such as the loss of situational awareness or
    overconfidence. Other issues include: collaborative missions that
    need unambiguous communication to manage self-initiative to start or
    transfer tasks; safety-critical situations in which earning and
    maintaining trust is essential at operational phases; or cooperative
    human-machine decision tasks where understanding machine decisions
    are crucial to validate safe autonomous actions.

-   Process Assurance and Certification: Process Assurance is the
    planned and systematic activities that assure system lifecycle
    processes conform to its requirements (including safety) and quality
    procedures. In our context, it covers the management of the
    different phases of AI-based systems, including training and
    operational phases, the traceability of data and artefacts, and
    people. Certification implies a (legal) recognition that a system or
    process complies with industry standards and regulations to ensure
    it delivers its intended functions safely. Certification is
    challenged by the inscrutability of AI-based systems and the
    inability to ensure functional safety under uncertain and
    exceptional situations prior to its operation.

-   Safety-related Ethics, Security and Privacy: While these are quite
    large fields, we are interested in their intersection and
    dependencies with safety and robustness. Ethics becomes increasingly
    important as autonomy (with learning and adaptive abilities)
    involves the transfer of safety risks, responsibility, and
    liability, among others. AI-specific security and privacy issues
    must be considered with regard to its impact on safety and
    robustness. For example, malicious adversarial attacks can be
    studied with focus on situations that compromise systems towards a
    dangerous situation.

Figure [\[fig:taxonomy\]](#fig:taxonomy){reference-type="ref"
reference="fig:taxonomy"} reflects the seven categories described above.
Many of the terms and concepts we will expand on correspond to one or
more of these categories.

\centering
![Taxonomy of AI Safety. Taken from
[@espinoza2019].[]{label="fig:taxonomy"}](taxonomy.jpg){#fig:taxonomy
width="65%"}

Recommended reading
===================

Some introductory sources for AI Safety and Robustnes are [@amodei2016],
[@espinoza2019], [@gabriel2020artificial], [@david2019understanding],
and [@russell2015research].

Terms
=====

In what follows we make a selection of key terms in AI Safety and
Robustness, giving short definitions and extended formulations for each
of them.

[Alignment]{style="color: darkblue"}
------------------------------------

: [(Mis)directed]{style="color: darkblue"} / [(Un)intended
behaviour]{style="color: darkblue"}

The goal of AI [alignment]{style="color: darkblue"} is to ensure that AI
systems are aligned with human intentions and values. This first
requires determining the normative question of what values or principles
we have and what humans really want, collectively or individually, and
second, the technical question of how to imbue AI systems with these
values and goals.

The concept of [alignment]{style="color: darkblue"} has been mostly
covered at the philosophical and ethical levels, because the normative
question involves fundamental issues about human behaviour and ethics,
and goes beyond the related concept of
[validity]{style="color: darkblue"}. Also, the technical question is
hard to solve even if the normative question is clear, because it
depends on a very diverse collection of paradigms about what an AI
system is and what it is expected to be, in terms of techniques and
capabilities.

Let us start with the normative question. Following Gabriel (2020),
there is no consensus of what alignment means: "there are significant
differences between AI that aligns with instructions, intentions,
revealed preferences, ideal preferences, interests and values". In
particular, these six different perspectives can be summarised as
follows:

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
(Leslie 2019). A significant research and philosophical effort about the
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
(reinforcement learning, digital assistants and object recognition
systems) that have been around for some time, and we still face many
safety and robustness issues with them. The problems with new paradigms,
such as language models, are still being recognised.

Overall, AI alignment is a critical and fundamental open problem that
requires philosophical, ethical and technical progress. The progress so
far is not keeping up with the developments of AI as a field.

[Robustness]{style="color: darkblue"}
-------------------------------------

: [Brittleness]{style="color: darkblue"}

[Robustness]{style="color: darkblue"} is the degree in which an AI
system functions[^3] reliably and accurately *under harsh conditions.*
These conditions may include adversarial intervention, implementer
error, or skewed goal-execution by an automated learner (in
reinforcement learning applications). The measure of robustness is
therefore the strength of a system's integrity and the soundness of its
operation in response to difficult conditions, adversarial attacks,
perturbations, data poisoning, and undesirable reinforcement learning
behaviour.

[Robustness]{style="color: darkblue"} is a broad term that usually
encompasses many problems that can affect the stability and good
behaviour of an AI system. However, it does not cover the failure of a
system under normal operation, attrition or obsolescence, issues that
are covered by the related term of
[reliability]{style="color: darkblue"}. Robustness is also closely
related to [security]{style="color: darkblue"}, as in both cases the
system must withstand (adversarial) attacks. However, robustness does
not usually cover elements such as unauthorised access that compromises
[privacy]{style="color: darkblue"}, but only those that can lead to
operational failure or damage.

[Robustness]{style="color: darkblue"} can be ensured by *prevention* or
by *recovery* procedures. The prevention aspect of robustness has to do
with preventive testing of the functioning of the AI System under
uncommon or stressful conditions. This has been argued by the European
Commission as a key piece to ensure the trustworthiness of AI systems
[@EU_whitepaper], and is similar to the testing any software would
undergo before taking decisions in the real world, from aircraft control
systems to banking web pages. Testing for robustness not only considers
attrition over time, covered by [reliability]{style="color: darkblue"},
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

[Robustness]{style="color: darkblue"} is compromised when systems are
brittle to unfamiliar events and scenarios. They may make unexpected and
serious mistakes, because they have neither the capacity to
contextualise the problems they are programmed to solve nor the
common-sense ability to determine the relevance of new 'unknowns'. This
fragility or brittleness can have especially significant consequences in
safety-critical applications like fully automated transportation and
medical decision support systems where undetectable changes in inputs
may lead to significant failures. Alternatively,
[robustness]{style="color: darkblue"} might also be critical in
situations where it is very hard for a human to intervene and manually
recover from the error, such as for instance, in a space mission.

[Reliability]{style="color: darkblue"}
--------------------------------------

: [dependability]{style="color: darkblue"}

[^4] The objective of [reliability]{style="color: darkblue"} is that an
AI system behaves exactly as its designers intended and anticipated,
*over time*. A reliable system adheres to the specifications it was
programmed to carry out at any time. Reliability is therefore a measure
of consistency of operation and can establish confidence in the safety
of a system based upon the dependability with which it operationally
conforms to its intended functionality.

The usual definition of [reliability]{style="color: darkblue"} is the
probability of a system performing its intended functions under expected
conditions. Reliability is closely related to
[robustness]{style="color: darkblue"} and resilience, but the focus is
on the time dimension, which is different from other safety
considerations. That is, the system can perform its designed
functionality for the intended period of time. Hardware reliability is
in general well studied, or there are mature methods for testing and
assessing hardware reliability. Thus, the focus of AI reliability,
different from traditional reliability studies, is on the software
system. Compared to hardware reliability, software reliability is
typically more difficult to test, which brings challenges to the
research and development of reliable AI systems.

Kaur and Bahl [@kaur2014software] defined the reliability of software as
"the probability of the failure-free software operation for a specified
period of time in a specified environment\". There are thus three key
elements in the definition of reliability, "failure", "time" and
"environment" (or "operational profile\"). Failure means that in some
way the software has not functioned according to the customer's
requirements [@rushby1988quality]. The failure events of an AI system
can be mostly related to software errors, in addition to the failure of
hardware. For hardware failures, [@hanif2018robust] discussed that AI
hardware failures are related to software errors, aging, process
variation, and temperature. Software failures, understood as a departure
of the external behavior of the program from the user's requirements,
are usually related to software errors and interruptions. For example,
the occurrence of a disengagement event is considered as a failure of
the system for autonomous vehicles [@hong2021reliability]). Note also
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
interrelationships are summarised below (adapted from
[@rushby1988quality]):

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
quantification of software reliability [@rushby1988quality]. Software
reliability models have appeared as people try to understand the
features of how and why software fails, and attempt to quantify software
reliability. Given that the quantities associated with reliability are
usually random variables (due to of the complexity of the factors
influencing the occurrence of a failure), reliability models follow the
form of random stochastic processes defining the behaviour of software
failures to time. Over 200 models have been established since the early
1970s (see [@musa1990software] for a survey of software reliability
models). Since the number of faults in a program generally changes over
time (as they are usually repaired when they appear), the probability
distributions of the components of a reliability model vary with time
and, thus, reliability models are based on nonhomogeneous random
processes.

Finally, it should be stressed that, when people desire extremely high
reliability because of the critical nature of a particular application,
e.g. for autopilot software, they often use formal logical systems to
maximise their certainty of implementation correctness
[@latham1986department; @russell2015unifying].

While many of the concepts in software reliability apply to artificial
intelligence, some approaches are not directly applicable because the
lack of a clear specification, and accordingly there are many other
sources of faults that are not software 'bugs' or hardware errors.

[Evaluation]{style="color: darkblue"}
-------------------------------------

: [Assessment]{style="color: darkblue"},
[Testing]{style="color: darkblue"},
[Measurement]{style="color: darkblue"}

[AI measurement]{style="color: darkblue"} is any activity that estimates
attributes as *measures*--- of an AI system or some of its components,
abstractly or in particular contexts of operation. These attributes, if
well estimated, can be used to explain and predict the *behaviour* of
the system. This can stem from an engineering perspective, trying to
understand whether a particular AI system meets the specifications or
the intention of their designers, known respectively as
[verification]{style="color: darkblue"} and
[validation]{style="color: darkblue"}. Under this perspective, AI
measurement is close to computer systems
[testing]{style="color: darkblue"} (hardware and/or software) and other
evaluation procedures in engineering. However, in AI there is an
extremely complex *adaptive* behaviour, and in many cases, with a lack
of a written and operational specification. What the systems has to do
depends on some constraints and utility functions that have to be
optimised, is specified by example (from which the system has to learn a
model) or ultimately depends on feedback from the user or the
environment (e.g., in the form of rewards).

AI [measurement]{style="color: darkblue"} has been taken place since the
early days of AI and has framed the discipline very significantly.
Actually, one of the foundational ideas behind AI is the famous
imitation game [@turing1950computing], which ---somewhat misleadingly---
is usually referred to as the Turing *test*. However, this initial
emphasis on evaluation, albeit mostly philosophical, did not develop
into technical AI evaluation as an established subfield in AI, in the
same way the early [reliability]{style="color: darkblue"} and
[robustness]{style="color: darkblue"} problems in software engineering
led to the important areas of software validation, verification and
testing, today using both theoretical and experimental approaches
[@musa1990software][@adrion1982validation]. Still, there are some recent
surveys and books covering the problem of AI evaluation, and giving
comprehensive or partial views of AI measurement, such as
[@hernandez2017evaluation][@moam2017][@hernandezCosmos2017][@welty2019metrology][@flach2019performance][@flach2019b][@guillaume2019][@hernandez2020ai][@martinezdual][@hernandez2021identifying][@orallo2022].

The tradition in AI measurement turns around the concept of
'task-oriented evaluation'. For instance, given a scheduling problem, a
board game or a classification problem, systems are evaluated according
to some metric of *task performance*. To standardise the comparisons
among systems, there are datasets and benchmarks that are used for
evaluating these systems, so that evaluation data is not cherry-picked
by the AI designers. We find a myriad of examples of the latter in
PapersWithCode[^5] (PwC), an open-source, community-centric platform
which offers researchers access to hundreds of benchmarks and thousands
of results from associated papers, with an emphasis on machine learning.
PwC collects information about the performance of different AI systems
during a given period, typically ranging from the introduction of the
benchmark to the present day.
Figure [\[fig:PWCimagenet\]](#fig:PWCimagenet){reference-type="ref"
reference="fig:PWCimagenet"} shows an example of the evolution of
results for ImageNet[@deng2009imagenet].

\centering
![State-of-the-Art for the image classification task using the benchmark
ImageNet. The points represent the accuracy of all the attempts from
2011 to 2022. The connected points on the Pareto front are shown in
blue. Chart from
<https://paperswithcode.com/sota/image-classification-on-imagenet>.[]{label="fig:PWCimagenet"}](PwC_IN.pdf){#fig:PWCimagenet
width="0.75\columnwidth"}

However, the focus on particular benchmarks (which are known by the
researchers in advance) and the power of machine learning techniques has
led to a problem of benchmark specialisation, a phenomenon that is
related to issues such as "teaching to the test\" (students prepare for
the test but do not know how to solve cases that differ slightly from
those of the exam) or Goodhart's or Campbell's laws (optimising to the
indicator may lead to the metric not measuring what it measured
originally, with possibly some other side effects). One clear
manifestation of this phenomenon is the 'challenge-solve-and-replace'
evaluation dynamics [@schlangen2019language] or a
'dataset-solve-and-patch' adversarial benchmark co-evolution
[@zellers2019hellaswag], which means that as soon as a benchmark is
released, performance grows quickly because researchers specialise the
design and training of the system to the benchmark, but not to the
general task [@hernandez2020ai]. Ultimately the benchmark needs to be
replaced by another one (usually more complex or adversarially
designed), in a continuous cycle.

This task-oriented evaluation has been blamed for some of the failures
or narrowness of AI in the past ---lack of common sense, of generality,
of adaptability to new contexts and distributions. As we said, since the
beginning of the discipline, other approaches for AI measurement have
been used or proposed. These include the Turing test, and endless
variants [@oppydowe2011; @hernandez2020twenty], the use of human tests,
from science exams [@mihaylov2018can] to psychometric tests
[@BringsjordSchimanski2003; @IQnotmachines2012; @computermodels-iq2015],
the adaptation of psychophysics [@leibo2018psychlab] or item response
theory [@martinez2019item], the use of collections of video games
[@bellemare2013arcade], the exploration of naive physics
[@bakhtin2019phyre], or the adaptation of tests from animal cognition
[@beyret2019animal]. All these approaches attempt to measure
intelligence more broadly, some general cognitive abilities or at least
skills that could be applied to a range of different tasks. Accordingly,
these fall under the paradigm of 'capability-oriented evaluation'
[@hernandez2017evaluation].

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
[@ijcai2022-not-a-number].

[Negative side effects]{style="color: darkblue"}
------------------------------------------------

:

[Negative side effects]{style="color: darkblue"} are an important safety
issue in AI system that considers all possible unintended harm that is
caused as a secondary effect of the AI system's operation. An agent can
disrupt or break other systems around, or damage third parties,
including humans, or can exhaust resources, or a combination of all
this. This usually happens because many things the system should *not*
do are not included in its specification. In the case of AI systems,
this is even more poignant as written specifications are usually
replaced by an optimisation or loss function, in which it is even more
difficult to express these things the system should not do, as they
frequently rely on 'common sense'.

[Negative Side Effects]{style="color: darkblue"} are unanticipated or
unintended effects caused by an AI system during operation. Negative
side effects are a key issue within the AI safety literature
[@amodei2016] and typically stem from the difficulty of fully
articulating everything that we want the AI system *not* to do. Negative
side effects can be of two kinds, related to some preservation of the
environment or related to the use of resources. For instance, a clumsy
incompetent agent may break everything around it
[@saisubramanian2020avoiding], not preserving things that should be
unrelated to the goal. On the other hand, a very proficient agent may
exhaust all available resources and disrupt any other agent (machine or
human) that interferes with its goals [@yampolskiy2018artificial].
Recognising these two different causes for side effects is crucial for
the design of safer AI systems.

There are a number of proposed methods for measuring the negative side
effects caused by a system [@armstrong2017; @leike2017; @turner2020],
but a recurring theme is based on estimating counterfactual scenarios in
which the system was not present (or acted differently), and comparing
the changes in the state of the world. Alternatively, in some approaches
for mitigating side effects, these are set externally (marked safe
areas) or incorporated as a "secondary objective\"
[@saisubramanian2020multi] for which trade-offs are found. But in these
approaches side effects just become part of the specification or the
optimisation function, significantly deviating from the original
definition of *side* effect.

For machine learning systems, the real challenge of side effects is that
many of them are not known during training, and they cannot be
incorporated as a regulariser in the target function to be optimised. In
many cases, this information is not even available to the agent during
operation, so we cannot modify the agent's behaviour according to this
information, such as marking some forbidden areas of operation.

While some other safety issues in RL have received important attention
[@garcia2015comprehensive], dealing with side effects is still mostly
unexplored, especially in realistic situations where the agent does not
have any feedback about side effects during training or operation. Also,
the analysis of AI safety in reinforcement learning has usually been
conducted with toy scenarios, not having the complex interaction of the
real world. SafeLife [@safelife] is an exception in this landscape, as a
very rich and full *ecosystem* where many complex behaviours and effects
can be analysed.

\center
![An example task instance from SafeLife. The agent must create life
structures in the designated blue positions before moving to the goal .
Ideally the agent should not disturb the green life cells
.[]{label="fig:SafeLifeEnv"}](SafeLifeLevel7.png){#fig:SafeLifeEnv
width="35%"}

Figure [\[fig:SafeLifeEnv\]](#fig:SafeLifeEnv){reference-type="ref"
reference="fig:SafeLifeEnv"} gives the visual representation of a state
of a SafeLife instance. There we can see that achieving the goals can be
done carefully so that the green life cells are not disturbed. The real
challenge is when the system is not informed explicitly (as part of the
reward or a constraint) that the green life cells should not be
disturbed. In this case, only agents that try to be minimise changes
that are not necessary for the goals will be expected to have low side
effects.

[Distributional shift]{style="color: darkblue"} / [concept drift]{style="color: darkblue"}
------------------------------------------------------------------------------------------

: [Data shift]{style="color: darkblue"} (for [distributional
shift]{style="color: darkblue"})

[^6] Once trained, most machine learning systems operate on static
models of the world that have been built from historical data which have
become fixed in the systems' parameters. This freezing of the model
before it is released 'into the wild' makes its accuracy and reliability
especially vulnerable to changes in the underlying distribution of data.
When the historical data that have crystallised into the trained model's
architecture cease to reflect the population concerned, the model's
mapping function will no longer be able to accurately and reliably
transform its inputs into its target output values. These systems can
quickly become prone to error in unexpected and harmful ways. In all
cases, the system and the operators must remain vigilant to the
potentially rapid concept drifts that may occur in the complex, dynamic,
and evolving environments in which your AI project will intervene.
Remaining aware of these transformations in the data is crucial for safe
AI.

A common use case of machine learning in real world settings is to learn
a model from historical data and then deploy the model on future unseen
examples. When the data distribution for the future examples differs
from the historical data distribution (i.e., the joint distribution of
inputs and outputs differs between training and test o deployment
stages), machine learning techniques that depend precariously on the
i.i.d. assumption tend to fail. This phenomena is call distributional
shift and is a very common problem [@quinonero2008dataset]. Note that a
particular case of distributional shift occurs when only the input
distribution changes (covariate shift) or there is a shift in the target
variable (prior probability shift).

The problem of distributional shift is of relevance not only to academic
researchers, but to the machine learning community at large.
Distributional shift is present in most practical applications, for
reasons ranging from the bias introduced by experimental design to the
irreproducibility of the testing conditions at training time. An example
is email spam filtering, which may fail to recognise spam that differs
in form from the spam the automatic filter has been built on
[@ben2006analysis], yet often the model being highly confident in its
erroneous classifications. This issue is especially important in
high-risk applications of machine learning, such as finance, medicine,
and autonomous vehicles, where a mistake may incur financial or
reputational loss, or possible loss of life. It is therefore important
to assess both a model's robustness to distribution shift and its
estimates of predictive uncertainty, which enable it to detect
distributional shifts [@amodei2016; @gal2016dropout]

In general, the greater the degree of shift, the poorer the model's
performance is. The performance of learned models tend to drop
significantly even with a tiny amount of distribution shift between
training and test [@recht2019imagenet; @szegedy2013intriguing], which
makes it challenging to reliably deploy machine learning in real world
applications. Although one can always increase training coverage by
adding more sources of data [@devlin2018bert], data augmentation
[@madry2017towards; @shorten2019survey], or injecting structural bias
into models
[@fukushima1982neocognitron; @hochreiter1997long; @vaswani2017attention]
for generalisation to any potential input for the learned model, it is
unrealistic to expect a learned model to predict accurately under any
form of distribution shift due to the combinatorial nature of real world
data and tasks.

On the other hand, adapting a model to a specific type of distribution
shift might be more approachable than adapting to any potential
distribution shift scenarios, under appropriate assumptions and with
appropriate modifications. By knowing where the model can predict well,
one can use the model to make conservative predictions or decisions, and
to guide future active data collection to covered shifted distributions.
Therefore, in addition to improving the generalisation performance of
models in general, methods that explicitly deal with the presence of
distribution shift are also desirable for machine learning to be used in
practice [@wu2021learning].

In terms of assessment, the robustness of learning models to
distributional shift is typically assessed via metrics of predictive
performance on a particular task: given two (or more) evaluation sets,
where one is considered matched to the training data and the other(s)
shifted, models which have a smaller degradation in performance on the
shifted data are considered more robust. The quality of uncertainty
estimates is often assessed via the ability to classify whether an
example came from the "in-domain" dataset or a shifted dataset using
measures of uncertainty.

For its part, concept shift (or concept drift) is different from
distributional shift in that it is not related to the input data or the
class distribution but instead is related to the relationship between
two or more dependent variables. An example may be the customer
purchasing behavior over time in a particular online shop. This
behaviour may be influenced by the strength of the economy, this being
not explicitly specified in the data. In this case, the concept of
interest (consumer behaviour) depends on some hidden context, not known
a priori, and not given explicitly in the form of predictive features,
making the learning task more complicated [@tsymbal2004problem]. In this
sense, concept shift can be categorised into 3 types: (1) sudden, abrupt
or instantaneous concept shift (e.g., following the previous example,
the COVID-19 lockdowns significantly changed customer behaviour); (2)
gradual concept shift (e.g., customers are influenced by wider economic
issues, unemployment rates or other trends) which can be divided further
into moderate and slow drifts, depending on the rate of the changes
[@stanley2003learning]; and (3) cyclic concept drifts, where hidden
contexts may be expected to recur due to cyclic phenomena, such as
seasons of the year or may be associated with irregular phenomena, such
as inflation rates or market mood [@harries1998extracting].

Concept drift may be present on supervised learning problems where
predictions are made and data is collected over time. These are
traditionally called online or incremental learning problems
[@ditzler2012incremental], given the change expected in the data over
time. For its part, the common methods for detecting concept drift in
machine learning generally include ongoing monitoring of the performance
(e.g., accuracy) and confidence scores of a learning model. If average
performance or confidence deteriorates over time, concept shift could be
occurring

[Security]{style="color: darkblue"}
-----------------------------------

:

[^7] The goal of [security]{style="color: darkblue"} encompasses the
protection of several operational dimensions of an AI system when
confronted with possible attacks, trying to take control of the system
or having access to design, operational or personal information. A
secure system is capable of maintaining the integrity of the information
that constitutes it. This includes protecting its architecture from the
unauthorised modification or damage of any of its component parts. A
secure system also keeps confidential and private information protected
even under hostile or adversarial conditions.

Security must be an integral part of the AI process. Protecting AI
systems, their data and their communications is critical to the security
and privacy of users, as well as protecting business investments. The AI
systems themselves are incredibly expensive and possess valuable
intellectual property to protect against disclosure and misuse. The
confidentiality of the program code associated with AI systems may be
considered less critical, but access to it, as well as the ability to
manipulate this code, can result in the disclosure of important and
confidential assets.

Several kinds of attacks against AI systems have been reported.
Currently, the most prominent attack vector categories are
[@liao2011secure]: adversarial inputs [@goodfellow2014explaining]; data
poisoning attacks [@schwarzschild2021just]; model stealing techniques
[@tramer2016stealing; @fabra2018identifying]; model poisoning
[@fang2020local], data leakage [@papadimitriou2010data] and neural
network Trojans [@ji2019programmable], among others. Attack vectors
directed against the AI systems' deployment or training environment are
equally applicable. These may be attack vectors directed against
servers, databases, protocols or libraries utilised within the AI system
[@hartmann2020hacking].

Currently, AI systems often lack sufficient security assessments
[@Neustadter2020]. This may be the result of the mutually independent
development of AI methods and their implementation in applications:
while the application should have a security assessment, embedded AI
(via APIs or frameworks) is rarely considered in terms of its security
vulnerabilities by application developers and/or practitioners. While AI
developers may follow coding standards and guidelines for secure
software development, they will not assess the potential attack surface
of an AI system (i.e., the means by which an attacker may enter, extract
data or manipulate the system in question) using the system.

[Adversarial attack]{style="color: darkblue"}
---------------------------------------------

: [adversarial input]{style="color: darkblue"}, [adversarial
example]{style="color: darkblue"}.

An [adversarial input]{style="color: darkblue"} is any perturbation of
the input features or observations of a system (sometimes imperceptible
to both humans and the own system) that makes the system fail or take
the system to a dangerous state. A prototypical case of an adversarial
situation happens with machine learning models, when an external
agent[^8] maliciously modify input data --often in imperceptible ways--
to induce them into misclassification or incorrect prediction. For
instance, by undetectably altering a few pixels on a picture, an
adversarial attacker can mislead a model into generating an incorrect
output (like identifying a panda as a gibbon or a 'stop' sign as a
'speed limit' sign) with an extremely high confidence. While a good
amount of attention has been paid to the risks that adversarial attacks
pose in deep learning applications like computer vision, these kinds of
perturbations are also effective across a vast range of machine learning
techniques and uses such as spam filtering and malware detection. A
different but related type of adversarial attack is called [data
poisoning]{style="color: darkblue"}, but this involves a malicious
compromise of data sources (used for training or testing) at the point
of collection and pre-processing.

[^9] The vulnerabilities of AI systems to adversarial examples have
serious consequences for AI safety. The existence of cases where subtle
but targeted perturbations cause models to be misled into gross
miscalculation and incorrect decisions have potentially serious safety
implication for the adoption of critical systems like applications in
autonomous transportation, medical imaging, and security and
surveillance.

To get an idea of what adversarial examples look like, consider the
example in Figure [\[fig:AdvEx\]](#fig:AdvEx){reference-type="ref"
reference="fig:AdvEx"} shown in [@goodfellow2014explaining]: starting
with an image of a panda from ImageNet [@russakovsky2015imagenet], the
attacker adds a imperceptibly perturbation (i.e., an small vector whose
elements are equal to the sign of the elements of the gradient of the
cost function with respect to the input), to make the image be
recognised as a gibbon with high confidence by a particular deep neural
net (GoogLeNet [@szegedy2015going]). Also, recent research has shown
that even in physical world scenarios, machine learning systems are
vulnerable to adversarial examples: [@kurakin2018adversarial] shows how
printed adversarial images (with modifications imperceptible to the
human eye) obtained from a cell-phone camera are not correctly
classified by the models. In general, adversarial examples have the
potential to be dangerous. For example, attackers could target
autonomous vehicles by using stickers or paint to create an adversarial
stop sign that the vehicle would interpret as a 'yield' or other sign,
as discussed in [@papernot2017practical].

\center
![An adversarial input, overlaid on a typical image, can cause a
classifier to miscategorise a panda as a gibbon. Adapted from
[@goodfellow2014explaining].[]{label="fig:AdvEx"}](adversarial_img_1.png){#fig:AdvEx
width="95%"}

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
found at <https://github.com/IBM/adversarialrobustness-toolbox>.

[Data Poisoning]{style="color: darkblue"}
-----------------------------------------

:

[^10] [Data poisoning]{style="color: darkblue"} occurs when an adversary
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
Likewise, in third- party data curation processes (such as
'crowdsourced' labelling, annotation, and content identification),
attackers may simply handcraft malicious inputs.

[Data poisoning]{style="color: darkblue"} is a security threat to AI
systems in which an attacker controls the behaviour of a system by
manipulating its training, validation or testing data
[@schwarzschild2021just]. While it usually refers to the training data
for machine learning algorithms, it could also affect some other AI
systems by corrupting the testing data. Note that when the deployment
data is corrupted during operation, we are in the situation of an
[adversarial attack]{style="color: darkblue"}. [Data
poisoning]{style="color: darkblue"} is related to [data
contamination]{style="color: darkblue"}, although contamination is
usually more accidental than intentional. For instance, many language
models
[@devlin2018bert; @brown2020language; @rae2021scaling; @hendrycks2020measuring; @hendrycks2021measuring; @bommasani2021opportunities; @ouyang2022training].
are trained with data that is then used for test or validation, leading
to an overoptimistic [Evaluation]{style="color: darkblue"} of a system's
behaviour.

In the particular case of an attacker manipulating the training data by
inserting incorrect or misleading information, as the algorithm learns
from this corrupted data, it will draw unintended and even harmful
conclusions. This type of threat is particularly relevant for deep
learning systems because they require large amounts of data to train
which is usually extracted from the web, and, at this scale, it is often
infeasible to properly vet content. We find examples such as Imagenet
[@russakovsky2015imagenet] or the Open Images Dataset
[@kuznetsova2020open] containing tens or hundreds of millions of images
from a wide range of potentially insecure and, in many cases, unknown
sources. The current reliance of AI systems on such massive datasets
that are not manually inspected has led to fears that corrupted training
data can produce flawed models [@jiang2018mentornet].

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
classified into two broad categories: *backdoor and *triggerless
poisoning attack. The former causes a model to misclassify samples at
test time that contain a particular trigger (e.g., small patches in
images or characters sequence in text)
[@chen2017targeted; @dai2019backdoor; @saha2020hidden; @turner2018clean].
For example, training images could be manipulated so that a vision
system does not identify any person wearing a piece of clothing having
the trigger symbol printed on it. In this case model, the attacker
modifies both the training data (placing poisons) and test data
(inserting the trigger)
[@biggio2012poisoning; @huang2020metapoison; @zhu2019transferable].
Backdoor attacks cause a victim to misclassify any image containing the
trigger. On the other hand, triggerless poisoning attacks do not require
modifications at the time of inference and cause a victim to misclassify
an individual sample [@shafahi2018poison].**

Data poisoning attacks can cause considerable damage with minimal
effort. Their effectiveness is almost directly proportional to the
quality of the data. Poor quality data will produce subpar results, no
matter how advanced the model is. For instance, the experiment ImageNet
Roulette [@crawford2019excavating] used user-uploaded and labelled
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
for keeping machine learning data safe[^11]: network (e.g., setting up
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
techniques from [explainable AI]{style="color: darkblue"} is also
challenging, as the trapdoors may represent a very small percentage of
the behaviour of the system. Overall, [data
poisoning]{style="color: darkblue"} is a complex problem that is closely
related to other major problems in AI safety, and will remain
problematic with the current paradigm of learning from massive amounts
of data.

\bibliographystyle{plain}

[^1]: Most of this section is taken from [@espinoza2019].

[^2]: FLI's Landscape of AI Safety and Beneficence Research for research
    contextualization and in preparation for brainstorming at the
    Beneficial AI 2017 conference
    (<https://futureoflife.org/landscape/ResearchLandscapeExtended.pdf>),
    the Assuring Autonomy International Programme (AAIP) to develop a
    Body of Knowledge (BoK) intended, in time, to become a reference
    source on assurance and regulation of Robotics and Autonomous
    Systems (RAS),
    (<https://www.york.ac.uk/assuring-autonomy/research/body-of-knowledge/>)
    and Ortega et al (DeepMind) structure of the technical AI safety
    field
    (<https://medium.com/@deepmindsafetyresearch/building-safe-artificial-intelligence-52f5f75058f1>).

[^3]: From here the definition is taken from [@david2019understanding]
    under Creative Commons Attribution License 4.0.

[^4]: Definition taken from [@david2019understanding] under Creative
    Commons Attribution License 4.0.

[^5]: [paperswithcode.com](paperswithcode.com)

[^6]: Definition taken from [@david2019understanding] under Creative
    Commons Attribution License 4.0.

[^7]: Definition taken from [@david2019understanding] under Creative
    Commons Attribution License 4.0.

[^8]: From here the definition is taken from [@david2019understanding]
    under Creative Commons Attribution License 4.0.

[^9]: Also taken from [@david2019understanding] under Creative Commons
    Attribution License 4.0.

[^10]: Definition taken from [@david2019understanding] under Creative
    Commons Attribution License 4.0.

[^11]: <https://cmmc-coe.org/test/>
