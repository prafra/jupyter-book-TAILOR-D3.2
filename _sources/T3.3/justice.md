# Justice

## In brief

**Justice** encompasses three different perspectives: (1) *fairness* understood as the fair treatment of people, (2) *rightness* as the quality of being fair or reasonable, and (3) a legal system, the scheme or system of law. Justice can be distinguished between *substantive* and *procedural*.

## More in Detail

It is commonly accepted that, *justice* entails "the proper
administration of the law; the fair and equitable treatment of all
individuals under the law" {cite}`lehman2004west`. Therefore, *justice*
encompasses three different perspectives, (1) *fairness* understood as
the fair treatment of people, (2) *rightness* as the quality of being
fair or reasonable, and (3) a legal system, the scheme or system of law,
in which every person receives his/her/its due from the system,
including all rights, both natural and legal {cite}`hill2002people`.
Artificial Intelligence (AI) can be a tool for administering justice in
the legal system, or it can itself be subject to the requirements of
fairness and rightness when used for automated decision making (ADM). In
the former case, AI can be adopted at several levels of autonomy
{cite}`Eliot2021Identifying`, e.g., from no automation to superhuman
autonomous AI for legal reasoning. For a state of the art of the use of
Machine Learning (ML) in the criminal justice system (mainly in the
United States), see {cite}`Berk2021`. Several books and newspapers
commentaries warn about the risks of using AI for justice administration
{cite}`Forrest21`. In the latter case, the design of AI-based systems can
benefit from discussion and theories of justice in the legal and ethical
disciplines. However, the above conceptualization of *justice* has given
rise to an endless and ongoing debate regarding whether justice is an
inherent component of the law, not separate or distinct from it, or is
simply a moral judgment about law {cite}`d1992connection`. In essence, the
debate considers whether justice understood as fairness and rightness is
independent from the law, or to what extent the *law* includes
considerations of justice and the legal system simply applies justice to
human conflicts. In conclusion, the concept of *justice* is as central
to legal theory as it is difficult to define.

Nevertheless, a range of different components or categories of justice
have been defined, both in the philosophical literature {cite}`sep-justice`
and in the legal literature {cite}`Susskind19`. These can be understood along
several distinctions, starting with one between *substantive* and
*procedural* justice. This is the difference between considering justice
in terms of the outcomes which have to meet certain standard in order to
be just {cite}`rawls2020theory`, versus considering justice in terms of a
procedure which meets certain standards (and possibly considering the
outcomes of any such procedure as being just regardless of the resulting
distributions {cite}`nozick1974anarchy`). It is, however, common to consider
procedural justice partly in terms of the results (e.g., a trial
procedure is just if it -- at least -- mostly acquits the innocent and
punishes the guilty). As such, substantive justice is the main notion to
discuss here, although the use of AI in procedures also affects
questions of procedural justice.

Substantive justice in turn can be viewed in different ways. First,
there is a question of whether one focuses on *distributive* justice or
on *corrective* justice. Distributive justice deals with the
distribution of the benefits and burdens of social cooperation
{cite}`rawls2020theory`. These can be *comparative*, such as the theory of
(strict) egalitarianism which requires that resources are distributed to
minimize overall inequality {cite}`hirose2014egalitarianism` and other
versions of egalitarianism. For example, on Luck egalitarianism (and,
closely related, Equality of Opportunity) inequalities in the final
distribution may be allowed only in so far as they are not the result of
luck or a difference of opportunity
{cite}`anderson1999point,wolff2010fairness`. By far the most influential,
however, has been Rawls' view of Justice as Fairness, which combines a
requirement of equality of opportunity with the difference principle:
unequal distributions have to satisfy a min-max condition where "they
are to be to the greatest benefit of the least advantaged members of
society." {cite}`rawls1993political` Alternatively, distributive notions
of justice can be *non-comparative*. Sufficiency principles
{cite}`brock2018sufficiency`, requiring that everyone receives a minimally
sufficient amount of resources are a clear example of a distributive
justice notion that doesn't involve comparisons between individuals.
Desert-based principles {cite}`moriarty2018desert`, which hold that resources
should be allocated based on what individuals deserve can also be
non-comparative (if they specify absolute amounts based on what one
deserves, as opposed to a share of the total). Views thus differ on what
the right principles are for distributive justice. Furthermore, it is
interesting that most of these principles have only a limited overlap to
*fairness* in ADM {cite}`kuppler2021distributive` (cf. the entry on {doc}`fairness`).

