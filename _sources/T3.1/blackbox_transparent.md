# Black Box Explanation vs Explanation by Design

## In brief

## More in detail

We distinguish between black box explanation and explanation by design. 

In the first case, the idea is to couple an AI with a black box model with an explanation method able to interpret the black box decisions. In the second case, the strategy is to substitute the obscure model with a transparent model in which the decision process is accessible by design.
Figure {numref}`{number} <post-hoc>` depicts this distinction. 

```{figure} ./post.png
---
name: post-hoc
width: 600px
align: center
---
(Top) Black box explanation pipeline. (Bottom) Explanation by design pipeline. {cite}`Guidotti2021`.
```

Starting from a dataset *X*, the **black box explanation** idea is to maintain the high performance of the obscure model b used by the AI and to use an explanation method *f* to retrieve an explanation e by reasoning over *b* and *X*. This kind of approach is the one more addressed nowadays in the XAI research field {cite}`ribeiro` {cite}`Craven20` {cite}`Lundberg45`. 

On the other hand, the **explanation by design** consists of directly designing a comprehensible model *c* over the dataset *X*, which is interpretable by design and returns an explanation *e* besides the prediction *y*. Thus, the idea is to use this transparent model directly into the AI system {cite}`rudin61` {cite}`rudin62`. 

In the literature, there are various models recognized to be interpretable. Examples are decision tree, decision rules, and linear models {cite}`Freitas24`. These models are considered easily understandable and interpretable for humans. However, nearly all of them sacrifice performance in favor of interpretability. In addition, they cannot be applied effectively on data types such as images or text, but only on tabular, relational data, i.e., tables.


```{bibliography}
:style: unsrt
:filter: docname in docnames
```

---
 
This entry was readapted from *Guidotti, Monreale, Pedreschi, Giannotti. Principles of Explainable Artificial Intelligence. Springer International Publishing (2021)* by Francesca Pratesi and Riccardo Guidotti.
