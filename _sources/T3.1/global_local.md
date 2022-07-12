# Global vs Local Explanations

## In brief

We distinguish between a **global** or **local** explanation depending on whether the explanation allows understanding the whole logic of a model used by an AI system or the explanation refers to a specific case, i.e., only a single decision is interpretable. 

## More in detail

A **global explanation** consists in providing a way for interpreting any possible decision of a *black box model*. 
Generally, the black box behavior is approximated with a transparent model trained to mimic the obscure model (see {doc}`blackbox_transparent`) and also to be human-understandable. In other words, the interpretable model approximating the black box provides a global interpretation. Unfortunately, global explanations are quite hard to achieve and, up to now, can be provided only for AI working on relational data. 

A **local explanation** consists in retrieving the reasons for a specific *outcome* returned by a black box model relatively to the decision for a certain instance. 
In this case, it is not required to explain the whole logic underlying the AI, but a local explanation only provides the reason for the prediction on a specific input instance. 
Hence, an interpretable model is used to approximate the black box behavior only in the "neighborhood" of the instance analyzed, i.e., with respect to similar instances only. The idea is that it is easier to approximate the AI with a simple and understandable model, in such a neighborhood. Regarding Figure {numref}`{number}<post-hoc>` (top) (see {doc}`blackbox_transparent`), a *global* explanation method *f* uses many instances *X* over which the explanation is returned.


```{figure} ./global_tree.png
---
name: global-tree
width: 600px
align: center
---
Global explanation example in the form of decision tree {cite}`Guidotti2021`.
```

Figure  {numref}`{number} <global-tree>` illustrates an example of a global explanation *e* obtained by a decision tree structure for a classifier recommending to play tennis or not. 
The overall decision logic is captured by the tree that says that the classifier recommends playing tennis or not by first looking at the *Outlook* feature. If its values *Overcast*, then the prediction is "not to play". Otherwise, if its value is *Sunny*, the classifier checks the *Humidity* feature and recommends "not to play" if the *Humidity* is *High* and "to play" if it is *Normal*.
The same reasoning applies to the other branch of the tree. 
Again, with reference to Figure {numref}`{number}<post-hoc>` (top) (see {doc}`blackbox_transparent`), a local explanation method *f* returns an explanation only for a single instance *x*.

Two examples of local explanations are given in the following. <!--shown in Figures  {numref}`{number} <local-rule>` - {numref}`{number} <local-feature>`. -->

```{figure} ./local_rule.png
---
name: local-rule
width: 400px
align: center
---
Local explanation example in the form of decision rule {cite}`Guidotti2021`.
```


The local rule-based explanation (Figure  {numref}`{number} <local-rule>`) *e* for a given record *x* says that the black box *b* suggested playing tennis because the *Outlook* is *Sunny* and the *Humidity* is *Normal*. 


```{figure} ./local_feature.png
---
name: local-feature
width: 200px
align: center
---
Local explanation example in form of feature importance {cite}`Guidotti2021`.
```

On the other hand, the explanation *e* formed by features importance (Figure  {numref}`{number} <local-feature>`) says that the black box *b* suggested playing tennis because the *Outlook* has a large positive contribution, *Humidity* has a consistent negative contribution, and *Wind* has no contribution in the decision.




## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

---
 
This entry was readapted from *Guidotti, Monreale, Pedreschi, Giannotti. Principles of Explainable Artificial Intelligence. Springer International Publishing (2021)* by Francesca Pratesi and Riccardo Guidotti.
