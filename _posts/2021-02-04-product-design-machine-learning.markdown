---
layout: post
title:  "Why product design might be the hardest problem in machine learning"
subtitle: "Good Data Science = Good Product"
date:   2021-02-04 00:00:00 +0000
image:  10.jpg
tags:   [tech, data science, machine learning, career]
---

### Algorithms and infrastructure have been commoditised.


To train machine learning (ML) models, you need three things. Algorithms, compute and data.

The goal of data science projects is to automate tasks that are normally performed by humans. This means that they ought to recieve similar inputs as a human would and deliver comparable outputs. The job of a data scientist is to somehow replicate this human behaviour in code.


A good way of replicating human behaviour in code is by using _supervised_ machine learning. This is where you gather many examples of a human expert performing a task correctly - both inputs and outputs - and show them to a model. The model is then trained to predict which inputs lead to which outputs, in a way which generalises to other _unseen_ examples. Models store this knowledge in their _parameters_. So a model is comprised of the machine learning algorithms - these are the generic patterns of _how_ to learn - and the parameters, which are learned from data and used to constrain the models to give a desired outcome for a specific task.


Over the last decade, a staggering number of open-source machine learning algorithms and architectures have been made available for free. For many applications - particularly those involving structured data in spreadsheets - you can get extremely far by using classical algorithms such as gradient-boosted trees and linear regression. These algorithms continue to appear at the top of Kaggle leaderboards (albeit in ensembles), but are trivially simple to implement and tune using packages such as scikit-learn and XGBoost.

This is all well and good, but many of the most promising applications of machine learning rely on dealing with _unstructured data_, such as images, text and audio. For example, self-driving cars must identify the locations of pedestrians in a stream of images, and chatbots must classify what a user's intentions are. For the best part of a decade, these types of tasks have been dominated by deep learning, but building high quality systems has required huge amounts of data, expertise and have been costly to train. 

The advent of "pre-training" or "transfer learning" has made it possible to build intelligent applications around unstructured data with a fraction of the resources. This has been true of image processing for many years, where people reuse the general purpose layers of a large pretrained model such as VGG, GoogLeNet and ResNet, and plug them into a domain specific vision task. Along with massive improvements to deep learning libraries, better tutorials and cheaper cloud infrastructure, this led to a democratisation of computer vision technology. People could suddenly get close to cutting-edge performance in computer vision tasks with a fraction of the expertise and resources.

Meanwhile, developments in natural language processing were not going as smoothly. The standard toolbox of static word-embeddings, RNNs and CNNs was being pushed to its limit, and implementing these things required a lot of labelled data, expertise and compute. This often led many people to stick to classical ML methods based around word counts, such as TF-IDF. Simple, but often hard to beat without a step-up in investment.

That is until 2018, when transformers exploded onto the scene. 

Transformers allowed a huge increase in parallisation when training language models compared the RNNs, and are able to understand far wider contexts. Companies such as Google and OpenAI began training huge general purpose language models, naming them after Sesame Street characters and then open sourcing them. These general purpose models learn a huge amount of the complexities of language, which comes in very handy for a wide variety of tasks. You can profit from this by simply copying parts of these pretrained models to your own projects and training them further on your domain-specific tasks. It turns out that the general understanding these models start out with makes them far more robust and data efficient, often requiring less labelled data in the domain-specfic fine-tuning phase.

To top this all off, packages like Huggingface Transformers have centralised the sharing of model parameters and code and abstracted everything behind extremely simple APIs. Suddenly, the barriers to entry to building products driven by cutting-edge NLP have been drastically lowered.


This means models and compute have been commoditised. Very little prevents anyone from taking an off-the-shelf model, applying it to their own use-case and achieving suprisingly good performance.

But one thing is currently missing from our recipe. Labelled data. 

### Data is rarely labelled data

The amount of data sitting in databases is increasing exponentially all the time. This has led to the rise of a common misconception, that there is an abundance of data available to train machine learning models on. As outlined in the introduction, models normally need _labelled_ data in order to learn how to perform a task correctly. 

More recently, GPT3 has been shown to perform several tasks quite well without any task-specific training. This is known as zero-shot learning. The performance of GPT3 is extremely impressive and has caused quite a stir. Indeed, this area is of interest to many people, but there are two reasons why I will not focus on it:

- Without task-specific data it is impossible to quantify the performance of a model. This makes it extremely difficult to trust in production. This means that you will need labelled data anyway.
- The more specific and complex a task is, the more likely it is that you will need to train a supervised model using labelled data. This is because large pretrained models will have been exposed to less of this domain specific language, and complex tasks need more data to learn from.

When trying to solve complex and interesting problems using machine learning, it is highly likely that you will need to find some labelled data.

### Labelling data requires domain experts

Imagine you are building a spam detection system. Identifying emails as "spam" and "not-spam" needs limited domain expertise, so we can cheaply outsource this task to gather a large amount of training data. In addition, most people with an email address are qualified enough to tell whether items in their mailbox are spam or not. This means that email providers can design their interfaces to allow users to identify spam that has slipped through the net. This new labelled data can be fed back to the model, so over time the service gets better and better. Importantly, as spam bots get more sophisticated, our users will provide fresh data that can help us overcome this.

But many of the most interesting tasks require extensive domain knowledge and cannot be cheaply outsourced. In this case, you need to hire domain experts to get labelled data. If this field evolves over time, you may need to continually keep this expense on your payroll.

### Designing feedback loops in products is really valuable but really hard

As a machine learning practitioner, the best position to be in is for your models to be perfect. The second best scenario is for the users of your model to be continually providing feedback which can be used as fresh training data. This allows the accuracy of your models to scale with usage, and it provides up-to-date test data to gauge accuracy of your models. 

However, designing your products in this way can be exceedingly difficult. In particular, there are two interesting challenges:

- How do you design your interfaces to gather useful feedback without affecting user experience?
- How do you make sure that your users are qualified to provide this feedback?

These are all extremely complex and interesting questions. Ultimately, this means that the biggest blocker to achieving the "holy grail" of with usage, is shrewd product design.


Performance scales with usage. Operational costs will decrease over time. Extending features takes less upfront commitment to labelling.
- THis means that you need to design products which 

### The need for labelled data makes it harder to test product-market fit

As we have seen, profiting from machine learning is rarely as simple as typing `model.fit(data)` and hitting shift-enter.

- Labelling is a sunk cost
- Figuring out what your product is actually going to do determines what sort of labelled data you will need.
	- In NLP, building a chatbot, an entity tagger, a sentence classifier, or a question answering system ideally require different forms of labelled data.
- The contraints you put on labelling are hard to undo later, without making assumptions/approximations or significant investment into relabelling.
- Before you can even start labelling data, you must know what your product needs to do. This requires committing to product-decisions. But committing to decisions before you get product-market fit is not _agile_ or _lean_.
- One option is to test prototypes based on manually labelled data.
	- This can be effective, but it must be done in the knowledge that production performance will be lower.
	- You must gauge your sensitivity to getting things wrong. How much does a user care about false positives and false negatives? If you're diagnosing diseases, you don't want false negatives, if you're building a spam filter you want to minimise false positives.


	
	
### Takehomes
- Set up labelling in a way that you can iterate on
- Intimately relate labelled data to product 