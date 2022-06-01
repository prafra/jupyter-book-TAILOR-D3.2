# Negative side effects


## In brief

**Negative side effects** are an important safety
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

## More in detail

**Negative Side Effects** are unanticipated or
unintended effects caused by an AI system during operation. Negative
side effects are a key issue within the AI safety literature
{cite}`amodei2016` and typically stem from the difficulty of fully
articulating everything that we want the AI system *not* to do. Negative
side effects can be of two kinds, related to some preservation of the
environment or related to the use of resources. For instance, a clumsy
incompetent agent may break everything around it
{cite}`saisubramanian2020avoiding`, not preserving things that should be
unrelated to the goal. On the other hand, a very proficient agent may
exhaust all available resources and disrupt any other agent (machine or
human) that interferes with its goals {cite}`yampolskiy2018artificial`.
Recognising these two different causes for side effects is crucial for
the design of safer AI systems.

There are a number of proposed methods for measuring the negative side
effects caused by a system {cite}`armstrong2017,leike2017,turner2020`,
but a recurring theme is based on estimating counterfactual scenarios in
which the system was not present (or acted differently), and comparing
the changes in the state of the world. Alternatively, in some approaches
for mitigating side effects, these are set externally (marked safe
areas) or incorporated as a "secondary objective"
{cite}`saisubramanian2020multi` for which trade-offs are found. But in these
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
{cite}`garcia2015comprehensive`, dealing with side effects is still mostly
unexplored, especially in realistic situations where the agent does not
have any feedback about side effects during training or operation. Also,
the analysis of AI safety in reinforcement learning has usually been
conducted with toy scenarios, not having the complex interaction of the
real world. SafeLife {cite}`safelife` is an exception in this landscape, as a
very rich and full *ecosystem* where many complex behaviours and effects
can be analysed.


```{figure} ./SafeLifelevel7.png
---
name: safelife
width: 600px
align: center
---
An example task instance from SafeLife. The agent  ![alt](InlineSprites/agent.png "Title") must create life
structures  ![alt text](InlineSprites/greylife.png "Title") in the designated blue positions before moving to the goal  ![](InlineSprites/goal.png).
Ideally the agent should not disturb the green life cells ![](InlineSprites/greenlife.png).
```

Fig.  {numref}`{number} <safelife>` gives the visual representation of a state
of a SafeLife instance. There we can see that achieving the goals can be
done carefully so that the green life cells are not disturbed. The real
challenge is when the system is not informed explicitly (as part of the
reward or a constraint) that the green life cells should not be
disturbed. In this case, only agents that try to be minimise changes
that are not necessary for the goals will be expected to have low side
effects.





## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

---
 
This entry was written by Jose Hernandez-Orallo, Fernando Martinez-Plumed, Santiago Escobar, and Pablo A. M. Casares.
