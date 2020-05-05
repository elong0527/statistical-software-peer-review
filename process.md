
# <span style="color:red;">The Review Process [SEEKING FEEDBACK]</span> {#process}

This section attempts to briefly describe the entire workflow envisioned to
emerge from this project, from tools to enable authors to self-assess packages
prior to submission, to tools for identifying and assigning reviewers, to
methods and tools for structured review interventions after software has been
officially accepted. Although there are several potential general models we
could adapt for our proposed system, we anticipate the general workflow being
based on [github](https://github.com), for which two of the most prominent
current models are rOpenSci's own [submission
process](https://github.com/ropensci/software-review), and that of the [Journal
of Open Source Software (JOSS)](https://github.com/openjournals/joss). Both of
these systems treat submissions as issues within dedicated review repositories,
an approach we intend to adopt.

## Self-Evaluation of Software Prior to Submission {#self-eval}

A strong focus of this project will be the development of tools to assess
software, both generally and for statistical software specifically. One
important aim is to develop tools able to be used by software authors to assess
their own software. Such self-assessment, along with associated standardised
reporting of results, will ease pre-submission enquiries both on the part of
submitting authors, and editors responsible for assessing such enquiries.
Standardised reporting is considered in the [submission
phase](#submission-phase), while the remainder of the present sub-section
considers tools for self-assessment.

Current rOpenSci practices expect authors to assess their software using our
package standards, then editors perform automated assessment using 
[`goodpractice`](https://github.com/mangothecat/goodpractice), a package which
runs [`R CMD
check`](https://cran.r-project.org/doc/manuals/R-exts.html#Checking-packages)
as well as other tests including calculating test coverage, [linting](https://en.wikipedia.org/wiki/Lint_(software)),
and checking for some common coding anti-patterns.
The [`PharmaR` project's](https://pharmar.org) [`riskmetric`](https://github.com/pharmaR/riskmetric) package performs similar functions as well as providing more development-based metrics and providing a more extensible framework.
While authors commonly use the `goodpractice` assessment tool, demonstrated self-assessment is not
currently required at submission.

We anticipate developing a system for self-evaluation of
software, both in generic form able to be widely applied to software regardless
of category, as well as specific tools for statistical software. Many of these
generic assessments have been listed at the end of the preceding
[Framework](#overview), while tools specific to statistical software have been
considered in the preceding [Scope](#scope) chapter.

***Key Considerations*** The primary consideration here is actually one of the
primary considerations of the entire project, which is what sort of tools might
best be developed? It will be possible to develop extremely sophisticated
tools, but at the expense of compromising progress in other important aspects
of the project. Perhaps more than any other aspect of this project, answering
this question will require maintaining a keen awareness of the compromises
necessary to successfully deliver all desired project outcomes.

***Proposal***

1. Authors will be expected to run automated self-assessments prior to submission.
2. We develop a tool for general assessment of software and
   reporting of analytics, with several modules extending to specific
   assessment of statistical software.
3. We simultaneously develop a lightweight infrastructure to enable such
   assessment and reporting to be provided as an online service, so that authors
   can run assessment in the same environment as it will be run at submission.


## Pre-Submission Communication {#presub-comm}

Pre-Submission Communication is the stage currently practised by both rOpenSci
and JOSS whereby authors can enquire as to whether a potential submission is
likely to be considered within scope prior to full submission. Full submissions
can be potentially onerous, and the pre-submission phase represents
a considerable easing of the burden on authors through enabling them to
ascertain the potential suitability of a submission prior to completing a full
submission. For this reason, we intend to adopt and adapt this phase as part of
the new peer-review system. rOpenSci has github issue templates both for
[pre-submissions](https://github.com/ropensci/software-review/blob/master/.github/ISSUE_TEMPLATE/B-submit-a-presubmission-inquiry.md)
and
[submissions](https://github.com/ropensci/software-review/blob/master/.github/ISSUE_TEMPLATE/A-submit-software-for-review.md),
whereas the both pre-submission and submission enquiries to JOSS are initiated
through an external (non-github) website which automatically opens an
[issue on github](https://github.com/openjournals/joss-reviews/issues) with
initial details provided by the submitting author. 

These two systems have two major differences:

1. rOpenSci's pre-submission enquiries are entirely optional, whereas initial
   submissions to JOSS are by default pre-submission enquiries (unless
   originating elsewhere, such as from a completed rOpenSci review).
2. Pre-submission enquiries to rOpenSci serve the singular purposes of
   determining suitability of a potential full submission, whereas those to
   JOSS serve the additional purpose of seeking and assigning reviewers. Having
   found both editors and reviewers, a simple bot command of `@whedon start
   review` suffices to automatically transform the pre-submission to a full
   submission (as a new issue).

JOSS is also trialling the automatic generation and reporting of initial
software metrics in response to pre-submission enquiries, as in [this
example](https://github.com/openjournals/joss-reviews/issues/2149#issuecomment-596179168).
The generation is triggered by the command `@whedon check repository`, and
currently generates a [CLOC (Count Lines of
Code)](https://github.com/AlDanial/cloc) summary of lines devoted to various
computer languages, and a contribution chart with commits, additions, and
deletions from each contributor to the repository. The CLOC output is used to
automatically add labels to the issue identifying the primary computer
languages. 

Determining whether or not a potential submission lies within or beyond scope
requires aligning software with the statistical categories [described
above](#scope). The processing of pre-submission enquiries is accordingly also
expected to entail the categorisation of software. While it may be possible to
automate some aspects of software categorisation, we do not currently envision
such automated tools being developed during the initial stages of this project.

***Proposals***

1.  All submissions be initiated as mandatory pre-submission enquiries which
    may be automatically transitioned to full submissions upon successful
    nomination of editors and reviewers, as for JOSS. This has the distinct
    advantage of separating the search for reviewers from the actual review
    process itself, leaving resultant review issues notably cleaner and more
    focussed. Mandatory pre-submission enquiries also add clarity through
    removing potential ambiguity in deciding between two distinct ways to
    commence submission.
2. The process of pre-submission be partially automated in a similar manner to
   the current system of JOSS, with metrics extended and adapted to the unique
   needs of our own project. Only cursory metrics pertinent to the
   pre-submission stage will be generated, as exemplified by the JOSS system of
   using CLOC output to assign labels identifying primary computer languages.
3. Submitting authors be requested to identify potential categories describing
   their software as part of a pre-submission enquiry, with final
   categorisation being determined through mutual agreement between editors and
   submitting authors.
4. Automation procedures may perhaps be extended by some form of automated
   identification or suggestion of appropriate reviewers, with some aspects of
   the processes described in the following section potentially automatically
   triggered by a pre-submission enquiry.

***Questions***

- Which software metrics might aid the pre-submission process?


## Reviewers / Selection

The solicitation of reviewers is one of the most difficult tasks facing any
peer review system, including both rOpenSci and JOSS. rOpenSci has built up an
extensive network of users, participants, and developers, many of whom are
members of the organisation's [slack](https://slack.com) group. In contrast to
traditional academic journals, submitting authors are *not* requested to
recommend potential reviewers. JOSS explicitly states,

>  if you have any suggestions for potential reviewers then please mention them
here in this thread,

and also points authors of pre-submission enquiries to a curated [list of
potential reviewers (as a google
document)](https://docs.google.com/spreadsheets/d/1PAPRJ63yq9aPC1COLjaQp8mHmEq3rZUzwUYxTulyu78/edit#gid=856801822),
further requesting that authors suggest any potentially appropriate reviewers
from that list. Being a google document, it is simply progressively extended
line-by-line, currently amounting to 1,163 names, likely making it not
particularly easy for authors to find appropriate reviewers.

We will of course extend upon our existing pool of reviewers, and also intend
to cultivate and extend a network of reviewers with expertise in statistical
software throughout the duration of this project. We would also very much like
to develop and utilise tools which may aid the process of finding and
soliciting reviewers, with the remainder of this sub-section exploring a few
options.

### Database of Potential Reviewers

As described, JOSS maintains a database of potential reviewers within
a publicly accessible google document, while rOpenSci maintains theirs in an
private [airtable](https://airtable.com). The [debian system](https://debian.org) also maintains a comprehensive database
of developers, maintainers, and other stakeholders, publicly accessible for
search and via password for restricted access. Private directories have the advantage
of allowing for including notes such as review quality and timeliness that may
not, but also thus need to be more aggressively managed under standards such
as GPDR.  Different database platforms also have different privacy advantages.

### Automating the Identification of Potential Reviewers

It may be worthwhile developing automatic tools to aid identifying appropriate
reviewers. One possibility may be analyses of all openly-available code from
potential reviewers, to somehow measure degree of similarity with a given
submission. While this would be almost impossible to do between different
computer languages, it may be possible within R code alone, through processing
output from the `utils::getParseData` function to identify frequencies of usage
of various function calls.

Such an approach may have important advantages, notably in highlighting
reviewers for reasons other than mere prominence within some form of public
arena. Appropriate development of such a tool should ultimately enable and
empower a more equitable system which is actively designed to avoid any
tendency of submitting authors suggesting similar names of centrally prominent
developers.


## Submission {#submission-phase}

Submission is envisioned to mirror rOpenSci's current submission process to
a certain degree, although we anticipate a more extensive and structured
checklist (or equivalent) system, along with the development of automated tools
triggered in response to submission. For example, the current rOpenSci system
requires editors run diagnostics locally and to paste the
[`goodpractice`](https://github.com/mangothecat/goodpractice) output after
submission. Such a process is
readily automated (as exemplified by JOSS's current [experimental
system](https://github.com/openjournals/joss-reviews/issues/2149#issuecomment-596179168)),
and we expect to extend and refine both the automated checking [described
above](#self-eval), and to collate results within some kind of reporting
system. The self-identification of appropriate categories may also trigger
automated checking using software specific to various categories of statistical
software, with associated output also being automatically inserted into an
issue.

For both JOSS and rOpenSci's, current submissions occur via GitHub Issue [
template](https://github.com/ropensci/software-review/blob/master/.github/ISSUE_TEMPLATE/A-submit-software-for-review.md),
which is primarily a checklist of broad or general attributes with which
both software and associated online repositories are expected to comply. 
Submissions to [JOSS](https://joss.theoj.org) have a more extensive
and detailed [template](https://github.com/openjournals/joss/blob/master/docs/review_checklist.md),
which is filled out after initial submission form.  We may explore submission
via a other mechanisms, forms that automatically generate templates, or an R-based
workflows similar to `devtools::release()`. 

***Key Considerations***

1. Presuming the primary entry point to be via pre-submission enquiries as
   described above means that considerably more information will be available
   upon transitioning to actual submissions, and that the information will
   accordingly be able to be used in a more structured way that better lends
   itself to automation.
2. The tools used to generate such structured information will be largely those
   considered in the first of the above points, as tools able to be used for
   self-evaluation of software.
3. As mentioned above, the actual Submission phase is to be entered in to only
   following successful assignment of willing reviewers (notwithstanding
   potential alternative paths, exemplified by current path from rOpenSci
   review to direct JOSS submission).

***Proposal***

1. Progression from pre-submission to submission be automated as for JOSS.
2. A checklist be automatically generated as part of the opening issue, yet
   more reflecting current rOpenSci practices of affirming compliant aspects of
   a submission, rather than JOSS practices of affirming ultimate reviewer
   judgements.


## Initial Screening

The development and provision of automated tools for initial software
assessment will enable considerably more structured information to be provided
in direct (automated) response to the opening of a submission issue that with
the current rOpenSci system. The ready provision of such structured information
will aid all of the preceding steps, and will also greatly ease the burden of
initial screening of submissions. Software will already have been ascertained
to be within scope, willing reviewers will already have been assigned, and an
extensive report will have been automatically generated summarising a variety
of aspects of software structure, function, and other aspects pertinent to
review.

The primary purpose of the initial screening step will accordingly be for
editors to judge whether or not the totality of submitted data suffices for the
review process to officially start. An additional purpose could be the
assignment of due dates for submission of reviews. JOSS imposes a generic
review period of two weeks, whereas rOpenSci provides opportunity to discuss
appropriate due dates with reviewers.

***Proposal*** 

1. Initial screening involve the two tasks of editors 
   (i) agreeing on submission dates for reviews, and 
   (ii) officially approving a submission.
2. The agreement of submission dates be integrated within the official
   submission issue, rather than the pre-submission issue, so that explicit
   information on review dates remains within the review issue itself.
3. Submission dates be negotiated around an initial suggested duration of one
   month.
4. An automated command be implemented for the review process to be
   "officially" started, which will announce the agreed-upon dates and provide
   any extra information for reviewers. 

Note that JOSS currently implements `@whedon start review` to transition
a pre-submission to a full submission. The above suggestions effectively
translate to breaking this into the two commands of `start submission` to
transition to a full submission and `start review` to commence the actual
review process once approved by editors.



## Review Process

The review processes of rOpenSci and JOSS are qualitatively different, with
JOSS submissions guided by extensive automation, and so being strongly
determined by their
[checklist](https://github.com/openjournals/joss/blob/master/docs/review_checklist.md),
whereas rOpenSci reviews are commenced only after authors complete the
[checklist](https://github.com/ropensci/software-review/blob/master/.github/ISSUE_TEMPLATE/A-submit-software-for-review.md)
(or otherwise explain any anomalies). Reviewers of submissions to rOpenSci are
solicited privately, and privately informed both to read the [*Guide for
Reviewers* chapter](https://devguide.ropensci.org/reviewerguide.html) in the
[*Development, Maintenance, and Peer Review*
Guide](https://devguide.ropensci.org), and that their review must be submitted
with the [*Review
Template*](https://devguide.ropensci.org/reviewtemplate.html#reviewtemplate).
This template serves the same purpose as the automatically-generated JOSS
template, but is to be pasted by authors themselves into their own comments in
the review issue, whereas the JOSS checklist is to be filled out by reviewers
editing the opening comment of the review issue. In short, the rOpenSci
checklist is an official starting point, with reviews submitted at the end with
the help of a template; the JOSS checklist is an official endpoint, empty at
first and progressively completed by each reviewer as they progress through the
review process. 

We envision a system primarily derived from rOpenSci's current system, with
reviews completed through the use of a template and pasted as comments at the
bottom of a github issue. This approach will face one immediate difficulty in
that templates will likely differ through software being described by different
combinations of the [categories described above](#scope). It may suffice to
combine a generic "master" template with category-specific items to be appended
according to the description of submitted software within our list of
categories, although it is important to note that this may exclude review
criteria reflecting unique combinations of categories (for example, a checklist
item appropriate for the visualisation of results from ML algorithms).

The preceding consideration exemplifies the extent to which processes developed
and employed to review statistical software are likely to be strongly
influenced by the kinds of automated tools we develop, both for automated and
self assessment along with associated reporting systems, as well as potentially
for more comprehensive assessments and reporting systems or standards not
otherwise amenable to automation. In the current initial phase of this project
prior to the concrete development of any of these kind of tools, the present
considerations of the review process are accordingly and necessarily generic in
nature. We anticipate this current sub-section becoming particularly more
detailed as the project progress and as we develop project-specific tools for
software assessment.

### Review Templates

As described above, the [JOSS
checklist](https://github.com/openjournals/joss/blob/master/docs/review_checklist.md)
is pre-generated with the opening of each review issue, whereas the [rOpenSci
template](https://devguide.ropensci.org/reviewtemplate.html#reviewtemplate) is
to be completed and pasted in to the issue by reviewers. The two templates are
nevertheless broadly similar, both including the following checklist items:

- [ ] The reviewer has no conflict of interests

**Documentation** The software has:

- [ ] A clear statement of need
- [ ] Installation instructions
- [ ] Function documentation
- [ ] Examples
- [ ] Community guidelines for how to contribute

**Functionality** The software should:

- [ ] Install as documented
- [ ] Meet its own functional claims
- [ ] Meet its own performance claims
- [ ] Have automated tests (considered by JOSS as part of "Documentation")

In addition, JOSS requires reviewers:

- [ ] To agree to abide by a reviewer [code of
   conduct](https://joss.theoj.org/about#code_of_conduct)
- [ ] To confirm that the source code is in the nominated repository
- [ ] To confirm that the software has an appropriate license.
- [ ] To confirm that the submitting author has made major contributions, and that
   the provided list of authors seems appropriate and complete.

rOpenSci insists in turn on the two additional aspects, that software  

- [ ] Has a vignette demonstrating major functionality; and
- [ ] Conforms to the rOpenSci packaging guidelines

Perhaps the most influential difference between the two systems is that the
rOpenSci template concludes with the following lines:


```r
---

### Review Comments
```

The section break and sub-section heading act in combination as a prompt for
reviewers to add their own discursive comments, whereas the JOSS template has
no such field. Accordingly, the majority[^joss-review-claim] of JOSS reviews
merely consist of a completed checklist, whereas *all* rOpenSci reviews are
extensively discursive, with reviewers frequently offering very extensive
comments and analyses of submitted code.

[^joss-review-claim]: That claim has not been substantiated.

These differences may plausibly be interpreted to reflect general differences
in the *cultural practices* of the two review systems, with rOpenSci having
particularly nurtured the cultural practice of extensively discursive reviews,
notably through suggesting that prior reviews ought be perused for good
guidelines on review practices. We intend to continue to foster and encourage
such cultural practices, while at the same time aiming to develop a system for
more structured yet discursive input, in order both to provide more focussed
software reviews, and to lessen the burden on reviewers. We anticipate
commencing the development of such structure in subsequent iterations of the
present document.


### Category-Specific Aspects of Reviews

We defer consideration of category-specific aspects of review until we have
concluded a first round of consultation on the [preceding categorical
definitions](#scope).

### Reviewer Recommendations

Both rOpenSci and JOSS currently work with a binary recommendation scheme of
rejection or acceptance. In both cases, rejection is primarily decided in
response to a pre-preview (JOSS) or pre-submission enquiry (rOpenSci), and
usually for the reason of being out-of-scope (in rOpenSci's case because
software does not fit within the defined categories; and in JOSS's case because
the software does not have a specific research focus). Having obtained approval
to proceed from pre-review to full review, both systems generally work with
package authors to strive for ultimate acceptance. Rejections during this phase
generally only happen when authors stall or abandon ongoing or requested
package development. As long as authors continue to be engaged, reviews very
generally proceed until a submission is accepted.

***Proposal*** While a variety of potential outcomes of the review process are
considered [immediately below](#review-acceptance), reviewers will only be
requested to ultimately check a single box indicating their approval for
software to be accepted. An approved submission may then receive a variety of
labels in response to binary acceptance, as described below.

---

***Proposal***

1. We adopt the current rOpenSci approach of having reviews based on
   a pre-defined template to be completed by reviewers and pasted as the latest
   comment in a review issue, rather than the JOSS model of having reviewers
   edit the initial, opening comment of a review issue.
2. We adopt the current rOpenSci approach of having reviewers testify the time
   spent on their review. We either then:
   (i) Do not provide any information on typical times devoted by other
       reviewers; or
   (ii) Provide summary information including estimates of variation and
        proviso that such information is only intended to avoid reviewers
        otherwise feeling obliged to devote unnecessarily *long* times to
        reviews.
3. We adopt and adapt the general review templates currently used by rOpenSci
   and JOSS, extending both in order to provides as much structured discursive
   feedback as possible.
4. We develop at least examples of category-specific template items to be added
   to the general review template.

## Acceptance / Scoring / Badging {#review-acceptance}

Software being recommended for acceptance by reviews need not be reflected in
a simple "accepted" label. Particularly in the early stages of our system for
peer-reviewing statistical software, we may have some kind of checklist from
which we require authors to ultimately comply with some recommended limited
number of items, yet not all. It may then be worthwhile have a review outcome
that flags this compliance level, and indicates that software will be expected
to retain compliance as our system develops.

Another example may be outcomes which consider the kinds of life cycle models
considered above, in which context it may be useful to have an outcome that
labels software as having passed initial or primary review, yet which will
still be subject to subsequent review some agreed-upon time later. Such systems
of re-assessment will nevertheless not necessarily be (equally) applicable to
all submissions, and so such "progressive labelling" will likely only ever be
optional, and applicable where appropriate.

***Proposal*** We implement a recommendation system which explicitly flags the
version of our system's standards with which reviewed software complies.


## Post-acceptance Dissemination, Publication, etc. 

## Ongoing Maintenance

## Structured Review beyond Acceptance

