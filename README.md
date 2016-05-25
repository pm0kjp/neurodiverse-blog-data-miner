# A Neurodiverse Blog Data Mining Project

Completed in partial fulfillment of the requirements of IS 602, Advanced Programming Techniques, a course in the Data Analytics MS at the City University of New York

## Human Subjects Protection

I consider this to be exploratory work prior to research / a feasibility project and not research, so no IRB is involved.  Once this preliminary investigation is complete, a pilot project may be taken with IRB participation by the City University of New York or The Children's Hospital of Philadelphia.

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

We know that pronomial reversal (for example, mixing up "you" and "he") can be a challenge in ASD, as can fine motor skills, particularly bilateral fine motor skills (the kind necessary for typing). 

To do: lit review on bilateral fine motor skills and pronomial usage and reversal.

Because of this, I would like to mine blogs to determine if there are any detectable differences in the use of written language, when comparing writers with known (self-disclosed) ASD and no known ASD.  This is principally a tool-building exercise with no presumptive outcomes or treatment associated.

I will attempt to gather data on pronoun usage as well as word length and typing difficulty, with the goal of providing initial, provisional answers to questions like:

- Do autistic bloggers use the same number of pronouns as neurotypical bloggers?
- Do autistic bloggers use words of similar length when compared to neurotypical bloggers?
- Do autistic bloggers use words of similar typed difficulty when compared to neurotypical bloggers?
- Are people who have ASD-related fine motor impairment choosing simple-to-type synonyms for some words?  
- Is there an unusual concentration of easy-to-type letter sequences in the writing of people with autism?  

This project does not intend to provide support for or against any given hypotheses, but rather to gather additional data that can give feasibility estimates for further, more scientific inquiry.  

## Methods

I will assemble a list of blogs written by self-disclosed autistic bloggers, as well as a list of blogs by bloggers with no such disclosure.  This will be accomplished by conducting web searches and investigating blog-to-blog links.

I will use Python and Beautiful Soup to assemble corpora of text from these blogs.
* Separating blogs by type (Wordpress, Blogspot, etc.), I hope to find an economy of scale that will enable web scraping that does not have to be tailored to each site.  The initial proof of concept will use WordPress alone.
* I will try to respect robots.txt where used, and use appropriate timing to keep from unduly burdening hosts.
* I will attempt to spider blog sites in order to get previous posts in order to get large and robust corpora.

I will use the NLTK (Natural Language Toolkit) for Python to tokenize text, count word length, and count pronoun usage.

I will calculate typed difficulty based on a rough, self-written algorithm based on interkey intervals (I assume that the time it takes to execute a bigram sequence is a useful proxy for difficulty).

Resources in developing this algorithm will include scholarly publications such as the one found at http://userinterfaces.aalto.fi/how-we-type/. Additionally, I will search for digraph / bigram typing distance or difficulty metrics to include in this algorithm.  Citations of these external collaborataors will be included.
 
I will use matplotlib and subplots to create informative plots demonstrating differences/similarities between the language of autistic and neurotypical bloggers.

I will provide complete documentation that allows for reproducibility, with the help of GitHub repository and perhaps Jupyter notebooks for easy code tweaking by those who are interested in extending this research.

## Limitations and Caveats

 I make an assumption of a QWERTY keyboard to measure relative difficulty of typed words, and must account for the fact that some bloggers touch-type and others may "hunt and peck", making the measure of difficulty a very rough approximation.  At this time I am relying on the interkey interval datasets of other scientists.

 This is an observational study and causal relationships cannot be inferred.
