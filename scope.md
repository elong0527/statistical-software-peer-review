#  (PART) Scope and Standards {-}



# <span style="color:red;">Scope [SEEKING FEEDBACK]<span> {#scope}

One task in extending the rOpenSci peer review system to statistical software
is defining _scope_ - what software is included or excluded. Defining scope
requires some grouping of packages into categories.  These categories play key
roles in the peer review process and standards-setting.

1. Categorical definitions can determine which kinds of software will be admitted;
2. Different categories of software will be subject to different standards, so
   categories are key to developing standards, review guidance, and automated
   testing.

Creating a categorization or ontology of statistical software can easily become
an overwhelming project in itself. Here we attempt to derive categories or
descriptors which are *practically useful* in the standards and review process,
rather than a formally coherent system. We use a mix of empirical
research on common groupings of software and subjective judgement as to their
use in the review process.

We consider two main types of categories:

1. Categories of software structure, referred to as "software types",
   determined by computer languages and package formats in those languages; and
2. Categories defining different types of statistical software, referred to as
   "statistical categories".

## Software types {#software-types}

### Languages

This project extends existing an software peer-review process run by 
[rOpenSci](https://ropensci.org), and is primarily intended to target the **R**
language. Nonetheless, given the popularity of Python in the field (see
relevant analyses and notes in [Appendix A](#python)), the impact of developing
standards applicable to Python packages must be considered.  rOpenSci also has
a close collaboration with its sister organization,
[pyOpenSci](https://www.pyopensci.org).

In addition it is particularly important to note that many **R** packages
include code from a variety of other languages. The following table summarises
statistics for the top ten languages from all 15,576 [CRAN](https://cran.r-project.org)
packages as of Tue May 05 2020 (including only code from
the `/R`, `/src`, and `/inst` directories of each package).


Table: (\#tab:language-table)Proportion of code lines in different languages in all CRAN packages.

language       lines         proportion
-------------  -----------  -----------
R              21,687,052         0.451
C/C++ Header   6,438,969          0.134
HTML           4,774,583          0.099
C              4,723,903          0.098
C++            4,391,283          0.091
JavaScript     1,270,762          0.026
Fortran 77     798,821            0.017
JSON           685,641            0.014
CSS            570,436            0.012
Rmd            489,634            0.010

Close to one half of all code in all R packages to date has been written in the
R language, clearly justifying a primary focus upon that language. Collating
all possible ways of packaging and combining C and C++ code yields
15,554,155 lines or code or
32% of all code, indicating that
77% of all code has been
written in either R or C/C++. Three of these top ten languages are likely
related to web-based output (HTML, JavaScript, and CSS), representing a total
of 14% of all code. While this is
clearly a significant proportion, and while this *may* reflect an equivalent
high frequency of code devoted to some form of web-based visualisation, these
statistics represent *all* R packages. In many cases this represents extensive
headers in supplementary documentation. There is no simple way to identify which
of these might be considered statistical code in web-based languages, but knowing that there are
packages exclusively constructed to generate web-based visualisations and documentation in
a generic sense suggests that this value may be taken as an upper limit on
the likely frequency of these types of visualisation packages (or parts thereof) in the
context of statistical software.


***Key considerations***:

- Expansion into the Python ecosystem has great potential for impact, but goes
  beyond the general areas of expertise in the core ecosystem. (And Python code
  represents just
  162,339
  lines of code, or
  0.3%
  of all code within all R packages.)
- Compiled languages within R packages are core to many statistical
  applications; excluding them would exclude core functionality the project
  aims to addressed. The majority of compiled code is nevertheless C and/or
  C++, with Fortran representing under 2% of all code.
- Languages used for web-based visualisations comprise a significant proportion
  (14%) of all code. While this
  potentially indicates a likely importance of visualisation routines, this
  figure reflects general code in all R packages, and the corresponding
  proportion within the specific context of statistical software may be
  considerably lower.
- Any decision to include visualisation software and routines within our scope
  will likely entail an extension of linguistic scope to associated languages
  (HTML, JavaScript, and maybe CSS).

### Structure

R has a [well-defined
system](https://cran.r-project.org/doc/manuals/R-exts.html) for structuring
software packages" Other forms of packaging **R** software may nevertheless be
considered within scope. These may include

1. Python-like systems of [modules for **R**](https://github.com/klmr/modules);
2. Packaging appropriate for other languages (such as Python) yet with some
   interface with the R language;
3. R interfaces ("wrappers") to algorithms or software developed independently
   in different languages, and which may or may not be bundled as a standard
   R package; and
4. Web applications such as Shiny packages.

**Key considerations**: Allowing non-package forms of code into the peer review
system could potentially bring in a large pool of code typically published
alongside scientific manuscripts, and web applications are a growing, new area
of practice. However, there is far less standardization of code structure to
allow for style guidelines and automated testing in these cases.


## Statistical Categories {#scope-categories}

As alluded to at the outset of this chapter, a primary task of this project
will be to categorise statistical software in order to:

- Determine the extent to which software fits within scope
- Enable fields of application of software to be readily identified
- Enable determination of applicable standards
- Enable discernment of appropriate reviewers

Different categories of statistical software will likely have different
standards, yet there will nevertheless be general standards applicable
regardless of categories. 

### Examples of Statistical Software

We now consider a few brief categorical examples, to illustrate the kinds of
decisions such a process of categorisation will likely face.

---

-   [**gtsummary**](https://github.com/ropensci/software-review/issues/334),
    submitted to rOpenSci and reject as out-of-scope.


    Creates presentation-ready tables summarizing data sets, regression models,
    and more. The code to create the tables is concise and highly
    customizable. Data frames can be summarized with any function,
    e.g. mean(), median(), even user-written functions. Regression models are
    summarized and include the reference rows for categorical variables.
    Common regression models, such as logistic regression and Cox proportional
    hazards regression, are automatically identified and the tables are
    pre-filled with appropriate column headers.

    This package appears not to contain any algorithmic implementations, yet is
    clearly aimed at enhancing a purely statistical workflow. Such a submission
    requires answering the question of whether software categorized as
    "workflow" only and which does not correspond to any other of the above
    categories, may be deemed in scope?

---

-   [greta: simple and scalable statistical modelling in
    R](https://joss.theoj.org/papers/10.21105/joss.01601), published in JOSS.


    greta is an package for statistical modelling in R (R Core Team, 2019) that
    has three core differences to commonly used statistical modelling software
    packages:

    -   greta models are written interactively in R code rather than in a
        > compiled domain specific language.

    -   greta can be extended by other R packages; providing a fully-featured
        > package management system for extensions.

    -   greta performs statistical inference using TensorFlow (Abadi et al.,
        > 2015), enabling it to scale across modern high-performance computing
        > systems.

    The `greta` package might be considered predominantly an interface to
    TensorFlow, yet it provides a new way to specify and work with purely
    statistical models. This might be considered under both workflow and wrapper
    categories, and serves here to illustrate the question of whether wrappers
    around, in this case, externally-installed software might be considered in
    scope? And if so, to what extent ought aspects of such externally-installed
    software also be directly addressed within a review process?

---

-   [**modelStudio**](https://joss.theoj.org/papers/10.21105/joss.01798),
    published in JOSS.


    The `modelStudio`R package automates the process of model exploration. It
    generates advanced interactive and animated model explanations in the form
    of a serverless HTML site. It combines R(R Core Team, 2019) with D3.js
    (Bostock, 2016) to produce plots and descriptions for various local and
    global explanations. Tools for model exploration unite with tools for EDA
    to give a broad overview of the model behaviour.

    As with `gtsummary` above, this is clearly a package intended to enhance a
    workflow, and furthermore one which primarily serves to generate summary
    output as a `ht``ml` document, yet the models it considers, and all aspects
    of output produced, are purely statistical. This package could meet both
    workflow and visualization categories, and serves here to illustrate
    difficulties in considering the latter of these. The `D3.``js` library
    contains numerous indubitably statistical routines, and so this package
    might be argued to be a wrapper in the same category as `greta` is a wrapper
    around `TensorFlow`. An important question likely to arise in considering
    both of these is the extent to which the library being wrapped should also
    be *predominantly statistical* for a package to be in scope? (A requirement
    which `greta` would more easily fulfil than `gtsummary`.)

---

We now consider potential categories within the general domain of statistical
software. In order to derive a realistic categorisation, we used empirical data
from several sources of potential software submissions, including all
apparently "statistical" R packages published in the [Journal of Open Source
Software (JOSS](https://joss.theoj.org)), packages published in the [Journal of
Statistical Software](https://www.jstatsoft.org/index), software presented at
the 2018 and 2019 Joint Statistical Meetings (JSM), and Symposia on Data
Science and Statistics (SDSS), well as CRAN task views. We have also compiled
a list of the descriptions of [all packages rejected by
rOpenSci](https://github.com/mpadge/statistical-software/blob/master/abstracts/ropensci-abstracts.md)
as being out of current scope because of current inability to consider
statistical packages, along with a selection of [recent statistical
R packages](https://github.com/mpadge/statistical-software/blob/master/abstracts/joss-abstracts.md)
accepted by JOSS. (The full list of all R package published by JOSS can be
viewed at <https://joss.theoj.org/papers//in/R>).

We allocated one or more key words (or phrases) to each abstract, and use the
frequencies and inter-connections between these to inform the following
categorisation are represented in the [interactive
graphic](https://ropenscilabs.github.io/statistical-software/abstracts/network-terms/index.html)
(also included in the [Appendix](#appendix-keywords)), itself derived from
analyses of abstracts from all statistical software submitted to both rOpenSci
and JOSS. (Several additional analyses and graphical representations of these
raw data are included an [auxiliary github
repository](https://github.com/ropenscilabs/statistical-software).) The primary
nodes that emerge from these empirical analyses (with associated *relative*
sizes in parentheses) are shown in the following table.


Table: (\#tab:top-terms)Most frequent key words from all JOSS abstracts (N = 92) for statistical software. Proportions are scaled *per abstract*, with each abstract generally having multiple key words, and so sum of proportions exceeds one.

  n  term                              proportion
---  -------------------------------  -----------
  1  ML                                     0.133
  2  statistical indices and scores         0.111
  3  visualization                          0.111
  4  dimensionality reduction               0.100
  5  probability distributions              0.100
  6  regression                             0.100
  7  wrapper                                0.100
  8  estimates                              0.089
  9  Monte Carlo                            0.089
 10  Bayesian                               0.078
 11  categorical variables                  0.078
 12  EDA                                    0.078
 13  networks                               0.078
 14  summary statistics                     0.067
 15  survival                               0.067
 16  workflow                               0.067




The top key words and their inter-relationships within the main [network
diagram](https://ropenscilabs.github.io/statistical-software/abstracts/network-terms/index.html)
were used to distinguish the following primary categories representing all
terms which appear in over 5% of all abstracts, along with the two additional
categories of "spatial" and "education". We have excluded the key word
"Estimates" as being too generic to usefully inform standards, and have also
collected a few strongly-connected terms into single categories.


Table: (\#tab:methods-categories)Proposed categorisation of statistical software, with corresponding proportions of all JOSS software matching each category

  n  term                                            proprtion  comment                                                                                                                                                                                       
---  ---------------------------------------------  ----------  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  1  Bayesian & Monte Carlo                              0.167                                                                                                                                                                                                
  2  dimensionality reduction & feature selection        0.144  Commonly as a result of ML algorithms                                                                                                                                                         
  3  ML                                                  0.133                                                                                                                                                                                                
  4  regression/splines/interpolation                    0.133  Including function data analysis                                                                                                                                                              
  5  statistical indices and scores                      0.111  Software generally intended to produce specific indices or scores as statistical output                                                                                                       
  6  visualization                                       0.111                                                                                                                                                                                                
  7  probability distributions                           0.100  Including kernel densities, likelihood estimates and estimators, and sampling routines                                                                                                        
  8  wrapper                                             0.100                                                                                                                                                                                                
  9  categorical variables                               0.078  Including latent variables, and those output from ML algorithms. Note also that method for dimensionality reduction (such as clustering) often transform data to categorical forms.           
 10  Exploratory Data Analysis (EDA)                     0.078  Including information statistics such as Akaike's criterion, and techniques such as random forests. Often related to workflow software.                                                       
 11  networks                                            0.078                                                                                                                                                                                                
 12  summary statistics                                  0.067  Primarily related in the empirical data to regression and survival analyses, yet clearly a distinct category of its own.                                                                      
 13  survival                                            0.067  strongly related to EDA, yet differing in being strictly descriptive of software *outputs* whereas EDA may include routines to explore data *inputs* and other pre-output stages of analysis. 
 14  workflow                                            0.067  Often related to EDA, and very commonly also to ML.                                                                                                                                           
 15  spatial                                             0.033  Also an important intermediate node connecting several other nodes, yet defining its own distinct cluster reflecting a distinct area of expertise.                                            
 16  education                                           0.044                                                                                                                                                                                                


The full network diagram can then be reduced down to these categories only,
with interconnections weighted by all first- and second-order interconnections
between intermediate categories, to give the following, simplified diagram
(in which "scores" denotes "statistical indices and scores"; with the diagram
best inspected by dragging individual nodes to see their connections to
others).

<!--html_preserve--><div id="htmlwidget-aa5efd67888a3c96c9ff" style="width:672px;height:480px;" class="visNetwork html-widget"></div>
<script type="application/json" data-for="htmlwidget-aa5efd67888a3c96c9ff">{"x":{"nodes":{"label":["Bayes/MC","dimensionality reduction","ML","regression","scores","visualization","probability distributions","wrapper","categorical variables","EDA","networks","summary statistics","survival","workflow","education","spatial"],"value":[15,13,12,11,10,10,9,9,7,7,7,6,6,6,4,3],"id":["Bayes/MC","dimensionality reduction","ML","regression","scores","visualization","probability distributions","wrapper","categorical variables","EDA","networks","summary statistics","survival","workflow","education","spatial"]},"edges":{"from":["Bayes/MC","Bayes/MC","Bayes/MC","Bayes/MC","Bayes/MC","Bayes/MC","Bayes/MC","Bayes/MC","Bayes/MC","Bayes/MC","Bayes/MC","categorical variables","categorical variables","categorical variables","dimensionality reduction","dimensionality reduction","dimensionality reduction","dimensionality reduction","dimensionality reduction","dimensionality reduction","dimensionality reduction","EDA","EDA","EDA","EDA","EDA","EDA","EDA","education","education","education","education","education","education","education","ML","ML","ML","ML","ML","ML","ML","ML","networks","networks","probability distributions","regression","regression","scores","scores","summary statistics","summary statistics","summary statistics","survival","visualization","visualization","workflow"],"to":["EDA","education","ML","networks","regression","scores","spatial","summary statistics","survival","visualization","wrapper","ML","networks","scores","Bayes/MC","ML","regression","spatial","survival","visualization","workflow","education","ML","networks","summary statistics","visualization","workflow","wrapper","dimensionality reduction","ML","networks","summary statistics","visualization","workflow","wrapper","networks","probability distributions","regression","summary statistics","survival","visualization","workflow","wrapper","visualization","wrapper","regression","survival","visualization","visualization","workflow","visualization","workflow","wrapper","visualization","workflow","wrapper","wrapper"],"width":[5,5,5,5,5,5,5,5,5,5,5,2.36111111111111,2.36111111111111,2.36111111111111,3.88888888888889,3.88888888888889,3.88888888888889,3.88888888888889,3.88888888888889,3.88888888888889,3.88888888888889,2.77777777777778,2.77777777777778,2.77777777777778,2.77777777777778,2.77777777777778,2.77777777777778,2.77777777777778,1.66666666666667,1.66666666666667,1.66666666666667,1.66666666666667,1.66666666666667,1.66666666666667,1.66666666666667,2.5,2.5,2.5,2.5,2.5,2.5,2.5,2.5,0.972222222222222,0.972222222222222,0.555555555555556,1.66666666666667,1.66666666666667,0.694444444444444,0.694444444444444,0.694444444444444,0.694444444444444,0.694444444444444,0.277777777777778,0.416666666666667,0.416666666666667,0.138888888888889]},"nodesToDataframe":true,"edgesToDataframe":true,"options":{"width":"100%","height":"100%","nodes":{"shape":"dot"},"manipulation":{"enabled":false}},"groups":null,"width":null,"height":null,"idselection":{"enabled":false},"byselection":{"enabled":false},"main":null,"submain":null,"footer":null,"background":"rgba(0, 0, 0, 0)"},"evals":[],"jsHooks":[]}</script><!--/html_preserve-->

We intend, at least initially, to use these categories to define and guide the
assessment of statistical software. Standards considered under any of the
ensuing categories must be developed with reference to inter-relationships
between categories, and in particular to potential ambiguity within and between
any categorisation. An example of such ambiguity, and of potential difficulties
associated with categorisation, is the category of "network" software which
appropriate describes the
[`grapherator`](https://github.com/jakobbossek/grapherator) package (with
accompanying [JOSS paper](https://joss.theoj.org/papers/10.21105/joss.00528))
which is effectively a distribution generator for data represented in
a particular format that happens to represent a graph; and three JSM
presentations, one on [network-based clustering of high-dimensional
data](https://ww2.amstat.org/meetings/jsm/2018/onlineprogram/AbstractDetails.cfm?abstractid=327171),
one on [community structure in dynamic
networks](https://ww2.amstat.org/meetings/jsm/2018/onlineprogram/AbstractDetails.cfm?abstractid=328764)
and one on [Gaussian graphical
models](https://ww2.amstat.org/meetings/jsm/2018/onlineprogram/AbstractDetails.cfm?abstractid=328764).
Standards derived for network software must accommodate such diversity of
applications, and must accommodate software for which the "network" category
may pertain only to some relatively minor aspect, while the primary algorithms
or routines may not be related to network software in any direct way.

### Bayesian and Monte Carlo Routines

Packages implementing or otherwise relying on Bayesian or Monte Carlo routines
represent form the central "hub" of all categories in the above diagram,
indicating that even though this category is roughly equally common to other
categories, software in this category is more likely to share more other
categories. In other words, this is the leading "hybrid" category within which
standards for all other categories must also be kept in mind. Some examples of
software in this category include:

1. The [`bayestestR`
   package](https://joss.theoj.org/papers/10.21105/joss.01541) "provides tools
   to describe ... posterior distributions"
2. The [`ArviZ` package](https://joss.theoj.org/papers/10.21105/joss.01143) is
   a python package for exploratory analyses of Bayesian models, particularly
   posterior distributions.
3. The [`GammaGompertzCR`
   package](https://joss.theoj.org/papers/10.21105/joss.00216) features
   explicit diagnostics of MCMC convergence statistics.
4. The [`BayesianNetwork`
   package](https://joss.theoj.org/papers/10.21105/joss.00425) is in many ways
   a wrapper package primarily serving a `shiny` app, but also accordingly
   a package in both education and EDA categories.
5. The [`fmcmc` package](https://joss.theoj.org/papers/10.21105/joss.01427) is
   a "classic" MCMC package which directly provides its own implementation, and
   generates its own convergence statistics.
7. The [`rsimsum` package](https://joss.theoj.org/papers/10.21105/joss.00739)
   is a package to "summarise results from Monte Carlo simulation studies".
   Many of the statistics generated by this package may prove useful in
   assessing and comparing Bayesian and Monte Carlo software in general. (See
   also the [`MCMCvis`
   package](https://joss.theoj.org/papers/10.21105/joss.00640), with more of
   a focus on visualisation.)
8. The [`walkr` package](https://joss.theoj.org/papers/10.21105/joss.00061) for
   "MCMC Sampling from Non-Negative Convex Polytopes" is indicative of the
   difficulties of deriving generally applicable assessments of software in
   this category, because MCMC *sampling* relies on fundamentally different
   inputs and outputs than many other MCMC routines.

***Key Considerations*** 

- The extent to which the output of Bayesian routines with uninformative prior inputs can or do
  reflect equivalent frequentist analyses.
- Ways to standardise and compare diagnostic statistics for convergence of MCMC
  routines.
- Forms and structures of data using in these routines are very variable,
  likely making comparison among algorithms difficult.

### Dimensionality Reduction and Feature Selection

Many packages either implement or rely upon techniques for dimensionality
reduction or feature selection. One of the primary problems presented by such
techniques is that they are constrained to yield a result independent on any
measure of correctness of accuracy [@estivill-castro_why_2002]. This can make
assessment of the accuracy or reliability of such routines difficult. Moreover,
dimensionality reduction techniques are often developed for particular kinds of
input data, reducing abilities to compare and contrast different
implementations, as well as to compare them with any notional reference
implementations.

1. [`ivis`](https://joss.theoj.org/papers/10.21105/joss.01596) implements
   a dimensionality reduction technique using a "Siamese Neural Network
   architecture.
2. [`tsfeaturex`](https://joss.theoj.org/papers/10.21105/joss.01279) is
   a package to automate "time series feature extraction," which also provides
   an example of a package for which both input and output data are generally
   incomparable with most other packages in this category.
3. [`iRF`](https://joss.theoj.org/papers/10.21105/joss.01077) is another
   example of a generally incomparable package within this category, here one
   for which the features extracted are the most distinct predictive features
   extracted from repeated iterations of random forest algorithms.
4. [`compboost`](https://joss.theoj.org/papers/10.21105/joss.00967) is
   a package for component-wise gradient boosting which may be sufficient
   general to potentially allow general application to problems addressed by
   several packages in this category. 
5. The [`iml`](https://joss.theoj.org/papers/10.21105/joss.00786) package may
    offer usable functionality for devising general assessments of software
    within this category, through offering a "toolbox for making machine
    learning models interpretable" in a "model agnostic" way.

***Key Considerations***

- It is often difficult to discern the accuracy of reliability of
  dimensionality reduction techniques.
- It is difficult to devise general routines to compare and assess different
  routines in this category, although possible starting points for the
  development of such may be offered by the
  [`compboost`](https://joss.theoj.org/papers/10.21105/joss.00967) and
  [`iml`](https://joss.theoj.org/papers/10.21105/joss.00786) packages.

### Machine Learning

Machine Learning (ML) routines play a central role in modern statistical
analyses, and the ML node in the above diagram is roughly equally central,
and equally connected, to the Bayesian and Monte Carlo node. Machine Learning
algorithms represent perhaps some of the most difficult algorithms for which to
develop standards and methods of comparison. Both input and output data can be
categorically different or even incomparable, while even where these may be
comparable, the abiding aims of different ML algorithms can differ sufficiently
to make comparison of outputs to otherwise equivalent inputs largely
meaningless. A few potentially fruitful routes towards productive comparison
may nevertheless be discerned, here according to the sub-domains of input data,
output data, and algorithms.

***Input Data*** One promising R package which may prove very useful for
standardising and comparing data used as input to ML algorithms is the
[`vtreat`](https://joss.theoj.org/papers/10.21105/joss.00584) package that
"prepares messy real world data for predictive modeling in a reproducible and
statistically sound manner." The routines in this package perform a series of
tests for general sanity of input data, and may prove generally useful as part
of a recommended ML workflow.

***Algorithms*** A number of packages attempt to offer unified interfaces to
a variety of ML algorithms, and so may be used within the context of the
present project either as potential recommended standards, or as ways by which
different algorithms may be compared within a standard workflow. Foremost among
such packages are 
[`mlr3`](https://joss.theoj.org/papers/10.21105/joss.01903), which represents
one of the core R packages for ML, developed by the key developers of previous
generations of ML software in R. It offers a modular and extensible interface
for a range of ML routines, and may prove very useful in comparing different ML
routines and implementations.

***Output Data*** There are several extant packages for (post-)processing data
output from ML algorithms. Many, perhaps even most, of these primarily aim to
derive insightful visualisations of output, whether in interactive
(JavaScript-based) form, as with the
[`modelStudio`](https://joss.theoj.org/papers/10.21105/joss.01798) or
[`modelDown`](https://joss.theoj.org/papers/10.21105/joss.01444) packages, or
more static plots using internal graphical routines from R, as in the [`iml`
(Interpretable Machine
Learning)](https://joss.theoj.org/papers/10.21105/joss.00786) package. The
latter package offers a host of additional functionality useful in interpreting
the output of ML algorithms, and which may prove useful in general
standards-based contexts.

Potential "edge cases" which may be difficult to reconcile with the general
aspects described above include the following:

1. [`ReinforcementLearning`](https://joss.theoj.org/papers/10.21105/joss.01087)
   is a simulation package employing ML routines to enable agents to learn
   through trial and error. It is an example of a package with inputs and
   outputs which may be difficult to compare with other ML software, and
   difficult to assess via general standards.
2. [`BoltzMM`](https://joss.theoj.org/papers/10.21105/joss.01193) is an
   implementation of a particular class of ML algorithms ("Boltmann Machines"),
   and so provides an obverse example to the above, for which in this case
   inputs and outputs may be compared in standard ways, yet the core algorithm
   may be difficult to compare.
3. [`dml`](https://joss.theoj.org/papers/10.21105/joss.01036) is a collection
   of different ML algorithms which perform the same task ("distance metric
   learning"). While comparing algorithms *within* the package is obviously
   straightforward, comparison in terms of external standards may not be.

### Regression and Interpolation

This category represents the most important intermediate node in the above
network graphic between ML and Bayesian/Monte Carlo algorithms, as well as
being strongly connected to several other nodes. While many regression or
interpolation algorithms are developed as part of general frameworks within
these contexts, there are nevertheless sufficiently many examples of regression
and interpolation algorithms unrelated to these contexts to warrant the
existence of this distinct category. That said, algorithms within this category
share very little in common, and each implementation is generally devised for
some explicit applied purpose which may be difficult to relate to any other
implementations in this category.

Perhaps one feature which almost of the following examples share in common is
input and output data in (potentially multi-dimensional) vector format, very
generally (but not exclusively) in numeric form. This may be one category in
which the development of a system for [property-based
testing](#overview-testing), like the [`hypothesis` framework for
python](https://hypothesis.works) may be particularly useful. Such a system
would facilitate tests in response to a range of differently input
*structures*, such as values manifesting different distributional properties.
Property-based testing is likely to be a particularly powerful technique for
uncovering faults in regression and interpolation algorithms.

Examples of the diversity of software in this category include the following.

1. [`xrnet`](https://joss.theoj.org/papers/10.21105/joss.01761) to perform
   "hierarchical regularized regression to incorporate external data", where
   "external data" in this case refers to structured meta-data as applied to
   genomic features.
2. [`survPen`](https://joss.theoj.org/papers/10.21105/joss.01434) is, "an
    R package for hazard and excess hazard modelling with multidimensional
    penalized splines"
3. [`areal`](https://joss.theoj.org/papers/10.21105/joss.01221) is, "an
    R package for areal weighted interpolation".
4. [`ChiRP`](https://joss.theoj.org/papers/10.21105/joss.01287) is a package
    for "Chinese Restaurant Process mixtures for regression and clustering",
    which implements a class of non-parametric Bayesian Monte Carlo models.
5. [`klrfome`](https://joss.theoj.org/papers/10.21105/joss.00722) is a package
    for, "kernel logistic regression on focal mean embeddings," with a specific
    and exclusive application to the prediction of likely archaeological sites.
6. [`gravity`](https://joss.theoj.org/papers/10.21105/joss.01038) is a package
    for "estimation methods for gravity models in R," where "gravity models"
    refers to models of spatial interactions between point locations based on
    the properties of those locations.
7. [`compboost`](https://joss.theoj.org/papers/10.21105/joss.00967) is an
     example of an R package for gradient boosting, which is inherently
     a regression-based technique, and so standards for regression software
     ought to consider such applications.
8. [`ungroup`](https://joss.theoj.org/papers/10.21105/joss.00937) is, "an
     R package for efficient estimation of smooth distributions from coarsely
     binned data." As such, this package is an example of regression-based
     software for which the input data are (effectively) categorical. The
     package is primarily intended to implement a particular method for
     "unbinning" the data, and so represents a particular class of
     interpolation methods.
9. [`registr`](https://joss.theoj.org/papers/10.21105/joss.00557) is
     a package for "registration for exponential family functional data," where
     registration in this context is effectively an interpolation method
     applied within a functional data analysis context.


One package which may be potential general use is the
[`ggeffects`](https://joss.theoj.org/papers/10.21105/joss.00772) package for
"tidy data frames of marginal effects from regression models." This package
aims to make statistics quantifying marginal effects readily understandable,
and so implements a standard (tidyverse-based) methodology for representing and
visualising statistics relating to marginal effects.



### Statistical Indices and Scores

Many packages are designed to provide one or more specific statistical indices,
scores, or summary statistics from some assumed type of input data. Methodology
used to derive indices or scores may draw on many of the methods or algorithms
considered in the first category above or are often field-specific, arithmetic
calculations.  Such software may likely be considered within its own category
through a singular aim to provide particular indices or scores, in contrast
with more generic "Methods and Algorithms" software which offers more
abstraction or modeled approach.  Some examples include:

1. The
   [`spatialwarnings` package](https://github.com/spatial-ews/spatialwarnings) which provides "early-warning signal of
   ecosystem degradation," where these signals and associated indices are
   highly domain-specific.
1. The
   [`heatsaveR` package](https://github.com/robwschlegel/heatwaveR) which calculates and displays marine heatwaves using
   specific indices established in previously-published literature.
1. The
   [`hhi` package](https://github.com/pdwaggoner/hhi) which calculates and visualizes "Herfindahl-Hirschman Index
   Scores," which are measures of numeric concentration.
1. The
   [`DscoreApp` package](https://github.com/OttaviaE/DscoreApp) which provides an index (the "D-Score") to quantify
   the results of
   [Implicit Association Tests](https://en.wikipedia.org/wiki/Implicit-association_test).
1. The
   [`thurstonianIRT` package](https://github.com/paul-buerkner/thurstonianIRT) (with accompanying
   [JOSS paper](https://joss.theoj.org/papers/10.21105/joss.01662)) for score forced-choice questionnaires using
   ["Item Response Theory"](https://en.wikipedia.org/wiki/Item_response_theory).


 ***Key Considerations***:  Such packages can generally be reviewed for correctness
(or accuracy/precision) in comparison to pseudocode, reference implementations, or reference data sets
and in this way have can be straightforwardly  evaluated. More complex indices and
scores will require many of the considerations in the "methods and algorithms"
category above. In many cases,
the field-specific nature of indices and scores may tightly tie the algorithm
implementation to certain data input formats or workflows common to practitioners.
They may have considerable overlap with workflow packages (below). There is
also the possibility that some indices could be considered "trivial" arithmetic
calculations. We may wish to consider some qualitative standard for additional
utility that such packages would provide.  


### Visualisation

While many may consider software primarily aimed at visualisation to be out of
scope, there are nevertheless cases which may indeed be within scope, notably
including the
[`ggfortify` package](https://github.com/sinhrks/ggfortify) which allows results of statistical tests to be
"automatically" visualised using the
[`ggplot2` package](https://ggplot2.tidyverse.org). The list of "fortified" functions on the packages
[webpage](https://github.com/sinhrks/ggfortify) clearly indicates the very predominantly statistical scope of this
software which is in effect a package for statistical reporting, yet in visual
rather than tabular form. Other examples of visualisation software include:

1. The
   [`modelStudio` package](https://github.com/ModelOriented/modelStudio) (with accompanying
   [ JOSS paper](https://joss.theoj.org/papers/10.21105/joss.01798)), which is also very much a workflow package.
3. The
   [`shinyEFA` package](https://github.com/PsyChiLin/EFAshiny) (with accompanying
   [JOSS paper](https://joss.theoj.org/papers/10.21105/joss.00567)) which provides a, "User-Friendly Shiny Application for
   Exploratory Factor Analysis."
3. The
   [`autoplotly` package](https://github.com/terrytangyuan/autoplotly) (with accompanying
   [JOSS paper](https://joss.theoj.org/papers/10.21105/joss.00657)) which provides, "Automatic Generation of Interactive
   Visualisations for Statistical Results", primarily by porting the output of
   the authors' above-mentioned
   [`ggfortify` package](https://github.com/sinhrks/ggfortify) to
   [`plotly.js`](https://github.com/plotly/plotly.js).

***Key considerations***: The quality or utility visualization techniques can
be strongly subjective, but also may be evaluated using standardized principles
if the community can come to a consensus on those principles. Such
considerations may be context-dependent - e.g., the requirements of
a diagnostic plot designed to support model-checking are different from that
designed to present raw data or model results to a new audience.  This implies
that the intended purpose of the visualization should be well-defined.

Whether or not visualization is in-scope, many software packages with other
primary purposes also include functions to visualise output. Visualization will
thus never be *strictly* out of scope.  However one option is not to include
*primarily* visualization packages, or only *statistical* visualization packages
in which visualization is closely tied to another category or purpose. 

Visualisation packages will include numerical or statistical routines for
transforming data from raw form to graphics, which can be evaluated for correctness
or accuracy.

### Probability Distributions

The category of probability distributions is an outlier in the preceding
network diagram, connected only to ML and regression/interpolation algorithms.
The latter category was identified as one in which property-based testing was
likely to be useful, within similar suggestions applying to the present
category, particularly through enabling routines to be tested for robustness
against a variety of perturbations to assumed distributional forms.

Packages which fall exclusively within this category and not within any 
of the other categories considered here include:

1. [`univariateML`](https://joss.theoj.org/papers/10.21105/joss.01863) which
   is, "an R package for maximum likelihood estimation of univariate
   densities," which support more than 20 different forms of probability
   density.
2. [`kdensity`](https://joss.theoj.org/papers/10.21105/joss.01566) which is,
   "An R package for kernel density estimation with parametric starts and
   asymmetric kernels." This package implements an effectively non-parametric
   approach to estimating probability densities.
3. [`overlapping`](https://joss.theoj.org/papers/10.21105/joss.01023), which
   is, "a R package for estimating overlapping in empirical distributions."

The obverse process from estimating or fitting probability distributions is
arguably drawing samples from defined distributions, of which the 
[`humanleague`](https://joss.theoj.org/papers/10.21105/joss.00629) package is
an example. This package has a particular application in synthesis of discrete
populations, yet the implementation is quite generic and powerful.



### Wrapper Packages

"Wrapper" packages provide an interface to previously-written software, often
in a different computer language to the original implementation. While this
category is reasonably unambiguous, there may be instances in which a "wrapper"
additionally offers extension beyond original implementations, or in which only
a portion of a package's functionality may be "wrapped."  Rather than
internally bundling or wrapping software, a package may also serve as a wrapper
thorough providing access to some external interface, such as a web server.
Examples of potential wrapper packages include the following:

1. The
   [`greta` package](https://github.com/greta-dev/greta)
   (with accompanying
   [JOSS article](https://joss.theoj.org/papers/10.21105/joss.01601)) "for
   writing statistical models and fitting them by MCMC and optimisation"
   provides a wrapper around google's
   [`TensorFlow` library](https://www.tensorflow.org). It is also clearly a workflow package, aiming to
   provide a single, unified workflow for generic machine learning processes
   and analyses.
2. The
   [`nse` package](https://github.com/keblu/nse) (with accompanying
   [JOSS paper](https://joss.theoj.org/papers/10.21105/joss.00172)) which
   offers "multiple ways to calculate numerical standard errors (NSE) of
   univariate (or multivariate in some cases) time series," through providing
   a unified interface to several other R packages to provide more than 30 NSE
   estimators. This is an example of a wrapper package which does not wrap
   either internal code or external interfaces, rather it effectively "wraps"
   the algorithms of a collection of R packages.

***Key Considerations***:  For many wrapper packages it may not be feasible
for reviewers (or authors) to evaluate the quality or correctness of the wrapped
software, so review could be limited to the interface or added value provided,
or the statistical routines within. 

Wrapper packages include the extent of functionality represented by wrapped
code, and the computer language being wrapped. 
- *Internal or External:* Does the software *internally* wrap of bundle
  previously developed routines, or does it provide a wrapper around some
  external service? If the latter, what kind of service (web-based, or some
  other form of remote access)?
- *Language:* For internally-bundled routines, in which computer language
  e the routines written? And how are they bundled? (For R packages: In
  `./src`? In `./inst`? Elsewhere?)
- *Testing:* Does the software test the correctness of the wrapped component?
  Does it rely on tests of the wrapped component elsewhere?
- *Unique Advances:* What unique advances does the software offer beyond
  those offered by the (internally or externally) wrapped software?
  

### Categorical Variables

Like the category of probability distributions, software for categorical
variables also represents an outlier category that nevertheless encapsulates
unique software. This category is particularly prominent in software developed
to support social sciences, and its inclusion may be justified on that basis
alone: The mere inclusion of this category would open up the general process of
peer-reviewing of statistical software to much broader areas of the social
sciences than would be admissible without this category.

Most software in this category generally takes categorical input data and
outputs some form of quantitative response or summary statistic. Input data
vary from quantitative intervals to discrete orders or ranks to (cross-)tables
of categorical frequencies. Most packages seek to derive quantitative estimates
from categorical inputs, although the various estimates are of course in no way
comparable.

It thus seems exceedingly difficult if not impossible to derive general
standards for software in this category, even though we currently recommend
inclusion because of the unique importance in the social sciences. Examples of
software for categorical variables include the following.

1. [`perccalc`](https://joss.theoj.org/papers/10.21105/joss.01796) is, "An
   R package for estimating percentiles from categorical variables"
2. [`hopit`](https://joss.theoj.org/papers/10.21105/joss.01508) is "an
   R package for analysis of reporting behavior using generalized ordered probit
   models". The input data are assumed to be ordered categorical variables
   typical of survey responses, and the package translates these into estimates
   of the equivalent continuous latent variables.
3. [`DscoreApp`](https://joss.theoj.org/papers/10.21105/joss.01764) is, "an
   user-friendly web application for computing the Implicit Association Test
   D-score," where the stated score is a metric of association between
   categories elucidated in surveys or questionnaires.
4. [`thurstonianIRT`](https://joss.theoj.org/papers/10.21105/joss.01662)
   derives a score used to assess forced-choice questionnaires (in which
   answers must, for example, be either A or B).
5. [`qsort`](https://joss.theoj.org/papers/10.21105/joss.00911) provides "a new
   tool for scoring Q-sort Data", where these data are derived by asking survey
   respondents to sort categories in some specified order. The input data in
   this case are thus the sorting orders, rather than the categories
   themselves.

There is also software which takes quantitative input data and outputs discrete
categorisations, as exemplified by the
[`multistateutils`](https://joss.theoj.org/papers/10.21105/joss.00893) package,
which is a biostatistical package useful for distinguishing and categorising
dynamic trajectories (such as disease or treatment pathways).

We propose to exclude this as an explicit category, reflecting an assumption
that software within this category will generally able to be assessed under
other categories listed here.



### Networks

Network software is a particular area of application of what might often be
considered more generic algorithms, as in the example described above of the
[`grapherator`](https://github.com/jakobbossek/grapherator) package, for which
this category is appropriate only because the input data are assumed to
represent a particular form of graphical relationship, while most of the
algorithms implemented in the package are not necessarily specific to graphs.
That package might nevertheless be useful in developing standards because it,
"implements a modular approach to benchmark graph generation focusing on
undirected, weighted graphs". This package, and indeed several others developed
by its author [Jakob Bossek](http://www.jakobbossek.de/blog/), may be useful in
developing benchmarks for comparison of graph or network models and algorithms.

Cases of software which might be assessed using such generic graph generators
and benchmarks include:

1. [`mcMST`](https://joss.theoj.org/papers/10.21105/joss.00374), which is "a
   toolbox for the multi-criteria minimum spanning tree problem."
2. [`gwdegree`](https://joss.theoj.org/papers/10.21105/joss.00036), which is
   a package for, "improving interpretation of geometrically-weighted degree
   estimates in exponential random graph models." This package essentially
   generates one key graph statistic from a particular class of input graphs,
   yet is clearly amenable to benchmarking, as well as measures of stability in
   response to variable input structures.

Network software which is likely more difficult to assess or compare in any
general way includes:

1. [`tcherry`](https://joss.theoj.org/papers/10.21105/joss.01480) is a package
   for "Learning the structure of tcherry trees," which themselves are
   particular ways of representing relationships between categorical data. The
   package uses maximum likelihood techniques to find the best tcherry tree to
   represent a given input data set. Although very clearly a form of network
   software, this package might be considered better described by other
   categories, and accordingly not directly assessed or assessable under any
   standards derived for this category.
2. [`BNLearn`](https://www.bnlearn.com/) is a package "for learning the
   graphical structure of Bayesian networks." It is indubitably a network
   package, yet the domain of application likely renders it incomparable to
   other network software, and difficult to assess in any standardised way.



### Statistical Reporting and Exploratory Data Analysis

Many packages aim to simplify and facilitate the reporting of complex
statistical results or exploratory summaries of data. Such reporting commonly involves visualisation, and there
is direct overlap between this and the Visualisation category (below). This roughly breaks out into software
that summarizes and presents _raw_ data, and software that reports complex data derived from statistical routines.
However, this break is often not clean, as raw data exploration may involve an algorithmic or modeling step
(e.g., projection pursuit.). Examples include:

1.  A package rejected by rOpenSci as out-of-scope,
[`gtsummary`](https://github.com/ddsjoberg/gtsummary), which provides, "Presentation-ready data summary and analytic
result tables." Other examples include:
1. The
   [`smartEDA` package](https://github.com/daya6489/SmartEDA) (with accompanying
   [JOSS paper](https://joss.theoj.org/papers/10.21105/joss.01509)) "for automated exploratory data analysis". The package,
   "automatically selects the variables and performs the related descriptive
   statistics. Moreover, it also analyzes the information value, the weight of
   evidence, custom tables, summary statistics, and performs graphical
   techniques for both numeric and categorical variables." This package is
   potentially as much a workflow package as it is a statistical reporting
   package, and illustrates the ambiguity between these two categories.
2. The
   [`modeLLtest` package](https://github.com/ShanaScogin/modeLLtest) (with accompanying
   [JOSS paper](https://joss.theoj.org/papers/10.21105/joss.01542)) is "An R Package for Unbiased Model Comparison using Cross
   Validation." Its main functionality allows different statistical models to
   be compared, likely implying that this represents a kind of meta package.
3. The
   [`insight` package](https://github.com/easystats/insight) (with accompanying
   [JOSS paper](https://joss.theoj.org/papers/10.21105/joss.01412) provides "a unified interface to access information from
   model objects in R," with a strong focus on unified and consistent reporting
   of statistical results.
4. The
   [`arviz` software for python](https://github.com/arviz-devs/arviz) (with accompanying
   [JOSS paper](https://joss.theoj.org/papers/10.21105/joss.01143) provides "a unified library for exploratory analysis of
   Bayesian models in Python."
5. The
   [`iRF` package](https://github.com/sumbose/iRF) (with accompanying
   [JOSS paper](https://joss.theoj.org/papers/10.21105/joss.01077) enables "extracting interactions from random forests", yet
   also focusses primarily on enabling interpretation of random forests through
   reporting on interaction terms.

In addition to potential overlap with the Visualisation category, potential
standards for Statistical Reporting and Meta-Software are likely to overlap to
some degree with the preceding standards for Workflow Software. Checklist items
unique to statistical reporting software might include the following:

- [ ] **Automation** Does the software automate aspects of statistical
  reporting, or of analysis at some sufficiently "meta"-level (such as variable
  or model selection), which previously (in a reference implementation)
  required manual intervention?
- [ ] **General Reporting:** Does the software report on, or otherwise provide
  insight into, statistics or important aspects of data or analytic processes
  which were previously not (directly) accessible using reference
  implementations?
- [ ] **Comparison:** Does the software provide or enable standardised
  comparison of inputs, processes, models, or outputs which could previously
  (in reference implementations) only be accessed or compared some comparably
  unstandardised form?
- [ ] **Interpretation:** Does the software facilitate interpretation of
  otherwise abstruse processes or statistical results?
- [ ] **Exploration:** Does the software enable or otherwise guide exploratory
  stages of a statistical workflow?

### Survival Analyses

Software for survival analyses obtains its own category here due to the
relatively large number of packages. Survival analysis is a unique category
only in that it concerns models to process, predict, or analyse time-to-event
data. In many other ways software for survival analyses crosses over with many
other categories (including the central ML and Bayes/Monte Carlo categories),
with aspects presumably covered by standards developed in those respective
categories. The
[`multistateutils`](https://joss.theoj.org/papers/10.21105/joss.00893) package,
for example, is a biostatistical package useful for distinguishing and
categorising dynamic trajectories (such as disease or treatment pathways).
Several routines within this package involve assigning these categories to
states, and estimating times spent in various states. Although these are
survival analyses in a strict sense, that software is likely more appropriate
considered under other categories.

Perhaps one thing much survival analysis software has in common is similarity
of output, at least conceptually, in trying to quantify or predict times to
some defined event of a dynamic processes. One package that may potentially be
useful in interpreting and comparing the outputs of different survival routines
is [`survxai`](https://joss.theoj.org/papers/10.21105/joss.00961), which offers
"structure-agnostic explanations of survival models," whether survival neural
networks, survival random forests, or any other approach.

1. [`ccostr`](https://joss.theoj.org/papers/10.21105/joss.01593) "for
   estimating mean costs with censored data"
2. [`survPen`](https://joss.theoj.org/papers/10.21105/joss.01434) "for hazard
   and excess hazard modelling with multidimensional penalized splines", where
   hazard is interpreted as time-to-event in comparison with some baseline
   scenario.
3. [`GammaGompertzCR`](https://joss.theoj.org/papers/10.21105/joss.00216) which
   fits "a Gamma-Gompertz survival model to capture-recapture data collected on
   free-ranging animal populations" (and was described under Bayesian and Monte
   Carlo software, above).

***Key Considerations*** Although survival analysis is a common purpose of
statistical software, general methodologies may be too diverse to permit
general comparison and standardisation. This category of software nevertheless
very generally overlaps strongly with other categories considered here,
suggesting that this entire category may be safely excluded from consideration,
with the presumption that primary functional of survival software will be
addressed by standards devised under the other categories considered here.

***Proposal*** This category be excluded from explicit consideration.


### Workflow Support

"Workflow" software may not implement particular methods or algorithms,
but rather support tasks around the statistical process.  In many cases, these
may be generic tasks that apply across methods. These include:

1. Classes (whether explicit or not) for representing or processing input and
   output data;
2. Generic interfaces to multiple statistical methods or algorithms;
3. Homogeneous reporting of the results of a variety of methods or algorithms;
   and
4. Methods to synthesise, visualise, or otherwise collectively report on
   analytic results.

Methods and Algorithms software may only provide a specific interface to
a specific method or algorithm, although it may also be more general and offer
several of the above "workflow" aspects, and so ambiguity may often arise
between these two categories. We note in particular that the "workflow" node in
the
[interactive network diagram](https://ropenscilabs.github.io/statistical-software/abstracts/network-terms)
mentioned above is very strongly connected to the "machine learning" node,
generally reflecting software which attempts to unify varied interfaces to
varied platforms for machine learning.

Among the numerous examples of software in this category are:

1. The
   [`mlr3` package](https://github.com/mlr-org/mlr3) (with accompanying
   [JOSS paper](https://joss.theoj.org/papers/10.21105/joss.01903)), which provides, "A modern object-oriented machine learning
   framework in R."
2. The
   [`fmcmc` package](https://github.com/USCbiostats/fmcmc)
   (with accompanying
   [JOSS paper](https://joss.theoj.org/papers/10.21105/joss.01427)), which provides a unified framework and workflow for
   Markov-Chain Monte Carlo analyses.
3. The
   [`bayestestR` package](https://github.com/easystats/bayestestR) (with accompanying
   [JOSS paper](https://joss.theoj.org/papers/10.21105/joss.01541))
   for "describing effects and their uncertainty, existence and significance
   within the Bayesian framework. While this packages includes its own
   algorithmic implementations, it is primarily intended to aid general
   Bayesian workflows through a unified interface.

Workflows are also commonly required and developed for specific areas of
application, as exemplified by the
[`tabular` package](https://github.com/nfrerebeau/tabula) (with accompanying
[JOSS article](https://joss.theoj.org/papers/10.21105/joss.01821) for "Analysis, Seriation, and visualisation of Archaeological
Count Data".

 ***Key Considerations:*** Workflow packages are popular and add considerable value
and efficiency for users.  One challenge in evaluating such packages is the
importance of API design and potential subjectivity of this.  For instance,
`mlr3` as well as `tidymodels` have similar uses of providing a common interface
to multiple predictive models and tools for automating processes across these
models.  Similar, multiple packages have different approaches for handling MCMC
data.  Each package makes different choices in design and has different priorities,
which may or may not agree with reviewers' opinions or applications.  Despite such
differences, it may be possible to evaluate such packages for *internal* cohesion,
and adherence to a sufficiently clearly stated design goal. Reviewers may be able
to evaluate whether the package provides a _more_ unified workflow or interface
than other packages - this would require a standard of relative improvement over
the field rather than baseline standards.

These packages also often contain numerical routines (cross-validation,
performance scoring, model comparison), that can be evaluated for correctness
or accuracy.  

### Summary Statistics

1. [`SmartEDA`](https://joss.theoj.org/papers/10.21105/joss.01509)
2. [`modelDown`](https://joss.theoj.org/papers/10.21105/joss.01444)
3. [`insight`](https://joss.theoj.org/papers/10.21105/joss.01412)
4. [`rsimsum`](https://joss.theoj.org/papers/10.21105/joss.00739)
5. [`MCMCvis`](https://joss.theoj.org/papers/10.21105/joss.00640)

### Spatial Analyses

### Education

A prominent class of statistical software is *educational* software designed to
teach statistics. Such software many include its own implementations of statistical
methods, and frequently include interactive components.  Many examples of educational statistical software are
listed on the
[CRAN Task View: Teaching Statistics](https://cran.r-project.org/web/views/TeachingStatistics.html). This page also clearly indicates the
likely strong overlap between education and visualisation software. With
specific regard to the educational components of software, the follow checklist
items may be relevant.
A prominent example is the [`LearnBayes` package](https://cran.r-project.org/web/packages/LearnBayes/index.html). 

 ***Key Considerations:*** Correctness of implementation of educational or tutorial
software is important. Evaluation of such software extends considerably beyond correctness,
with heavy emphasis on documentation, interactive interface, and pedagogical soundness
of the software.  These areas enter a very different class of standards.  It is
likely that educational software will very greatly _structurally_, as interaction
may be via graphical or web interfaces, text interaction or some other form.

The [Journal of Open Source Education](https://jose.theoj.org) accepts both educational
software and curricula, and has a peer review system (almost)
identical to [JOSS](https://joss.theoj.org). Educational statistical software
reviewed by rOpenSci could thus potentially be fast-tracked through JOSE
reviews just as current submissions have the opportunity to be fast-tracked
through the JOSS review process. 

- *Demand:* Does the software meet a clear demand otherwise absent from
  educational material? If so, how?
- *Audience:* What is the intended audience or user base? (For example,
  is the software intended for direct use by students of statistics, or does it
  provide a tool for educational professionals to use in their own practice?)
- *Algorithms:* What are the unique algorithmic processes implemented by
  the software? In what ways are they easier, simpler, faster, or otherwise
  better than reference implementations (where such exist)?
- *Interactivity:* Is the primary function of the software interactive?
  If so, is the interactivity primarily graphical (for example, web-based),
  text-based, or other?

## Proposals

1. Peer review in the system will primarily focus on code written in R, C, and
   C++. Standards will be written so as to separate language-specific and
   non-language-specific components with an eye towards further adoption by
   other groups in the future (in particular groups focussed on the Python
   language). 
2. The system will be limited to R packages, and tools developed will be
   specific to R package structure, although keeping in mind potential future
   adaptation and adaptability to non-packaged R code. Standards that may apply
   to non-packaged are code may also be noted for use in other contexts.
3. Submissions will be required to nominate at least one statistical category,
   to nominate at least one "reference implementation", and to explain how the
   submitted software is superior (along with a possibility to explain why
   software may be sufficiently unique that there is no reference
   implementation, and so no claims of superiority can be made).
4. We will only review packages where the primary statistical functionality is
   in the main source code developed by the authors, and not in an external
   package.  
5. The following 11 categories of statistical software be defined, and be
   considered in scope:
    - 1. Bayesian and Monte Carlo algorithms
    - 2. Dimensionality Reduction and Feature Selection
    - 3. Machine Learning
    - 4. Regression and Interpolation
    - 5. Probability Distributions
    - 6. Wrapper Packages
    - 7. Networks
    - 8. Exploratory Data Analysis
    - 9. Workflow Software
    - 10. Summary Statistics
    - 11. Spatial Statistics
6. The following categories be considered, at least initially, to be
   out-of-scope:
    - 1. Educational Software
    - 2. Visualisation Software


Beyond these general *Proposals*, the following lists *Proposals* specific to
particular categories of statistical software:

1. For packages which parameterise or fit probability distributions, develop
   routines to assess and quantify the sensitivity of outputs to the
   distributional properties of inputs, and particularly to deviations from
   assumed distributional properties.
2. We identify a sub-category of software which accepts *network inputs*, and
   develop (or adapt) general techniques to generate generic graphs to be used
   in benchmarking routines. Other software which falls within the category of
   *Network Software* only because of restricted aspects such as internal data
   representations (such as `tcherry`) *not* be considered or assessed within
   that category.

