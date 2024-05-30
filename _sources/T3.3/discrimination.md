# Grounds of Discrimination

## In brief

International and national laws prohibit **discriminating on some explicitly defined grounds**, such as race, sex, religion, etc. They can be considered in isolation, or interacting, giving rise to multiple discrimination and intersectional discrimination.

## More in Detail

The Universal Declaration of Human Rights prohibit discrimination in
several grounds [^declaration]: 1) race, 2) skin colour, 3) sex, 4) language, 5)
religion, 6) political or other opinion, 7) national or social origin,
8) property, or 9) birth {cite}`assembly1948universal`, although
the list is not exhaustive.
By directly addressing these grounds, the
Declaration highlights the problematic of considering decisions or
regulations on them while leaves the door open to a more extensive view
by prohibiting as well discrimination based on *other grounds*.
By doing so, the Declaration implies that any difference in treatment or exercise with respect to the rights encompassed in the Declaration would have legal implications.
Therefore, grounds of discrimination should not be considered a closed and fixed list but an enumeration opened to debate and reflection as the circumstances and context require.
For example, the African Charter on Human and People's Rights prohibits discrimination in grounds of fortune, rather than property {cite}`africanunion` whereas the American Convention on Human Rights includes economic status {cite}`americanconvention` and the Charter of Fundamental Rights of the European Union adds the association with a national minority {cite}`charter2007`.


To this regard, *grounds of discrimination* encompass three different
motives on which decisions and policies should not be based (see also
the entry {doc}`equity`): (1) grounds innate to the individual such as race, gender,
age, disability, (2) grounds intrinsic to the individual freedom and
autonomy that is political belief or religion, and (3) grounds highly
founded on stereotypes or stigma and which are usually irrelevant for
social, economic, or politic interactions, as sexual orientation or
ethnicity) {cite}`gerards2013discrimination`. The use of any of these
grounds is often perceived as a lack of impartiality influenced by
negative and prejudiced reasons and emotions towards certain members of
the society. Prohibiting discrimination on these grounds aims to ensure
that the distribution of social goods and services do not respond to
subjective and irrational feelings, whether that turns out to be an
advantage or a disadvantage for the individual or group concerned.

*Sex* refers to a person's biological status, categorized as male,
female, or intersex; *gender* refers to the attitudes and behaviors that
a culture associates with a person's sex, categorized as masculine,
feminine and transgender (gender identity different from sex assigned at
birth or non-binary); *sexual orientation* refers to the sex of those to
whom one is sexually and romantically attracted, categorized as
homosexual, heterosexual, and bisexual. See {cite}`lgb2011` for a
psychological discussion of the differences between the terms,
{cite}`Case1995` for a discussion with reference to the United States (U.S.)
anti-discrimination law, and {cite}`fra2015protection` for a comparative
analysis on anti-discrimination European Law. A country profile report
on the legal rights of lesbian, gay, bisexual and transgender and (LGBT)
people is published yearly[^lgbt] by Human Rights Watch. Human-Computer
Interaction research is also addressing the extent to which AI systems
"express gender and sexuality explicitly and through relation of
experience and emotions, mimicking the human language on which they are
trained" {cite}`DBLP:conf/cui/EdwardsCP21`.

*Race* is a social construct to categorize people into groups. The term
is controversial, and with little consensus on its actual meaning.
{cite}`Blank04` summarizes biological and social concepts of race,
and discuss U.S. categorizations of races used for data collection,
e.g., in census data. *Ethnicity* refers to self-identifying groups
based on beliefs concerning shared culture, ancestry and history. The
distinction between *race* and *ethnic* grounds is, nonetheless, a
provocative issue primarily in Europe where after the Second War World
the notion of *race* become some sort of a *taboo*. By consequence, the
lacking of words, academic work, and policies addressing *race
(un)justice* has also resulted on a downplay of race grounds of
discrimination and the indistinct use of *ethnic origin* as *race* with
mislead intentions {cite}`algorithmwatch`.

Legislations and research studies have evolved with a different focus on
vulnerable groups, sometimes restricting themselves to specific
settings, including credit and insurance, sale, rental, and financing of
housing, personnel selection and wages, access to public accommodation,
and education. For instance, discrimination against Afro-Americans is
dealt with to a large extent by studies from the U.S., whilst
discrimination against Roma people has been mainly considered by E.U.
studies.

Although the aforementioned grounds for discrimination are typically
considered separately, the interaction of multiple forms of
discrimination has been receiving increasing attention
{cite}`EUMultiple,multiple44`. An elderly disabled woman for example, could
be discriminated against for being above a certain age, because she is a
woman, because she is disabled, or any combination of these. *Multiple*
discrimination comes into play when a person is discriminated against on
the basis of different characteristics *at different times*: each type
of discrimination works independently, according to distinct
experiences, and multiple discrimination refers to their cumulative
impact. When different grounds operate *at the same time*, then this is
known as *compound* or *intersectional* discrimination. Compound
discrimination (sometimes called *additive multiple discrimination*)
occurs when each ground *adds* to discrimination on other grounds, for
example migrant women experiencing both under-employment (such as
migrants compared to local residents) and lower pay (such as female
workers compared to male workers). Intersectional discrimination occurs
when concurrent acts of discrimination result in a specific and distinct
form of discrimination {cite}`Fredman16`. For example, {cite}`Makkonen02` reports
the case of Afro-American women stereotypes which when taken in
isolation cover neither women nor Afro-Americans.

