# AI human interaction

## In Brief

As AI develops to learn and adapt, it is increasingly being perceived as human-like in both its appearance and intelligence. This ability to imitate human behavior and interactions creates anthropomorphic cues which cause users to form emotional bonds {cite}`kim2023anthropomorphic`. As AI becomes more commonplace in our daily lives, being integrated into virtual assistants, recommender systems etc. it is important to assess how the system’s anthropomorphic cues affect our interaction with it. In addition, potential risks resulting from AI-human interaction should be assessed prior to any implementation of AI as previous research has demonstrated the unpredictability of AI. 

## More in Detail

While AI systems have been implemented in industry applications such as price forecasting for many years, they have only recently been piloted for end-user interaction. This was primarily enabled by the onset of large language models, which have allowed for competent AI based virtual assistants to become commonplace on a variety of platforms. This section will assess the factors which impact AI-human interaction and how both human and AI traits can affect human perception of a AI. Next, potential adverse outcomes resulting from poor AI-human interaction identified in the literature are assessed. Finally, recommendations for AI design choices leading to successful AI-human interactions are provided. 

### Factors of AI-Human Interaction
Three factors of an AI are found to affect the anthropomorphic response of humans to AI interactions: appearance, cognitive intelligence and emotional intelligence {cite}`kim2023anthropomorphic`. Cognitive intelligence is found to be the most vital factor in triggering an anthropomorphic response but must co-occur with high quality design in order to be perceived as human-like. As such, systems which exceed in both design and intelligence are found to be perceived as most human-like by users and are hence most likely to cause the formation of emotional bonds. Based on this, developers should consider the impact of their systems design and function on the human anthropomorphic response before implementation in order to gauge any potential problems caused by the system. This is especially important in regard to vulnerable groups, which may form maladaptive attachments to AI which could cause harm. Consequentially the impact of the system on AI-human interaction must be assessed prior to implementation and steps to allow self-identification and regulate emotional impact must be taken. 

### Consequences of AI-Human Interaction
The implementation of AI to communicate with end-users has been seen in several different fields. Here we will be assessing the usage of AI in medicine. For each application, the current usage will be briefly elaborated and the potential risks and benefits discussed.

In the medical field, AI holds the potential to be implemented as a medical chatbot. These bots may be implemented for mental health counseling to support practitioners and provide low-cost assistance to patients. To produce human-level text, these bots utilize natural language processing, which allows the analysis of user utterances, which may allow the detection of sentiment changes. Based on this, machine learning algorithms may be able to detect patient outcomes and behavior changes. Through this technology, AI holds the potential to alleviate the substantial load on mental health professionals and provide support for patients in need. In addition, AI chatbots may support those unable to communicate with mental health providers due to stigmatization. Finally, previous research has demonstrated potential positive effects of AI chatbots over traditional therapy-alternatives {cite}`denecke2021artificial`.

However, despite these positive implications of AI in healthcare, the technology still presents major limitations, which block its successful implementation. First, the AI may not be capable of expressing the empathy and understanding required by an end-user leading to drop-out and decreased success rates. In addition, a self-learning AI bot may develop new conversational rules which deviate from existing protocol and could present harm to end-users. Finally, chatbots based on LLMs require large amounts of training data, which is difficult to acquire in the medical domain. It is important that chat bots are trained on domain-specific data as generic data may lead to adverse responses which may endanger users. 

### Guidelines
The current EU guidelines for AI focus on a risk-based approach to assessing AI safety. Based on this, human-AI interaction falls under the label of limited risk. However, depending on the target domain, this may change as medical chatbots would be considered high risk as they pose a risk of harm to people’s health. As such, developers should consider the potential outcomes of their developed model prior to implementation and consider the according regulations. The regulations applying to limited and high risk applications are briefly summarized below. 

**Limited Risk**
Limited risk AI systems are those systems which are considered to pose minimal risk of harm to user’s privacy, safety and fundamental rights. Limited risk applications are lightly regulated as they are considered to not pose major harm to end-users. However, systems must make it explicit to the end-user that they are communicating with an AI in order to avoid misunderstandings. 

**High Risk**
High-risk AI systems, as defined by the EU AI Act, are those that present a significant potential threat to people's safety, well-being, and fundamental rights. These systems are subject to stricter regulations to mitigate these risks.
Developers of high-risk AI systems must conduct thorough risk assessments, ensure human oversight to prevent misuse, and implement robust data management practices to minimize bias and privacy risks. For these systems, there is a greater emphasis on transparency in decision-making processes, which helps identify and address potential biases or errors.
Classifying AI systems as high-risk aims to proactively manage potential dangers and promote the responsible development and deployment of AI technology. This approach seeks to ensure that AI benefits society while protecting people's well-being and fundamental rights.
As such, AI systems which interact with users in a medical domain and may have frequent interactions with vulnerable audiences must undergo stringent testing as well as prove to be transparent in their decisions in order to ensure user safety[^secureprivacy]. 


## Bibliography

```{bibliography}
:style: unsrt
:filter: docname in docnames
```

> This entry was written by Nicola Rossberg and Andrea Visentin.


[^secureprivacy] <a href="https://secureprivacy.ai/\_2024" target=_blank>https://secureprivacy.ai/_2024</a>.
