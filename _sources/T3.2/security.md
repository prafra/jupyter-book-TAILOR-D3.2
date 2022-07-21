# Security

## In brief

The goal of **security** encompasses the
protection of several operational dimensions of an AI system when
confronted with possible attacks, trying to take control of the system
or having access to design, operational or personal information. A
secure system is capable of maintaining the integrity of the information
that constitutes it. This includes protecting its architecture from the
unauthorised modification or damage of any of its component parts. A
secure system also keeps confidential and private information protected
even under hostile or adversarial conditions. [^def2]

## More in detail

Security must be an integral part of the AI process. Protecting AI
systems, their data and their communications is critical to the security
and privacy of users, as well as protecting business investments. The AI
systems themselves are incredibly expensive and possess valuable
intellectual property to protect against disclosure and misuse. The
confidentiality of the program code associated with AI systems may be
considered less critical, but access to it, as well as the ability to
manipulate this code, can result in the disclosure of important and
confidential assets.

Several kinds of attacks against AI systems have been reported.
Currently, the most prominent attack vector categories are
{cite}`liao2011secure`: adversarial inputs {cite}`goodfellow2014explaining`; data
poisoning attacks {cite}`schwarzschild2021just`; model stealing techniques
{cite}`tramer2016stealing,fabra2018identifying`; model poisoning
{cite}`fang2020local`, data leakage {cite}`papadimitriou2010data` and neural
network Trojans {cite}`ji2019programmable`, among others. Attack vectors
directed against the AI systems' deployment or training environment are
equally applicable. These may be attack vectors directed against
servers, databases, protocols or libraries utilised within the AI system
{cite}`hartmann2020hacking`.

Currently, AI systems often lack sufficient security assessments
{cite}`Neustadter2020`. This may be the result of the mutually independent
development of AI methods and their implementation in applications:
while the application should have a security assessment, embedded AI
(via APIs or frameworks) is rarely considered in terms of its security
vulnerabilities by application developers and/or practitioners. While AI
developers may follow coding standards and guidelines for secure
software development, they will not assess the potential attack surface
of an AI system (i.e., the means by which an attacker may enter, extract
data or manipulate the system in question) using the system.


## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was written by Jose Hernandez-Orallo, Fernando Martinez-Plumed, Santiago Escobar, and Pablo A. M. Casares.

[^def2]: Definition taken from {cite}`david2019understanding` under Creative Commons Attribution License 4.0.