Grounds of discrimination are key inputs in the design of fair AI
systems: fairness metrics, for instance, rely on comparing models'
performances across protected and unprotected groups. We refer to the
entries on and for details. Here, we concentrate on the problem of
faithfully representing grounds of discrimination in data, by
distinguishing the coding of human identity in raw data (*datafication*)
and the representativeness of grounds of discrimination in data
(*representation bias*).

For instance, if gender is coded with a binary feature (male/female),
then any further discrimination analysis is limited to contrasting only
such two groups, excluding non-binary people. There is then the need for
a more elaborate representation of human identity in raw data, e.g,
using ontologies for concept reasoning {cite}`DBLP:journals/jamia/KronkD20`.
Moreover, the categories used to encode grounds of discrimination may
embed forms of structural discrimination, which is hidden when features
are considered in isolation, but made apparent when connected with other
features in a knowledge graph {cite}`DBLP:journals/corr/abs-2111-03687`. The
issue of *source criticism* {cite}`Koch2020`, which is central historical and
humanistic disciplines, is still in its infancy in the area of big data
and AI. Source criticism attains at the provenance, authenticity, and
completeness of data collected, especially in social media platforms.
For instance, the mechanisms of social software, such as the option
given to users to identify their gender as binary, result into
functional biases {cite}`DBLP:journals/fdata/Olteanu00K19` of the data
collected. Beyond the complexity of datafication, the representiveness
of grounds of discrimination in datasets
{cite}`DBLP:journals/corr/abs-2203-11852` also affects discrimination and
diversity analyses, and the fairness of AI models trained over those
datasets (see also the entry on {doc}`bias`).

Most of the grounds of discrimination fall in the category of sensitive
personal data whose collection and processing is prohibited under
several privacy and data protection laws, unless certain exceptions
apply. For example, the grounds of race, ethnic origin, sexual
orientation, political stances, religious beliefs, and trade union
membership are considered special categories of personal data under the
European General Data Protection Regulation {cite}`gdpr`. Likewise, the
California Privacy Rights Act (CPRA) will include as sensitive
attributes, among other, consumer's racial or ethnic origin, religious
or philosophical beliefs {cite}`CPRA`, while the Virginia Consumer Data
Protection Act (VCDPA) will add to those attributes, the ground of
mental or physical health, sexual orientation, or citizenship or
immigration status {cite}`VCDPA`. From a regulatory perspective, the
restriction towards the collection and processing of sensitive personal
data intends to minimize the possibilities of algorithmic systems to
discriminate people based on intrinsic or innate attributes of the
individual. However, some criticism have arisen towards this perspective
as more voices defend the need to use sensitive attributes to ensure the
non-discriminatory nature of algorithmic models {cite}`vzliobaite2016using`.
The European Proposal for Regulating Artificial Intelligence (Artificial
Intelligence Act) seems to have reflect on this position as it will
introduce a exception allowing, to the extent that it is strictly
necessary for the purposes of ensuring bias monitoring, detection and
correction in relation to the high-risk AI systems, the processing of
special categories of data {cite}`aiact`.

Discrimination grounds in datasets can be be the output of an inference.
For instance, gender may be explicitly given (e.g., in a registration
form) with consent to a specific usage (e.g., personalization), or it
can be inferred using supervised learning
{cite}`DBLP:journals/peerj-cs/SantamariaM18`. A growing number of AI
approaches can infer people's personality traits
{cite}`DBLP:journals/taffco/VinciarelliM14`, to be used e.g., for
personalization and recommendation purposes. To some extent, even in
cases where the system is blinded to protected attributes, inferences
can lead to discriminatory results as the system finds correlations
directly related to grounds of discriminatory. Inferences can,
therefore, be quite problematic because they can reinforce the
historical disadvantage and inequalities suffered by certain members of
the society {cite}`xenidis2020tuning`. As the current legal protections rest
on the restricted access to data reveling the belonging of an individual
to a protected group or prohibition of use of such data to motivate a
decision, the access and use of such information indirectly creates a
threat to individuals' rights {cite}`barocas2014data`. For this reason, the
correctness of such inferences can be crucial on attributed grounds of
discrimination and, consequently, on decisions and fairness analyses.
Despite inferences offer new possibilities for biased and invasive
decision-making, the legal status of inferred personal, both with
respect to data protection and anti-discrimination laws, is quite
debated {cite}`Wachter2019`.


## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was written by Alejandra Bringas Colmenarejo and Salvatore Ruggieri.

[^declaration]: Protected group, protected grounds and prohibited grounds are also used as synonymous of grounds of discrimination.
[^lgbt]: For 2021, see <a href="https://www.hrw.org/video-photos/interactive/2021/04/23/country-profiles-sexual-orientation-and-gender-identity" target=_blank>the Human Right Watch World Report</a>.
