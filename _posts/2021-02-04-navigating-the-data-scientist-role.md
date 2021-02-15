---
layout: post
title:  "Navigating the Data Scientist role"
subtitle: "Become useful... and prove it"
date:   2021-02-04 00:00:00 +0000
image:  10.jpg
tags:   [tech, data science, machine learning, career]
---


One morning in September 2019, I uploaded the pdf of my PhD thesis to my university website, clicked "submit", closed my laptop and left my front door. Earlier that year, I had been speaking at physics conferences, but today was my first day on placement as a data scientist at a tech startup. The only data scientist, to be precise. For the last two weeks I had spent my days on the Faculty Fellowship - an intensive training course helping academics transition into data science - and in the evenings I had been in Goldsmith's library trying to finish my thesis on theoretical physics. I knew I had wanted to make this transition since the start of my PhD, and it was finally happening. The "Fellowship" had been drumming into me the _theory_ of how to be a good data scientist, but now I had to put it to the test. I didn't know the challenges ahead of me, but I was excited.

It has now been 15 months since my transition from physics to data science. I'm still at that startup where I started out, and have been building out the data science function here ever since. In this article, I want to give an overview of the most important lessons I have learned.

### The lifecycle of data science projects

Everyone wants to do machine learning, but before you can do machine learning you need data. The allure of data science and machine learning leads many companies to invest in a data scientist when actually what they need is a data engineer. In [this]() great article, the author shares the idea of the hierarchy of a company's data needs. At the very top of the pyramid, one is able to perform machine learning. The rest of the pyramid is built up of:

- Sourcing data
- Setting up "Data Warehousing" or some other centralised, flexible data store
- Building data pipelines (ETL/ELT) to load disparate data sources into the data warehouse
- Deploying and automating data pipelines

Only once you have these solid data engineering foundations can you then move onto the next phase. Labelling data.

Labelling data is exceedingly difficult to get right.


Once all of the infrastructure is set up and you have managed to get a bunch of labelled data and you have trained a model that performs well enough to solve your problem... congratulations! You have managed to get extremely far. Now for the exciting part: deploying your model to production.

To serve your model to users you first have to make sure that your model pipeline is fully reproducible. This means that it predicts the exact same output every time you feed in the same input, regardless of which device it's on. You manage this, by using scikit-learn pipelines and setting all your random seeds. You then put the model in a versioned Python package. Brilliant! Getting there.

You then write an API to serve your model, and deploy it on your favourite cloud infrastructure. You need to make sure that the model in your production environment is exactly the same as the one you trained in your notebook, so you build a Continuous Integration pipeline to run a suite of unit tests every time your package and API gets deployed. This same pipeline also gets used to automate deployments. Nice!

When your model is live, you need to make sure that it is working correctly and that it's not getting worse over time. It would be nice if it told you when something unexpected happens. Provide this visibility means setting up dashboards for metrics and logging.

Your model has a tendency to get worse over time, so you set out to get more labelled data. Or maybe you work out a way to gather feedback for your model in a scalable way that can be used to improve it over time. You now need to link different versions of your data to different deployments of your model, to make sure that you can always roll-back changes and retrain your model if needs be. 

You now have a new model, that appears to perform better than the one in production. To test that it _actually_ works as you expect in your production environment, you deploy it in _shadow-mode_. This means that your old model continues to be user-facing, but your new model _has a go_ on the production data coming in through your application. Only after your satisfied, after your new model has seen enough data, do you decide to roll traffic over to your new model endpoint. This has all ensured that your users benefit from the new model with zero down-time.

This is the full machine learning model lifecycle.

Here is a big list of all the tasks that data scientists could find themselves responsible for:

- Developing data-driven product features
	- Pulling and cleaning data
	- Building labelled datasets
	- Exploratory data analysis
	- Reading and implementing papers to figure out what works
	- Model building, selection and optimisation
- Machine Learning ops
	- Write reproducible model pipelines (training and predicting) as production code (unit tests, logging, config files, versioning)
	- Build an API that is suitable for your usecase (e.g. REST, polling, webhooks, serverless)
	- Deploy your model on suitable architecture
	- Set up schedulers for automating model retraining and any other data integrations
	- Set up metrics and logs dashboarding
	- Manage shadow-mode deployments if necessary
- Software engineering
	- Building quick & dirty user interfaces to demo models to your company/clients
	- Git, version control and code reviews
	- Test-driven development
	- Setting up CI/CD pipelines to automate tests, model deployment, package builds, etc.
- Product data science
	- Building dashboards and visualising data
	- Data analysis, predictive analytics, user modelling and customer segment analysis
	- Managing A/B experiments
	- Statistical analysis of user behaviour to inform business decisions
- Miscellaneous
	- Speaking to stakeholders/product managers to figure out what the requirements are
	- Hiring
	- Management/mentorship
	- Presenting findings back to the company
	- Standups, Agile, Kanban
	- Meeting with clients, domain experts, advisors and third-party service providers


