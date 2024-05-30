# Bias Conducive Factors

## In brief

**Bias conducive factors** are aspects of individuals and institutions that lead to biases in data-driven models by influencing data and tech development. This entry presents a selection of bias conducive factors in algorithmic hiring.

## More in Detail

We present a selection of bias conducive factors distinguishing between 1) overarching factors, 2) institutional biases, 3) individual preferences, and 4) technology blindspots.


### Overarching factors

Overarching factors are fundamental biases interacting with all other factors and leading to worse algorithmic outcomes for disadvantaged groups.

*Stereotypes*. Stereotypes, shaped by culture, socialization, and experience, are commonly held beliefs about groups based on shared characteristics, impacting their perceived suitability for certain roles. Acquired early and often activated unconsciously {cite}`jaxon2019acquisition,moskowitz2012implicit`, stereotypes persistently influence individuals' lives, both descriptively and prescriptively {cite}`ellemers2018:gs`. Consequently, they mold expectations regarding personal and others' qualities, priorities, and needs, particularly in the context of work {cite}`bobbitt2011:gd,undp2023breaking`. For instance, men are typically associated with *agency* (leadership and goal achievement), while women are associated with \emph{communion} (warmth and caregiving), leading to widespread effects on gender roles and expectations in employment {cite}`eagly2019:gs,heilman2012gender`.

*Proxies*. Sensitive attributes are normally not used directly as input features to algorithms. Despite this fact, sensitive attribute information is still available to data driven methods through variables that are strongly correlated with sensitive attributes, referred to as proxies. In algorithmic hiring, for example, video interviews and resumes encode information on gender and race  {cite}`deshpande2020mitigating,dearteaga2019bias`.

### Institutional biases 
Institutional biases stem from practices, habits, and norms of institutions.

*Horizontal segregation*. Horizontal segregation, a significant aspect of job allocation, influences hiring decisions and future workforce dynamics. Past experience is a key determinant of job suitability {cite}`fuller2021hidden`. This segregation involves disparities in employment rates among industries due to factors like gender and race {cite}`bloksgaard2011masculinities,tesfai2020dimensions` (see also the entry {doc}`./segregation`). Gender biases, rooted in enduring stereotypes about traits like agency and communion, contribute to pronounced gender imbalances across various regions. Field experiments consistently reveal discrimination against individuals in industries dominated by the opposite gender {cite}`riach2002field,rich2014field`.

*Vertical segregation*. Vertical segregation refers to disparities in career advancement toward leadership roles, traditionally examined through a gender lens {cite}`cotter2001glass,eige2020gender`. However, recent research extends this concept to non-binary individuals, racial minorities, and intersectional identities {cite}`davidson2016gender,hegde2022race`. These disparities, when formalized into data, perpetuate wage gaps {cite}`rus2022closing` and the underrepresentation of diverse groups in high-ranking positions.

### Individual preferences
Individual preferences shaping generalized patterns for protected groups are presented in this section. Caveat: Categorizing bias in this manner doesn't assign individual responsibility or justify discrimination. Instead, it underscores how apparent individual choices often stem from broader recurring patterns linked to protected attributes.

*Job satisfaction*. Job satisfaction plays a key role in job commitment {cite}`bedeian1992age,shields2002racial`. However, historically marginalized groups—like transgender, nonbinary, women, Black, and disabled workers—are more prone to workplace discrimination and harassment {cite}`schneider1997job,shields2002racial,waite2021should`. This issue can be seen in data sets showing lower job tenure for these groups, potentially leading to biases in algorithms designed to maximize tenure to cut hiring costs and retain talent.

*Differences in salary negotiation*. Differences in salary negotiation between men and women are well-documented, including variations in their propensity and approach {cite}`leibbrandt2015women,gray2019career`. Explanations range from differences in risk aversion to perceived chances of success {cite}`gray2019career,hernandez2019review`. Despite appearing as an individual outcome for female candidates, unsuccessful salary negotiations also reflect an unfair status quo that affects group expectations {cite}`gray2019career`.

### Technological blindspots
Technological blindspots are introduced by biased components unreflectively integrated into larger algorithmic pipelines.

*Accessibility challenges and ableist norms*. Accessibility challenges and ableist norms can deter disabled individuals from applying for jobs and lead to biased evaluations against them {cite}`scholz2020taken,tilmes2022disability`. Asynchronous video interviews can disadvantage candidates with speech impairments, who may give shorter answers, or those with visual impairments, due to misinterpretation of eye contact by algorithmic recruitment systems. This can result in these candidates being rated less favorably {cite}`orcaa2020description`.

*Uneven performance*. The uneven performance of language processing and computer vision tools regarding gender, race, and other sensitive attributes has been well-documented {cite}`blodgett2016demographic,buolamwini2018gender`. Integrating these off-the-shelf algorithms into hiring processes can lead to worse performance for minority candidates due to biased feature extraction, negatively impacting other algorithms based on these features.

## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

>This entry was readapted from~\cite[Section 3]{fabris2024fairness} by Alessandro Fabris}\\[1ex]