Where distributive justice focuses on the just distribution of goods,
corrective justice concerns the rectification of wrongs or the undoing
of transactions which can be either voluntary (contract) or involuntary
(when defrauded or a victim of misrepresentation)
{cite}`ripstein2003division,weinrib2012idea`. This differs from
distributive justice, as corrective justice first requires a wrong that
needs to be corrected, and the correction might violate the ideal
distribution of goods according to distributive justice principles. As
such, disagreements exist over the priority to be placed between these
two principles: is corrective justice merely a way to achieve
distributive justice or is corrective justice normatively prior?
{cite}`walt2006eliminating` However this issue is settled, it is a matter of
fact that corrective justice is an important part of current legal
systems. Similarly, *retributive* justice {cite}`sep-justice-retributive`,
which focuses on the compensation of the victim of criminal behaviour
and the punishment of the lawbreaker, is crucial to our current systems.

In all these cases procedures are followed to make decisions on the
distribution of resources, the appropriate corrections and potential
punishments. *Procedural* justice relates to the normative conditions
that these procedures have to meet. As such, it encompasses principles
of legality, proportionality, effective remedy, fair trial, presumption
of innocence and right of defence
{cite}`charter2007,blader2003four,meyerson2018procedural,lee2019procedural`.
Procedural justice is also affected by the use of AI, as this changes
procedures and so new standards have to be found for when a procedure
including AI is just. Such standards are also needed for transparency,
and the notion of procedural justice has been used to propose such a
standard by {cite}`loi2021transparency`, who argue that what matters to
determine the justness of an algorithm is the goals of the algorithm as
well as how effectively they are met. That is intended to allow an
evaluation of the justness of the procedure, and thus of the use of the
algorithm. For instance, {cite}`Minhao2022` conducted experiments involving
laypeople, that showed a "fairness gap" between human judges and AI
robot judges. Such a gap is reduced by enhancing the interpretability of
AI decisions.

Part of the question of what procedures are just is that of which
political procedures should be decided on. *Political* justice addresses
the foundational issues of political rights and responsibilities
embedded in constitutional theory and how individuals shall share the
control over the shape of the constitution[^constitution] {cite}`sobel2015oxford`.
*Social* justice, on the other hand, addresses how members should
compare under the basic structure of the society {cite}`sobel2015oxford`,
and, its "primary task is not so much to save the computational
infrastructure AI and ICTs rely on but rather to defend society"
{cite}`DBLP:conf/iconference/TachevaNA22`. This concern decisions about the
broad shape of society and thus cannot readily be solved with fair ML
tools. Yet algorithms can help in the implementation of these decisions.
As such, *justice* can be seen to differ from *fairness*: its scope is
often broader, and it is not restricted to questions of equality between
different groups to which an algorithm is applied. See e.g.,
{cite}`Taylor2017` for a discussion of *data justice*, pertaining to "the way
people are made visible, represented and treated as a result of their
production of digital data", and the literature on organizational
justice theory {cite}`Bankins22,DBLP:journals/hhci/RobertPMKA20` for the
notion of *interactional justice* pertaining to how workers are treated
with respect and dignity (*interpersonal justice*) and how they are
provided with explanations of business process and outcomes
(*informational justice*). Still, the design of AI systems intersects
with all of the notions of justice discussed here.

The increased use of AI and ADM reflects a tendency to *solutionism*
{cite}`Morozov13`, where technical solutions are offered to solve all social
and economic problems {cite}`zavrvsnik2021algorithmic`. However, unfair,
discriminatory, and unjustified decisions affecting different aspects of
individuals' economy and private life has encouraged a critical
reflection on questions regarding "what, then, do we talk about when we
talk about governing algorithms?" {cite}`barocas2013`. Likewise, the
proposed *algorithmic justice* {cite}`marjanovic2021theorising` strives to
address these unintentional effects provoked by the use of ADM for the
allocation of welfare services. This novel conception of justice,
founded on Nancy Fraser's *abnormal justice theory*, defends "the need
to expand our collective understanding of justice, beyond issues of
equal access to, and equal distribution of justice"
{cite}`fraser2008abnormal,fraser2010injustice` as referred in
{cite}`marjanovic2021theorising` in order to recognise, debate,
diagnose and address harmful effects of ADM in the allocation of
transformative services {cite}`marjanovic2021theorising`. That being the
case, (un)just ADM are more and more scrutinised under the lens of
*procedural justice* as several studies
{cite}`lind1988social,colquitt2015measuring,bussone2015role` "suggest
that people do not only care about whether the outcome of a decision
benefits them, but also whether it meets standards of justice"
{cite}`binns2018s`. To this regard, AI's *explainability and
transparency* would be crucial to justify and explain the algorithmic
decisions and decision-making process and therefore ensure the
accountability intelligibility of the decisions, and, by extension, of
the process (a principle known as *open justice* when referring to the
judicial system {cite}`Pah2022`).

## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

---

This entry was written by Alejandra Bringas Colmenarejo, Stefan Buijsman, and Salvatore Ruggieri.

---

[^constitution]: See <a href="https://www.europeansocialsurvey.org/data/themes.html?t=justfair" target=_blank>the European Social Survey page</a> for a survey on
perceptions of political justice in Europe.


