# Auditing AI

## In brief



## More in Detail

One of the measures to ensure that AI is used responsibly is the
initiation of auditing practices as they facilitate to verify if the
system works as intended.

Audits can be conducted either in-house or by external parties. The
former requires internal evaluation regarding whether systems are fit,
the human elements involved with the system are appropriate and
monitored, and the technical elements of the system are in perfect
condition and function correctly {cite}`lovelace2020examining,kazim2021ai`.
The latter involves both regulators and third-parties verifying
compliance {cite}`cobbe2021reviewable`. Interestingly, critical external
audits encompasses "disparate methods of journalist, technicians, and
social scientist who have examined the consequences of already-deployed
algorithmic systems and who have no formal relationship which the
institutions designing or integrating the audited systems"
{cite}`metcalf2021algorithmic`. Well-known examples of these practices
such as the Propublica's examination of Northpoint recivism prediction
API {cite}`larson2016we` or the Gender Shade Project {cite}`buolamwini2017gender`,
have played a crucial role pointing out harmful application of algorithm
systems to draw the attention of the society and require companies an
active role setting out governance and accountability mechanism.

As a result of these social demands, internal governance mechanisms
{cite}`metcalf2021algorithmic` have been introduced from within the own
companies that design and deployed the algorithmic systems. The goal is
to propose technical and organisational procedures, among which are
detailed frameworks for algorithm auditing {cite}`raji2020closing`, able to
identify and address possible risk and impacts while ensuring robust and
trustful accountability. In essence, precise and well-documented audits
facilitate later scrutiny offering records on the reasons for the audit
to be initiated, the procedures that were followed as well as the
conclusions that were reached and, if carried out, the remedies or
measures that were adopted.

To this regard, more and more voices consider audits as indispensable
accountability mechanism to ensure the compliance of AI systems along
their life-cycle with the different applicable legislation, concerning
in particular privacy and data protection law {cite}`casey2019rethinking`.
Moreover, AI auditing can benefit from extensive literature in more
mature disciplines, such as audit studies in social sciences
{cite}`DBLP:conf/eaamo/VecchioneLB21` and empirical economics
{cite}`DBLP:journals/ker/RomeiR14`. Audits facilitate private entities the
provision of documentation when requested by public bodies, favouring a
systematic governance {cite}`kaminski2020algorithmic` of AI systems through a
general transparency and enforcement regime. This joint effort between
public and private institutions would, in turn, result in collaborative
governance scheme {cite}`kaminski2020algorithmic`.

The upcoming EU Artificial Intelligence Act can be seen as a proposal to
establish a Europe-wide ecosystem for conducting AI auditing
{cite}`mokander2021conformity` and in line with that idea more and more
research is done on auditing procedures for algorithms (for reviews see
{cite}`koshiyama2021towards, metaxa2021auditing`). For example,
{cite}`raji2020closing` propose a framework for internal AI auditing which
includes both ethical aspects (a social impact assessment and ethical
risk analysis chart) and technical audits (such as adversarial testing
and a Failure Modes and Effect Analysis). Such audits are often
supported by technical documentation, such as the Datasheets for
Datasets proposal {cite}`gebru2021datasheets` to maintain information on
datasets used to train AI systems. Such documentation can both help to
ensure that AI systems are deployed for tasks in line with the data they
were trained on and help to spot ethical risks stemming from the data
{cite}`boyd2021datasheets`, such as [biases](./bias.md).

Ethical risks can also be the sole focus of AI audits, as in
ethics-based auditing (proposed for AI in {cite}`mokander2021ethics`). While
still in development, several options are emerging where: "functionality
audits focus on the rationale behind decisions; code audits entail
reviewing the source code of an algorithm; and impact audits investigate
the types, severity, and prevalence of effects of an algorithm's
outputs." {cite}`mokander2021EBA` For these audits in particular determining
what is measured can be a challenge, as it is difficult to define clear
metrics on which ethical aspects of AI systems can be evaluated.
*Fairness metrics* (cf. the entry on ) can certainly help here, but as
discussed there is a difficulty in the selection of the right metric and
even then there are limitations and trade-offs with other metrics. In
addition, for the integration of AI ethics in ESG (Environmental, Social
and Governance) reporting towards investors {cite}`minkkinen2022investors`
such fairness metrics need not give sufficient insights into whether
algorithms are used responsibly at an organisational level. Existing ESG
criteria for organizational audits may help here, as well as work on
KPIs for Responsible Research and Innovation {cite}`kwee2021responsible`.
Despite all this work on metrics, it is however still an open question
to what extent ethics can be captured in numbers the way other aspects
of audits are, with some arguing that it is impossible to develop
benchmarks for how ethical an AI system is {cite}`lacroix2022metaethical`.
Instead, they argue, the focus should be on values and value trade-offs.

Z-Inspection, another auditing framework proposed based on the European
High Level Expert Group's Guidelines for Trustworthy AI
{cite}`smuha2019ethics`, takes values as its starting point {cite}`zicari2021z`.
As can also be seen in a case study for the framework involving an
algorithm that recognizes cardiac arrests in emergency calls
{cite}`zicari2021assessing` this framework proceeds from a wide
identification of stakeholders and their values to the analysis of
(socio-)technical scenario's to reach an identification and
(potentially) resolution of ethical, technical and legal issues of an AI
system. Ultimately this still depends on the translation of values into
metrics, and so the main challenge of developing such metrics stands
regardless of one's auditing approach.

Standards represent a natural framework for the proceduralization of
audits. Certification by neutral third party states compliance to
certain standards as the result of auditing. Several draft proposals are
being prepared which include (at least implicitely) elements for
conducting audits, such as the following:

-   [ISO/IEC TR 24027:2021](https://www.iso.org/standard/77607.html) -
    Artificial intelligence (AI) --- Bias in AI systems and AI aided
    decision making.

-   [IEEE 7010-2020](https://standards.ieee.org/ieee/7010/7718/):
    Recommended Practice for Assessing the Impact of Autonomous and
    Intelligent Systems on Human Well-being.

-   [IEEE P2863](https://standards.ieee.org/ieee/2863/10142/) -
    Recommended Practice for Organizational Governance of Artificial
    Intelligence.

-   [IEEE CertifAIEd](https://engagestandards.ieee.org/ieeecertifaied.html) --
    Ontological Specification for Ethical Accountability

-   [IEEE CertifAIEd](https://engagestandards.ieee.org/ieeecertifaied.html) --
    Ontological Specification for Ethical Algorithmic Bias.

-   [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework).

However, there is not yet a formal professional standard to guide
auditors of AI systems, yet some <a href="https://ec.europa.eu/futurium/en/system/files/ged/auditing-artificial-intelligence.pdf" target=_blank>guidelines</a> exist.


## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

---

This entry was written by Alejandra Bringas Colmenarejo, Stefan Buijsman, and Salvatore Ruggieri.


