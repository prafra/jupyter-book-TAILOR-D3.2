# Discrimination & Equity

## In brief

Forms of bias that count as discrimination against social groups or individuals
should be avoided, both from legal and ethical perspectives. Discrimination can
be direct or indirect, intentional or unintentional.

## More in Detail

Not all forms of *bias* (also known as *statistical discrimination*) are
problematic. Here we use the normative sense of *discrimination*, where
all forms of bias that count as discrimination are considered
problematic and should be avoided. This discrimination can be direct
(where a protected feature is intentionally used in the decision making
procedure). In such a case explainability tools such as feature
importance methods can help to detect whether a model's decisions are
based on the feature, in addition to the fairness metrics in the entry
on . Often, however, protected features are purposely not included among
the input variables, and so no direct discrimination will take place.
Instead, indirect discrimination (where there is direct discrimination
on features that strongly correlate with a protected feature, in such a
way that users with a socially salient value of the feature -- e.g.
women -- are worse off, cf. {cite}`lippert2013born`) is the most common type
of discrimination in machine learning systems. For ways to detect these
cases of indirect discrimination, see the [fairness metrics](./fairness.md).

This type of indirect discrimination is often unintentional.
Philosophical accounts thus disagree about the degree of intentionality
that is required for bias to count as discrimination: mental state
accounts {cite}`scanlon2009moral` require systematic animosity or preferences
towards a certain group. Such animosity need not be present among the
designers of the system, though it may be part of the reason for the
societal biases that filter through into the data. Other accounts
{cite}`lippert2013born,Loi2021` opt for weaker notions of intentionality,
where it is sufficient to enable the feature/group membership to play a
role in the decision making procedure. This clearly allows for the
(frequent) scenario where an algorithm has disparate impacts on groups
even when this was not the result of preferences/animosities of the
developers. Yet even then not all types of bias are considered
normatively problematic: a statistical bias that negatively impacts
smokers is not clearly a case of discrimination. So when is a bias a
case of discrimination?

An influential point of departure is the idea that biases should not be
on features outside of people's control
{cite}`lippert2007nothing, palmer2007insurance`. This might explain why the
paradigmatic cases of discrimination is when there is disparate
treatment based on gender, race, or ethnicity (cf. the entry {doc}`discrimination`), as we
cannot choose these. However, there are more features beyond our
control, as illustrated by the 'other people's choice principle'
{cite}`lippert2007nothing`: statistical patterns resulting from other
people's choices are not in our control either, and thus may lead to
discrimination. Consequently, charging higher premiums to a buyer of a
red car because on average drivers of red cars cause more accidents may
be seen as problematic. It violates the other people's choice principle,
as a buyer has no control over the driving of other car owners. On the
other hand, charging higher premiums to smokers does not violate this
principle, since smoking is a direct cause of higher health risks. In
practice, however, it is difficult to draw a clear border, as e.g.
socio-economic status impacts people's choices. Instead, some authors
{cite}`binns2018s` suggest to consider notions of {doc}`justice` as guiding the distribution of benefits and burdens resulting from the
use of AI. For example, luck egalitarianism would consider it
discriminatory to uphold biases which reflect factors of luck. Still,
while the exact confines of normatively problematic discrimination are
difficult to define, it is clear that gender, race, etc. are protected
features and that such discrimination needs to be detected and tackled.

Following the egalitarian principles of {cite}`Rawls,Moulin04`, some
authors address fairness from a multi-agent perspective
{cite}`JongTV08,Hao16` in automated decision making. Taking a welfare
perspective {cite}`HeidariFGK18` propose a family of welfare based measures
that can be integrated together with other fairness and performance
constraints. Following the same tracks, {cite}`JabbariJKMR17` considered the
temporal/sequential dimension and addressed fairness in the context of
Markov decision processes and reinforcement learning. Such
multi-objective and welfare approaches not only enforce human
intervention and social criteria to prevent unfair outcomes for some
users or stakeholders, but could be adapted to ensure equity and fair
trade-off between privilege and unprivileged groups.



## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was written by Stefan Buijsman and Miguel Couceiro.


