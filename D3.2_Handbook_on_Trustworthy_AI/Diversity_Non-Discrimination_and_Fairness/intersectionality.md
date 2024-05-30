# Intersectionality

## In brief

**Intersectionality** focuses on a specific type of bias due to the combination of sensitive factors. An individual might not be discriminated against based on race or based on gender only, but she might be discriminated against because of a combination of both. Black women are particularly prone to this type of discrimination.

## More in Detail

Historically, the topic of intersectionality has been influenced by several studies in the late twentieth century about violence against dark skinned women {cite}`crenshaw1990mapping`. On one hand, feminist efforts focused on politicizing experiences of women and on the other hand, antiracist efforts focused on politicizing experiences of people of color. However, both types of activists have frequently proceeded as though the issues and experiences they each detail occur on mutually exclusive terrains. 
Consequently, this intersectional identity as both women and with dark skin within a discourse targeting to respond to one or the other, women of color are marginalized within both. That is, the intersection of racism and sexism in black women's lives cannot be captured by looking at the race or gender dimensions separately.

In 2018, the Gender Shades project {cite}`genderShadesProject, buolamwini2017gender, buolamwini2018gender` described the first intersectional evaluation of face recognition systems. Instead of evaluating accuracy
by gender or skin type alone, Buolamwini et al.~examined four intersectional subgroups: dark-skinned females, dark-skinned males, light-skinned females, and light-skinned males. The three evaluated commercial gender classifiers, namely, Microsoft Cognitive Services Face {cite}`microsoftFace`, IBM Watson Visual Recognition {cite}`IBMVisual`, and Face++ (a computer vision company headquartered in China {cite}`FacePlusPlus`), had the lowest accuracy on dark-skinned females. More precisely, they had the highest error rates for all evaluated gender classifiers ranging from $20$ to $35\%$.

```{figure} ./Interaction.pdf
---
name: fig:interaction
width: 700px
align: center
---
Interaction Bias, where $A$ and $B$ are sensitive variables and $Y$ is an outcome.
```

Studying the problem of discrimination from the lenses of causality, intersectionality can be captured by the concept of interaction {cite}`interactionVanderweele`. Interaction is observed when two causes of the outcome interact with each other, making the joint effect smaller or greater than the sum of individual effects. Interaction is graphically illustrated in Figure {numref}`{number}<fig:interaction>`, where $A$ and $B$ are sensitive attributes and $Y$ is the outcome[^binary]. Note that regular DAGs are not able to express interaction. Figure `{number}<fig:interaction>` employs the graphical representation proposed by~\cite{weinberg2007can}. The arrows pointing to arrows instead of nodes account for the interaction term.

The interaction term coincides with the portion of the effect due to intersectionality and can be expressed as follows:<br>
$\textit{Interaction}(A,B) = P(Y_1|a_1, b_1) - P(Y_1|a_0, b_1) - P(Y_1|a_1, b_0) + P(Y_1|a_0, b_0)$<br>

In practice, intersectionality presents some challenges. The first challenge is related to the complexity of data collection and analysis. In other words, collecting and analyzing data on intersecting factors can be challenging due to limited resources, methodological constraints, and privacy concerns. Second, groups that are not (yet) defined in anti-discrimination law may exist and may need protection {cite}`wachter2019right`.

More generally, there are three practical concerns along the machine learning pipeline related to intersectionality in a fairness context {cite}`wang2022towards`. The first problem is related to which factors to consider when training models. It is advised to evaluate the most granular intersecting factors in the dataset while integrating domain knowledge with experiments to understand which are best to include when training models. The second problem concerns the challenge of handling increasingly small groups of individuals. Due to additional ethical considerations, it is advisable to refrain from directly applying conventional machine learning techniques to imbalanced data. Instead, exploring inherent structures among groups with shared identities is encouraged.
The third problem is related to evaluating a large number of sub-groups. In the context of binary attributes, fairness assessment often involves comparing group differences using performance metrics derived from the confusion matrix. When dealing with more than two groups, evaluation metrics have a similar structure, albeit more generalized. 
They are typically expressed in relation to the maximum disparity (or ratio) of a performance metric either between one group and all others {cite}`guo2021detecting, kearns2018preventing, yang2020fairness` or between two specific groups{cite}`foulds2020intersectional, ghosh2021characterizing`.
Hence, methods are proposed for conducting pairwise comparisons more judiciously and introducing supplementary metrics to capture broader algorithmic trends that existing metrics may overlook {cite}`wang2022towards`.



## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was written by Karima Makhlouf and Sami Zhioua.

[^binary] Without loss of generality, all three variables are assumed to be binary with sets of values $\{a_0,a_1\}$, $\{b_0,b_1\}$, and $\{y_0,y_1\}$, respectively.
