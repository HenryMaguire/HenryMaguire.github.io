---
layout: post
title:  "My Advice for Getting into Data Science"
subtitle: "Become useful... and prove it"
date:   2021-02-04 00:00:00 +0000
image:  10.jpg
tags:   [tech, data science, machine learning, career]
---
It was 2013 when I found out about machine learning. I was an undergraduate physics student, trying to dream up programming projects to practice my Python skills on (and to monetise of course). One evening I was getting ready to go to a party but I had bbeen working for basically 12 hours straight. I had barely spoken to anybody all day. I needed to warm up and get sociable. I needed some spontaneity, but nobody was around.

This sparked an idea: to create a game where you create stories one word at a time, in collaboration with an intelligent computer. The computer would give you curveballs and you would have to react. That way, you would always be able to put yourself into a creative and sociable mood by testing your improvisational skills. But the problem is, I needed a computer to generate language. I had no idea where to start. It seemed impossible, but was it?

After a lot of time thinking (and scraping Project Gutenberg), I came up with a simple prototype based on a principle called an *N-gram language model*, by calculating the statistics of words in story books. It generated language, but it just didn't behave smart enough. It didn't truly _understand_ text, it just memorised what it had seen. To take it to the next level, it seemed that I needed machine learning and for that I needed time and energy. I parked the idea.

Later, during my PhD, the story game continued to play on my mind. It was now 2016 and I had become quite familiar with some concepts in Natural Language Processing (NLP). Articles like [Unreasonable Effectiveness of RNNs](http://karpathy.github.io/2015/05/21/rnn-effectiveness/) and tutorials like [WildML](http://www.wildml.com/2015/09/recurrent-neural-networks-tutorial-part-1-introduction-to-rnns/) were sending waves of excitement across the internet. These results captured my imagination. Right then, it became clear to me that this is what I wanted to, but how? The jargon seemed so elaborate and the field seemed so huge. 

I decided I needed to learn machine learning from the ground up. This was the beginning of my ML journey.

It is now 2021. The field has got huger and the jargon more elaborate. 15 months ago I completed my Physics PhD and shortly after that I became the only data scientist in a small tech startup called Orbital Witness. I've learned a great deal in the last two years, some of which I think could be useful for others getting into the field. 

Is it worth getting into data science now? What are the sorts of qualities you need to succeed?

## Main body
Data science is not just one field. It is the interface of several fields: machine learning, applied statistics and software engineering. Many different profiles of job exist, but all of them sit somewhere on those three axes. These are hugely dependent on the stage of the organisation. There are three common roles that most job types tend to fall into:

#### The "data person" at a small company/startup
This type of role can vary wildly. [Quite often](https://www.reddit.com/r/datascience/comments/lch48m/how_many_of_you_are_hybrids_of_data_analyst_data/) it involves setting up infrastructure to facilitate the reporting of business intelligence. Often this is called "data scientist" but for the first year it looks more like a data engineer/business intelligence analyst.
- Setting up "Data Warehousing" to make data easily accessible for analysis
- Build ETL pipelines to take data from disparate application databases and storage containers and load it into the data warehouse
- Building dashboards and visualising data
- Some quick-win analysis of data
- Present their findings back to the company


As time goes on, this role may involve more R&D and product data science:

- Sourcing/building labelled datasets
- Developing and deploying small data-driven product features
- Possibly some predictive analytics or customer segment analysis
- Hiring a bigger team


Organisations

- Established small and mid-size firms that already have product-market fit but are looking to grow their customer base or move into new markets
- Small startups trying to understand how their customers are using their goods or services

#### The research scientist

This type of role normally exists in larger companies, or where infrastructure has been set up. Generally there is far less emphasis on building data pipelines and managing databases.

- Speaking to product managers to figure out what the requirements are
- Sourcing/building labelled datasets
- Reading and implementing papers to figure out what works
- Developing product features
- Presenting findings back to the company

More often, this role is becoming more integrated with a machine learning engineer.

Organisations

- Small but ambitous tech companies whose competitive advantage is in developing cutting-edge ML
- Large, well-established tech companies with research divisions e.g. FAANG, DeepMind, Tesla, etc.

#### The product data scientist
Very little deployment of user features.

- Managing A/B experiments
- Statistical analysis of user behaviour to inform business decisions
- Predictive analytics, user modelling and customer segment analysis
- Reporting findings back to the company

Organisations

- All tech companies with enough user "events" to support this type of analysis