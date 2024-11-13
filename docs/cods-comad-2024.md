# **Tutorial CODS COMAD 2024**

## Data preparation for fine tuning Large Language Models

When developing applications involving Large Language Models (LLMs), such as fine-tuning, pre-training, or instruct-tuning, data preparation stands as a
critical initial step. The quality of the model is heavily influenced by the quality and relevance of the training data.

This tutorial aims to guide the participants through the essential techniques for preparing data for LLM applications, focusing on the latest methodologies. We will begin
by exploring state-of-the-art methods used in the field. Following this, we will provide a hands-on tutorial using [data-prep-kit](https://github.com/IBM/data-prep-kit), an open-source
toolkit designed to facilitate various data preparation tasks.

To ensure the participants gain practical experience, we will construct a comprehensive data processing pipeline tailored to a specific use case in LLM application

development. This end-to-end example will equip the participants with the skills and knowledge needed to apply these techniques to their own projects.

By the end of this tutorial, the participants will have a solid understanding of data preparation best practices for LLMs and be able to implement them effectively in their applications.

### Overview 

This tutorial is organized into three primary sections. The first section will
cover the motivation behind data preparation for LLMs and discuss current
state-of-the-art techniques. In the second section, we will use a real-life use case
to demonstrate how to construct a data preparation pipeline. The third section
will introduce a novel development toolkit that allows users to easily add their
own transformations and scale up their projects. We will conclude the session
with a brainstorming session focused on actionable steps for the community to
collaborate and advance research in data preparation for LLMs.

1. [10 min] **Introduction**
2. [10 min] **Setup for hands-on session**
3. [45 min] **Part 1: Discussion on techniques for data preparation
for Code**
4. [60 min] **Part 2: Hands-on session to build data pipelines**
5. [30 min] **Part 3: Bring your own transform**
26. [10 min] **Conclusion**
7. [15 min] **Discussion, Q&A and brainstorming on what the community can do to advance this area**

## Expected Background

1. Basic Knowledge of Machine Learning (ML) and Deep Learning (DL)
2. Basic Understanding of Large Language Models (LLMs)
3. Experience with Programming
4. Familiarity with Data Handling and Preprocessing
5. Basic Understanding of Command Line Interface (CLI)
6. Knowledge of Version Control Systems
7. Basic Understanding of Linux/Unix Systems


## Expected Gained Skills

1. Data Preparation Techniques for LLMs
2. Usage of Open-Source data-prep-kit toolkit
3. Data Processing Pipeline Construction
4. Hands-On Experience with Real-World Use Cases
6. Better Understanding of Data Quality Impact

## Presenters

<div style="display: flex; align-items: center; margin-bottom: 20px;">
  <img src="https://media.licdn.com/dms/image/v2/C5103AQGWmIFOyywjCg/profile-displayphoto-shrink_800_800/profile-displayphoto-shrink_800_800/0/1516265104592?e=1736985600&v=beta&t=Ct-bAIXKQ1ZxsRkKT4g5ckYTbbJ8OuJxVEXICFAHCBE" alt="Presenter 2" style="width: 150px; height: 150px; margin-right: 20px;border-radius: 50%;">
  <div>
    <h3>Hima Patel</h3>
    <p>Hima Patel holds dual titles of a Senior Technical Staff Member and
Research Manager at IBM Research in Bengaluru, India. Her research interests
are around data centric AI, including data quality for tabular and unstructured
data, data cleaning, data transformations and building AI based data tools for
enhancing data scientist‚Äôs experience in an AI lifecycle by reducing time to value.
She currently heads the code data preparation globally at IBM Research and is
responsible for preparing data for all the Granite models which have been open
sourced. She has given tutorials at KDD 2020 (slides, video), KDD 2021 (slides),
KDD 2022(slides) and organised workshops at PAKDD 2021, KDD 2021 along
with bringing AI in community events like GHCI and IEEE Computer Science
3Bangalore Chapters 2020, 2021. Her work has also made impact to large number
of IBM products for which she has several IBM wide recognition‚Äôs to her credit.</p>
  </div>
</div>

<div style="display: flex; align-items: center; margin-bottom: 20px;">
  <img src="https://media.licdn.com/dms/image/v2/C4E03AQE8ODPiMcSdew/profile-displayphoto-shrink_800_800/profile-displayphoto-shrink_800_800/0/1517668872170?e=1736985600&v=beta&t=auvq_xUi9Vt6sD6e76TdA44hfokL8AxdoCxLjW_FZtE" alt="Presenter 1" style="width: 150px; height: 150px; margin-right: 20px;border-radius: 50%;">
  <div>
    <h3>Parameswaran Selvam</h3>
    <p>Parameswaran Selvam is a Senior Research Software Engineer at
IBM Research in Bengaluru, India. His research focuses on developing efficient
data processing and data preparation techniques, particularly for Large Language Models. He is currently involved in creating a highly scalable code data
preprocessing pipeline for IBM Granite models. With a strong background in software system design and development, he has contributed to several open-source
projects.</p>
  </div>
</div>


<div style="display: flex; align-items: center; margin-bottom: 20px;">
  <img src="https://media.licdn.com/dms/image/v2/D5603AQF5jSUsnI989g/profile-displayphoto-shrink_800_800/profile-displayphoto-shrink_800_800/0/1684307943099?e=1736985600&v=beta&t=zBjBKHtTPjBCmUHQ9WGanySDa120tYQ76463sHRvcG0" alt="Presenter 2" style="width: 150px; height: 150px; margin-right: 20px;border-radius: 50%;">
  <div>
    <h3>Saptha Surendran</h3>
    <p>Saptha Surendran is a Research Software Engineer at IBM Research in
Bengaluru, India. She is passionate about designing, developing, and optimizing
complex software systems. Her relentless curiosity drives her to tackle diverse
and challenging problems. Currently ,she focuses on data engineering for Large
Language Models (LLMs) tailored to enhance code generation. She plays a
crucial role in translating cutting-edge research into practical software solutions.
Saptha has been pivotal in the meticulous data preparation for IBM‚Äôs Granite
models, efficiently managing extensive code volumes within the pipeline while
maintaining high standards of code quality. She has also made significant
contributions to various open-source projects.</p>
  </div>

</div><div style="display: flex; align-items: center; margin-bottom: 20px;">
  <img src="https://media.licdn.com/dms/image/v2/D5603AQGUVUNXv6JbgA/profile-displayphoto-shrink_800_800/profile-displayphoto-shrink_800_800/0/1693992289798?e=1736985600&v=beta&t=JxXjV0egARWwUSUftBwdLRFB4nd7mV6YmHODZ6ui0E8" alt="Presenter 2" style="width: 150px; height: 150px; margin-right: 20px;border-radius: 50%;">
  <div>
    <h3>Shivdeep Singh</h3>
    <p>Shivdeep Singh is a Research Engineer at IBM Research in Bengaluru,
India. He is currently working to build data engineering preprocessing components and pipelines for data preparation of data for LLMs. He was involved in
processing data at scale for IBM Granite models which are now open-source.
His research is focussed on data processing and data preparation techniques and
is also involved in the development of data-prep-toolkit, a open-source toolkit
for processing data at scale for LLMs by IBM.</p>
  </div>
</div>

## Resources

- [Slides]() _Coming Soon_

## Related Literature
_Coming Soon_

## Citation

_Coming Soon_
