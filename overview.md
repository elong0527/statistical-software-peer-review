#  (PART) Introduction {-}

#  Project Overview {#overview}

This chapter lays out key considerations, outstanding
questions, and tasks for our first year of work, for purposes of generating
community feedback for the project. It consists of the following sections:

-   **[Scope of Statistical Software Review](#scope)** in which we address the
    scope of the project, and scopes of definition of "statistical software".

-   **[Standards for Statistical Software](#standards)** in which we consider the kinds of
    standards which might be developed and applied to assess statistical
    software.

-   **[Software Assessment](#assessment)** in which we provide a partial list
    of attributes and measures of software which might be usefully considered.

-   **[Statistical Software Peer Review Process](#process)** in which we
    consider questions regarding the possible forms and practices a peer review
    process might adopt.

Each of these sections aims to highlight what we consider some of the most
important questions and issues which the project will have to address. We
generally do so by posing a list of "*Proposals*" at the end of each of the
above-listed chapters. Each of these is intended to serve as a starting point
for debate, and should be considered entirely open to discussion, modification,
enhancement, removal, or any other suggestion which may arise. The *Proposals*
are primarily intended in current form to provide focal points for further
consideration and discussion prior to any concrete implementation.


<!--
The central questions which emerge from this document are given in condensed
form in an accompanying document which may be used to structure and enable
explicit feedback on the above aspects of the project.
-->

## Project Aims

-   To foster a community of practice in which users and developers of
    statistical software mutually improve quality, reproducibility, and
    reliability of research.

-   To provide software creators with a set of tools to assess the quality of
    their work, and a process by which to improve it.

-   To provide statistical software developers, users, and consumers of results
    a discoverable "badge" that transparently conveys a level of assurance of
    software quality and may be usable as professional credit.

-   To create a set of standards that may be adopted and adapted by open source
    and private groups, academic journals, or other statistical software
    evaluation projects.

-   To focus on R as primary language, but separate language-specific from
    language-agnostic components so as to maximize adaptability to other
    contexts.

-   To focus on problems and solutions specific to statistical software.

## Related projects and initiatives


The following internal and external projects related projects have (non-exclusive) 
bearing on our work:

rOpenSci is simultaneously working on improving the automation and documentation
of infrastructure to support software peer reviews. This will support many of
the processes described herein, initially those in metrics and diagnostic
reports (below), as well as in managing the review process.

Secondly, [under a separate project funded by the Moore
Foundation](https://ropensci.org/blog/2019/11/06/scientific-package-ecosystem/),
rOpenSci is building a system to automate the retrieval of information related
to use of software in published literature and automate reporting of software
impact as part of metadata in software repositories. This builds on
[Depsy](http://depsy.org/) and [CiteAs](http://citeas.org/about) projects and
may be leveraged for our work on metrics (below).

Third, an initiative organized under the R Consortium, the [R Validation
Hub](https://www.pharmar.org/), seeks to provide guidance primarily to R users
in the pharmaceutical industry on validating R packages in regulated contexts.
We are working closely with that group to share products and avoid duplicated
efforts.

## Outline of this document

We now briefly summarise the four sections identified at the outset of this
chapter, and which comprise Chapters 4--5 and 7--8 of this book: Scope; the
Peer Review Process; Standards; and Software Assessment.

### Scope of Statistical Software Review

The scope of statistical software review considers the core task of defining
the kinds of software that will be covered by our review process and standards,
for which key questions are:

-   What categories of statistical software might be considered *in scope*?

-   What categories of statistical software might be considered *out of scope*?

-   How would these vary between a useful definition and typology for general
    use, and the specific case of our R-focused peer review system?

A key consideration in scope is identifying categories of software that (a) will
benefit from our peer review process, and (b) the review process will be
equipped to handle. That is, can standards and procedures be defined that are
applicable, and will authors and reviewers be able to apply them? In considering
these issues of definition, it will be important to consider whether it may be
advantageous or necessary to develop different procedures for different
sub-categories, whether in terms of categories of external form or categories of
statistical software.

It will likely be particularly important for the present project to develop
a categorization scheme, particularly because the set of standards envisioned
by this project will be variably applicable to different categories, and
understanding which standards may or may not apply to a particular piece of
software will provide important information for review purposes. Individual
pieces of software will often fit more than one of these categories, and we
envision relating some kind of categorical checklist directly to
a corresponding checklist of relevant or applicable standards.

Potential schemes for defining the scope of statistical software acceptable
within our review process are considered in [Chapter 4](#scope) below, with
extensive consideration of potential categories in the [second section of that
chapter](#scope-categories).


### Standards for Statistical Software

[Chapter 5](#standards) considers Standards for Statistical Software intended
to serve both as expectations against which to compare software, and as guides
which reviewers may use to assess software. Important general questions
regarding standards include the following:

-   What kind of standards might apply to software in general?

-   What kind of standards might specifically apply to statistical software?

-   How might such standards differ between different languages?

-   To what extent should we aim for "verification" or "validation" of
    software, and how might be signify such?

### Software Assessment

The Software Assessment section in [Chapter 6](#assessment) presents a general
(yet non-exhaustive) overview of aspects of software which may be usefully
considered for standards-based assessment, both for retrospective purposes of
peer review, and for prospective use in developing software both in general,
and in preparation for peer-review.


### Statistical Software Peer Review Process

Our point of departure for our process is the rOpenSci software peer review
process, which has operated for five years, and has reviewed over >200
packages, primarily in areas of data life cycle management. However, we aim to
reassess this process in light of other models and needs specific to
statistical software. [Chapter 7](#lifecycle) considers a few analogous processes
of peer review, gleaning aspects which may be useful to adopt and adapt for our system.
[Chapter 8](#process) then describes the peer review process in terms of the
series of steps we currently envision comprising our system.

## Community

A core goal of the project is the building and maintenance of a community of
practice that will facilitate dissemination, adoption, and improvement of
standards and peer review. In striving for this goal, the following questions
are important:

-   What outreach should we conduct to maximize diversity and inclusion in the
    process?

-   How should this process involve other relevant communities in fields
    including software development, statistics, applied statistics (in various
    subfields)

-   What fora should we manage for developers, users, reviewers and editors to
    communicate? To what extent should we reuse existing fora from rOpenSci or
    other organizations?

We now briefly consider the three aspects of community relevant to this project:
communities of users, of developers, and of reviewers. Note that several of the
kinds of "metrics" alluded to in the following lines are given explicit
consideration at the end of this document.

**Software use and surrounding community:**

-   What sort of metrics might provide insight into community use of software?

-   How might such community engagement be enhanced to improve such metrics?

**Software development and surrounding community:**

-   What sort of metrics might provide insight into community development of
    software?

-   How might such community engagement be enhanced to improve such metrics?

**Reviewer pool and qualifications:**

-   What is the extent and type of effort expected of reviewers?

-   To what extent might searches for suitable reviewers be automated?

-   What sort of metrics might be useful in such searches?

In each case the project will strive to cultivate diverse, inclusive, and
geographically expansive communities, and metrics to describe such aspects may
also be important, as may automated tools to monitor community engagement and
development. Note that these aspects of community are not explicitly addressed
throughout any of the remainder of this document. It is important the future
revisions return to this point, and ensure that each of the following sections
are appropriately modified to ensure effective consideration and incorporation
of the concerns listed immediately above.

