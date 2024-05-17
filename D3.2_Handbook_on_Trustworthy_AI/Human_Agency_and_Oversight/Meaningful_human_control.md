# Meaningful human control

## In brief
**Meaningful human control** is the notion that aims to generalize the traditional concept of operational control over technological artifacts to artificial intelligent systems. It implies that artificial systems should not make morally consequential decisions on their own, without appropriate control from responsible humans.

## More in Detail

The notion of meaningful human control has its origins in the discussions on lethal autonomous weapon systems (LAWS), specifically in regards to life-or-death decisions that such systems could in principle make. Avoiding ethical issues related to autonomous decision making by artificial agents requires that humans, and only humans, have control of and are accountable for the use of lethal force {cite}`article36_2014`. The concrete implications of this requirement are still debated, with proposals range from calls for a full ban of LAWS  {cite}`article36_2015` to suggestions on governance, implementation, and use of such systems that can contribute to meaningful human control  (e.g.  {cite}`roff2016meaningful`,  {cite}`horowitz2015`).
While ethical issues associated with the lack of human control are perhaps most apparent for autonomous weapon systems, they extend far beyond the military domain, to a wider class of human-AI systems that make decisions with moral implications. At the time of writing, researchers have approached meaningful human control in the contexts of automated driving systems  {cite}`heikoop2019human`  {cite}`calvert2020gaps`, medical decision support systems {cite}`braun2021primer`, unmanned aerial vehicles {cite}`steen2022meaningful`, among other domains. Many of these domain-specific operationalizations rely on a philosophical account of meaningful human control proposed by {cite}`santoni2018meaningful`. This account builds on the concept of “guidance control” {cite}`fischer1998responsibility` and provides two necessary conditions for meaningful human control. The tracking condition requires that the decision-making system tracks and responds to all human reasons (i.e., values, norms, intentions) relevant in given circumstances. The tracing condition requires that any action/decision of the human-AI system should be traceable to at least one human within the system who has proper moral understanding of the situation and the effects of the system in that situation. 

Tracking and tracing, as well as several alternative domain-specific accounts, provide conceptual frameworks for meaningful human control. Making these concepts less vague and more relatable to design and engineering practice is however very challenging {cite}`crootof2016meaningful`. In {cite}`cavalcante2022meaningful` an attempt to close this gap between theory and practice is made by proposing four actionable properties that can be addressed throughout the system’s lifecycle:
-   Property 1: A system in which humans and AI algorithms interact should have an explicitly defined domain of morally loaded situations within which the system ought to operate. 
-   Property 2: Humans and AI agents within the system should have appropriate and mutually compatible representations.
-   Property 3: Responsibility attributed to a human should be commensurate with that human’s ability and authority to control the system.
-   Property 4: There should be explicit links between the actions of the AI agents and actions of humans who are aware of their moral responsibility.


## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was written by Arkady Zgonnikov and Luciano C Siebert.