### What has my role looked like?
My position so far has been quite idosyncratic. Many first data science hires might be required to set up infrastructure and build business intelligence dashboards. Back then, the reporting requirements at Orbital were simple enough that these tasks were split between the CTO and the product manager. On top of this, the company are intensely focused on building powerful technology, so my responsibilities were more around research and development of new product features. This meant that I've never had to build a Business Intelligence dashboard. This also meant that from day one I was spending more than half of my time working on typical data science projects, rather than building out infrastructure. Also, given that we are a legal tech company existing in a post-Transformer world, my work has been lucky enough to involve plenty of cutting-edge Natural Language Processing techniques.

At such a small startup, I have had to be involved in the entire lifecycle of all data science projects. 



For most tasks, we did not have any labelled data, so I had to set up and manage data labelling projects. This involved setting up data management and workflows, as well as giving guidance to labellers on how to generate higher quality data. Then  of the typical data science tasks: sourcing, cleaning and analysing data, building models. I then had to carry out all of the deployments: converting notebooks into production code, write APIs and test suites, deploy models on cloud architecture and build CI/CD pipelines to automate everything. I would also build and deploy web applications for internal use. This would allow people within the company to interact with the models to determine whether they could be turned into product features.


### What allowed me to succeed at this?
This has demanded several different skills, some of which - such as building web applications - I had picked up on side-projects long before I started the Faculty Fellowship.


### Lesson 1: "Data Scientist" is a very broad term

Data science is not just one field. It is the interface of several fields: machine learning, applied statistics, data engineering and software engineering. Broadly, most data science projects start out with the aim of extracting proactive insights from data. But unlocking this value is a multifaceted job and talented people from a wide variety of backgrounds have flocked to the role.

The upshot is that within data science, there are many different skills for you to generalise across or specialise into. There are also many different roles on offer that look completely distinct from each other. On top of this, in recent years many companies have simply renamed existing engineer and analyst roles as "data scientist" in order to signal to shareholders that they are jumping on the AI bandwagon. This makes the profession and the job market exceedingly difficult to navigate.

Is there a simple way to understand the different roles available? How do you `you.fit(jobs)` your way into a role that suits you?

So where does that lead us? Well, called Orbital Witness. I

Is it really worth getting into data science now? What are the sorts of qualities you need to succeed?

There are three common roles that most job types tend to fall into:

#### The "data person" at a small company/startup
This type of role can vary wildly. [Quite often](https://www.reddit.com/r/datascience/comments/lch48m/how_many_of_you_are_hybrids_of_data_analyst_data/) it involves setting up infrastructure to facilitate the reporting of business intelligence. Often this is called "data scientist" but for the first year it looks more like a data engineer/business intelligence analyst.
- Setting up "Data Warehousing" to make data easily accessible for analysis
- Build ETL pipelines to take data from disparate application databases and storage containers and load it into the data warehouse
- Building dashboards and visualising data
- Some quick-win analysis of data


As time goes on, this role may involve more R&D and product data science:

- Sourcing/building labelled datasets
- Developing and deploying small data-driven product features
- Possibly some predictive analytics or customer segment analysis
- Hiring a bigger team


Organisations

- Established small and mid-size firms that already have product-market fit but are looking to grow their customer base or move into new markets
- Small startups trying to understand how their customers are using their goods or services

#### The R&D data scientist

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



<!--- When I first found out about DS, what the world was like
- Nowadays, what the world is like. Cloud computing + open source technologies. ML and deep learning have been commodified. The advent of pretraining in both image and NLP has opened a similar kind of access to deep learning as scikit-learn allowed in traditional ML. The number of job opportunities called "data science" skyrocketed.
- Clarification over the term data scientist. It's a collection of fields. Broadly, the role is to "extract proactive insights from data", which given the democratisation of algorithms and compute makes them unreasonably valuable to many companies. But unlocking value from data is a multifaceted job - people from many different professions come into the role.
- There are many different skills for you to generalise across or specialise into. There are also many different roles on offer that look completely distinct from each other. It has also been used as a term to rename other different analyst roles as a way of signalling to shareholders that they are jumping on the AI bandwagon. This makes the profession and the job market exceedingly difficult to navigate.
- What I'm up to now. Essentially why you should read this article, but masked as a "what I've learned is X, Y, Z". I've recently been working on an immensely challenging problem with work and have been hiring a team. I've looked at many applicants and considered how my own skillset fits. I've learned some valuable lessons.
- Is there a simple way to categorise the different roles available? How do you `you.fit(job)` your way into a role that suits you? 
- I'm going describe ways to make yourself valuable, these will be true regardless of whether you are a first year undergraduate, or whether you have a PhD in Statistics. They will also be true regardless of whether you are 

Lessons

- Which school you went to or what you learned in your degrees doesn't count. It's only how useful you are and whether you can prove it.
	- Interview technique
	- Problem-->