# A Neurodiverse Blog Data Mining Project

This project was completed in partial fulfillment of the requirements of IS 602, Advanced Programming Techniques, a course in the Data Analytics MS at the City University of New York.

## Contents of this Repository

The creation of an inter-key interval (IKI) dataset and the resultant data is contained in the [typing_difficulty] (https://github.com/pm0kjp/neurodiverse-blog-data-miner/tree/master/typing_difficulty) directory.

Additional resources for study can be found in the [background_research](https://github.com/pm0kjp/neurodiverse-blog-data-miner/blob/master/background_research/) directory.

The main script that mines blogs, analyzes their content, and gives statistical and graphical results is in this directory, in the [Final Project.ipynb](Final%20Project.ipynb) file.

## Human Subjects Protection

I consider this to be exploratation / feasibility analysis on publicly available data prior to research and not human subjects research, so no IRB is involved.  Once this preliminary investigation is complete, a pilot project may be taken with IRB participation by the City University of New York or The Children's Hospital of Philadelphia.  Care has been taken to obscure the identity of the bloggers whose data was used to generate the analysis found here. 

## Introduction to ASD

The goal of this project is to do exploratory data mining on blogs written by self-disclosed autistic bloggers and on blogs written by bloggers presumed to be neurotypical (not on the autistic spectrum).  

Autism Spectrum Disorder (ASD) is a neurodevelopmental disorder characterized by:
-  difficulty with social interaction
-  language delay and/or impairment
-  repetitive behaviors in movement and/or motor delay
-  narrow, insistent, or odd interests
-  onset in early childhood 

ASD has wide-ranging degrees of affectedness and there is great diversity in the affected population.  While previously, the relative severity of ASD was indicated by differential diagnoses including Asperger's Syndrome, autism, and pervasive developmental disorder, we now apply the term "Autism Spectrum Disorder" to all levels of affectedness. 

The characteristics of ASD co-condition one another.  For example, in infants who will go on to have autism, we find a simplification / flattening of cries and coos, with a less rich sound vocabulary, prior to the formation of vocabulary or lexical content.  This can be understood as a relationship between motor development (the physical system of sound production) and language acquisition. 

## Intent / Goals of this Project

In spoken language, we recognize that there is a lexical component (which words you use), a motor component (how you use your body to make sounds), and a pragmatic element (how you make your wants and needs effectively communicated).  People with ASD may have difficulty in all three: unusual word choices or limited or echolalic vocabulary in the lexical domain, unusual pauses, unusual volume or pitch in the motor domain, and social inappropriateness, lack of tact, etc. in the pragmatic language domain.  This project attempt to investigate some lexical and motor components of language, but this time in written language.

We know that pronomial reversal (for example, mixing up "you" and "he") can be a challenge in ASD, as can fine motor skills, particularly bilateral fine motor skills (the kind necessary for typing). I did not include a lit review on bilateral fine motor skills and pronomial usage and reversal in this project, but this is a future enhancement I intend.

Because of this, I mined blogs to determine if there are any detectable differences in the use of written language, when comparing writers with known (self-disclosed) ASD and no known ASD.  This has been principally a tool-building exercise with no presumptive outcomes or treatment associated.

I gathered data on pronoun usage based on the Penn Treebank part of speech tagger in the Natural Language Tool Kit as well as typing difficulty (using a new measure that uses a subset of bigram interkey interval means), with the goal of providing initial, provisional data that could suggest answers to questions like:

- Do autistic bloggers use the same number of pronouns as neurotypical bloggers?
- Do autistic bloggers use words of similar typed difficulty when compared to neurotypical bloggers?
- Are people who have ASD-related fine motor impairment choosing simple-to-type synonyms for some words?  
- Is there an unusual concentration of easy-to-type letter sequences in the writing of people with autism?  

This project does not intend to provide definitive support for or against any given hypotheses, but rather to develop tools and gather additional data that can give feasibility estimates for further, more scientific inquiry under the oversight of an IRB.  

## Methods

I assembled a list of blogs written by self-disclosed autistic bloggers (n=30), as well as a list of blogs by bloggers with no such disclosure (n=24).  This was accomplished by conducting web searches and investigating blog-to-blog links.  The lists are not shared on this repository in order to preserve the privacy of the bloggers whose data was used.

I used Python and Beautiful Soup to assemble corpora of text from these blogs.
* The initial proof of concept used WordPress-powered blogs only, because of the predictable pattern required for successful web scraping.  In the future, by separating blogs by type (WordPress, Blogspot, etc.), I hope to find an economy of scale that will enable web scraping that does not have to be tailored to each site.  
* I partially spidered blog sites in order to get previous posts in order to get large and robust corpora.

I used the NLTK (Natural Language Toolkit) for Python to tokenize text and count pronoun usage.

I calculated typed difficulty based on a self-written algorithm based on inter-key intervals, or IKI (I assume that the time it takes to execute a bigram sequence is a useful proxy for difficulty).
* I gathered inter-key interval data from several studies of the biomechanics of typing and limited my bigrams of interest only to letter combinations (for example, "ng" or "ab").
* From these bigrams, I selected only the ones that had characteristics of unimodal distributions with low standard error values.  This is necessary because many key sequences may be multimodal, as they have different difficulty levels based on typing method (touch typing, hunt-and-peck, etc.).
* I used the Z-score of mean bigram IKI as a proxy for difficulty, and calculated total typed difficulty by taking a corpus, looking only at the set of bigrams for which robust statistical data was available, and taking the average difficulty level from among that set.

I used matplotlib and subplots to create informative plots demonstrating differences/similarities between the typed language of autistic and neurotypical bloggers.

I provided as complete documentation as possible given ethical and intellectual property protection requirements, with the goal of allowing for reproducibility, with the help of this GitHub repository and Jupyter notebooks for easy code reuse by those who are interested in extending this research.

## Findings

Bloggers with ASD do not have markedly different typing difficulty profiles when compared to bloggers without ASD.  They do, however, have statistically significant differences in the use of pronouns:  They use fewer possessive pronouns (words like _hers_, _ours_, _theirs_) and more "wh-" pronouns (_who_, _whom_).

## Limitations and Caveats

 I make an assumption of a QWERTY keyboard to measure relative difficulty of typed words, and must account for the fact that some bloggers touch-type and others may "hunt and peck", making the measure of difficulty a very rough approximation.  At this time I am relying on the interkey interval datasets of other scientists.  My sample size is limited. This is an observational study and causal relationships cannot be inferred.
