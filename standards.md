
# Standards {#standards}

An important output of the present project is a set of standards which can
serve as expectations for software and as guides against which developers and
reviewers can assess software. Important general questions regarding standards
include the following:

-   What kind of standards might apply to software in general?

-   What kind of standards might specifically apply to statistical software?

-   How might such standards differ between different languages?

-   To what extent should we aim for "verification" or "validation" of
  software, and how might be signify such?

We acknowledge that standards of the kind anticipated here will likely be better
conceived of to reflect ongoing processes of development. As such, of equal
importance to developing a set of standards *per se* will be developing an
understanding of the kinds of *processes* which may have the most defining
effect on resultant standards at any point in time.

The remainder of this document employs a convenient distinction between:

-   "*General Standards*" which may be applied to all software considered within
    this project, irrespective of how it may be categorized under the times of
    categories of statistical software listed above; and

-   "*Specific Standards*" which apply to different degrees to statistical
    software depending on the software category.

It is likely that standards developed under the first category may subsequently
be deemed to be genuinely *Statistical Standards* yet which are applicable
across all categories, and it may also be likely that the development of
category-specific standards reveals aspects which are common across all
categories, and which may subsequently be deemed general standards. We
accordingly anticipate a degree of fluidity between these two broad categories.

There is also a necessary relationship between the Standards described here,
and processes of Assessment described below in [Chapter 8](#assessment). We
consider the latter to describe concrete *and generally quantitative* aspects
of *post hoc* software assessment, while the present Standards provides guides
and benchmarks against which to *prospectively* compare software during
development. As this entire document is intended to serve as the defining
reference for our Standards, that term may in turn be interpreted to reflect
this entire document, with the current section explicitly describing aspects of
Standards not covered elsewhere.

As described above, we anticipate the ongoing development of this current
document to employ a versioning system, with software reviewed and hosted under
the system mandated to flag the latest version of these standards to which it
complies.

## Other Standards

Among the noteworthy instances of software standards which might be adapted for
our purposes, and in addition to entries in our [*Annotated
Bibliography*](#reading), the following are particularly relevant:

1. The [Core Infrastructure Initiative's Best Practices
   Badge](https://bestpractices.coreinfrastructure.org/en), which is granted to
   software meeting an extensive list of
   [criteria](https://github.com/coreinfrastructure/best-practices-badge/blob/master/doc/criteria.md).
   This list of criteria provides a singularly useful reference for software
   standards.
2. The [Software Sustainability Institute](https://www.software.ac.uk/)'s
   [*Software Evaulation
   Guide*](https://www.software.ac.uk/resources/guides-everything/software-evaluation-guide),
   in particular their guide to [*Criteria-based software
   evaluation*](http://software.ac.uk/sites/default/files/SSI-SoftwareEvaluationCriteria.pdf),
   which considers two primary categories of *Usability* and *Sustainability
   and Maintainability*, each of which is divided into numerous sub-categories.
   The guide identifies numerous concrete criteria for each sub-category,
   explicitly detailed below in order to provide an example of the kind of
   standards that might be adapted and developed for application to the present
   project.
3. The more technical considerations of the [Object Management
   Group](https://www.omg.org/index.htm)'s [*Automated Source Code CISQ
   Maintainability Measure*](https://www.omg.org/spec/ASCMM/) (where CISQ
   refers to the [*Consortium for IT Software
   Quality*](https://www.it-cisq.org/)). This guide describes a number of
   measures which can be automatically extracted and used to quantify the
   maintainability of source code. None of these measures are not already
   considered in one or both of the preceding two documents, but the
   identification of measures particularly amenable to automated assessment
   provides a particularly useful reference.

There is also rOpenSci's guide on [package development, maintenance, and peer
review](https://devguide.ropensci.org/), which provides standards of this type
for R packages, primarily within its first chapter. Another notable example is
the [tidyverse design guide](https://principles.tidyverse.org/), and the
section on [Conventions for R Modeling
Pacakges](https://tidymodels.github.io/model-implementation-principles/) which
provides guidance for model-fitting APIs.

## Generally Applicable Standards 

The project aims to establish and maintain a set of standards governing general
aspects of software, such as software interfaces, documentation, and testing.
The following list represents a synthesis of the preceding sets of reference
standards which might be of use to this project, primarily derived from the
[Software Sustainability Institute](https://www.software.ac.uk/)'s guide to
[*Criteria-based software
evaluation*](http://software.ac.uk/sites/default/files/SSI-SoftwareEvaluationCriteria.pdf).

This list is provided as an example of the kinds of standards considered in
other domains, and developed in order to be generally applicable to software.
At the present initial stage of this project, we merely present the following
list as exemplary, and aim to use it to stimulate and guide discussion
regarding the potential utility of adapting, adopting, or otherwise developing
an equivalent, and/or equivalently detailed, list of standards.

Prior to detailing the exemplary standards adapted from those of the 
[Software Sustainability Institute](https://www.software.ac.uk/), we note that
both these standards, and influential sources such as @mili_software_2015,
consider software in terms of qualitative aspects such as *Usability*,
*Sustainability* and *Maintainability*, rather than in the kinds of concrete
standards otherwise commonly considered such as those describing
*Documentation*, *Testing*, *Code Structure*, other other aspects of software
design. The use of qualitative categories in defining and guiding standards is
preferred and adopted here particularly because it facilitates and encourages
consideration of those properties as they pertain to multiple aspects of
software design, and is likely to better facilitate the design and development
of more consistent and unified software.


- 1. Usability
  - 1.1 Understandability
    - High level description of what/who the software is for
    - High level description of what the software does
    - High level description of how the software works
    - Design rationale - why the software does things the way it does
    - Architectural overview with diagrams
    - Descriptions of intended use cases
    - Case studies of use
  - 1.2 Documentation
    - Provides a high level overview of the software
    - Partitioned into sections for users, user-developers, and developers
      (depending on the software)
    - Lists resources for further information
    - Is task-oriented
    - Consists of clear, step-by-step instructions
    - Gives examples of what the user can see at each step
    - For problems and error messages, the symptoms and step-by-step solutions
      are provided
    - Does not use terms like "intuitive", "user-friendly", "easy to use",
      "simple", or "obviously" (other than in quotes from satisfied users).
    - States command names, syntax, parameters, error messages exactly as they
      appear or should be typed.
    - Uses ${\tt teletype-style fonts}$ for command line inputs and outputs,
      source code fragments, function names, class names, etc.
    - English language descriptions of commands or errors are provided.
    - Plain text files (e.g. READMEs) use indentation and underlining to
      structure the text.
    - Plain text files do not use `TAB` characters to indent the text.
    - Documentation is complete (includes configuration requirements or properties).
    - Is held under version control alongside the code
    - Is on the project web site
    - Documentation on web site makes it clear what version of software the
      documentation applies to.
  - 1.3 Buildability
    - Straightforward to meet build pre-requisites
    - Straightforward to build the software
    - Web site has build instructions
    - Source distributions have build instructions
    - Web site lists all third-party dependencies that are not bundled
    - Source distribution lists all third-party dependencies that are not
      bundled
    - All mandatory third-party dependencies are currently available
    - All optional third-party dependencies are currently available
  - 1.4 Installability
    - Web site has installation instructions
    - Binary distributions have installation instructions
    - Web site lists all third-party dependencies that are not bundled
  - 1.5 Learnability
    - A getting started guide is provided with a basic example
    - Instructions are provided for many basic use cases
    - Reference guides are provided for all options
    - Documentation is provided for user-developers and developers
  - 1.5 Performance
- 2. Sustainability &amp; Maintainability
  - 2.1 Identity
    - Identity of project is clear and unique both within domain of application
      and generally.
    - Project/software has own domain name
    - Project/software has distinct name within application area (appears
      within first page of search results when entered with domain keywords).
    - Project/software has distinct name regardless of application area
    - Project/software does not throw up embarrassing "Did you mean ..."
      suggestions on search engines.
    - Project/software name does not violate a trademark
    - Project/software name is trademarked
  - 2.2 Copyright
    - Web site states copyright
    - Web sites states developers and funders
    - If multiple web sites, then all state exactly same copyright, license,
      authorship
    - Each source code file has copyright statement
    - If supported by language, each source file has copyright statement
      embedded within a constant - 
    - Each source code file has a license header
  - 2.3 Licencing
    - Appropriate licence
    - Web site states licence
    - Software has a licence
    - Software has an open source licence
    - Software has an Open Software Institute recognised licence
  - 2.4 Governance
    - Management is transparent
    - Project has a defined governance policy
    - Governance policy is publicly available
  - 2.5 Community
    - To what extent does an active user community exist?
    - Web site has statement of numbers of users/developers/members
    - Web site has quotes from satisfied users
    - Web site lists most important partners or collaborators
    - Web site has list of project publications
    - Web site lists third-party publications that use the software
    - Web site lists software that uses/bundles this software
    - Users are required to cite software if publishing results derived from
      its use
    - Users exists who are not members of the project
    - Developers exists who are not members of the project
  - 2.6 Accessibility
    - To what extent is software accessible?
    - Binary distributions are available
    - Binary distributions are available without need for registration or
      authorisation
    - Source distributions are available
    - Source distributions are available without need for registration or
      authorisation
    - Access to source code repository is available (whether for free, payment,
      registration)
    - Anonymous read-only access to source code repository
    - Ability to browse source code repository online
    - Repository hosted in sustainable third-party site which will live beyond
      lifetime of any current funding
    - Downloads page shows evidence of regular releases
  - 2.7 Testability
    - Straightforward to test software to verify modifications
    - Project has unit tests
    - Project has integration tests
    - Project has scripts for testing non-automated scenarios (e.g. GUIs)
    - Project recommends tools to check conformance to coding standards
    - Project has automated tests to check conformance to coding standards
    - Project recommends tools to check test coverage
    - Project has automated tests to check test coverage
    - A minimum test coverage level has been defined
    - There is an automated test for this minimum level
    - Tests are automatically run nightly
    - Continuous integration is supported
    - Test results are visible to all developers/members
    - Test results are visible publicly
    - Project specifies how to set up external resources (FTP servers,
      databases, etc.) for tests
    - Tests create their own files, database tables, etc.
  - 2.8 Portability
    - To what extent can software be used on other platforms? (Checkboxes for
      various platforms.)
  - 2.9 Supportability
    - To what extent will software be supported currently and in the future?
    - Web site has page describing how to get support
    - User doc has page describing how to get support
    - Software describes how to get support (in README)
    - Project has an e-mail address
    - Project e-mail address has domain name
    - E-mails are read by more than one person
    - E-mails are archived
    - E-mails archives are publicly readable
    - E-mail archives are searchable
    - Project has a ticketing system
    - Ticketing system is publicly available
    - Ticketing system is searchable
    - Web site has a site map or index
    - Web site has a search facility
    - Project resources are hosted externally in a sustainable third-part
      repository which will live beyond lifetime of current project
    - E-mail archives or ticketing system shows that queries are resounded to
      (not necessarily fixed) within a week.
    - If there is a blog, it is regularly used
    - E-mail lists of forums, if present, have regular posts
  - 2.10 Analysability
    - Source code is structured into modules or packages
    - Source code structure relates clearly to the architecture or design.
    - Source code repository is in a version control system
    - Structure of source code repository and how this maps to software's
      components is documented
    - Source releases are snapshots of the repository
    - Source code is commented
    - Source code comments are written in a document generation mark-up
      language
    - Source code is laid out and indented well
    - Source code uses sensible class, package, and variable names
    - There are no old or obsolete source code files that should be handled by
      version control
    - There is no commented out code
    - There are not TODOs in the code
    - Auto-generated source code is in separate directories from other source
      code
    - Regeneration of auto-generated source code is documented
    - Coding standards are recommended by the project
    - Coding standards are required to be observed
    - Project-specific coding standards are consistent with community standards
  - 2.11 Changeability
    - Project has a defined contributions policy
    - Contributions policy is publicly available
    - Contributors retain copyright/IP of their contributions
    - Users, developer members, and developers who are not members can contribute
    - Project has a defined and stable deprecation policy
    - Stability/deprecation policy is publicly available
    - Releases document deprecated components within release
    - Releases document removed or changed components within release
  - 2.12 Evolvability
    - Web site describes project roadmap, plans, or milestones
    - Web site describes how project is funded or sustained
    - Web site describes end date of current funding lines
  - 2.13 Interoperability
    - Uses open standards
    - Uses mature, ratified, non-draft standards
    - Provides tests demonstrating compliance with standards

In contrast to these qualitative aspects, @mili_software_2015 identifies the
following attributes of *Software Quality*:

- 1. Functional Attributes
    - 1.1 Correctness
    - 1.2 Robustness
- 2. Useability Attributes
    - 2.1 Ease of Use
    - 2.2 Ease of Learning
    - 2.3 Customizability
    - 2.4 Calibrability
    - 2.5 Interoperability
- 3. Structural Attributes
    - 3.1 Design Integrity
    - 3.2 Modularity (including "cohesion" and "coupling")
    - 3.3 Testability
    - 3.4 Adaptability

Other aspects derived from other forms of standards include:

- Must use https
- Must be in English
- Unique version numbering
- Semantic versioning
- Release notes
- Static code analysis (with links to lots of language-specific tools)
- Dynamic code analysis (with links to lots of language-specific tools)
- Use of memory check tools, or memory-safe languages
- Functions that are [type
  stable](https://cran.r-project.org/web/packages/vctrs/vignettes/stability.html)
  unless explicitly indicated and explained otherwise. (See also the section on
  type stability in the [tidyverse design
  guide](https://principles.tidyverse.org/out-type-stability.html).)


An additional area for consideration is the creation of tools for documentation
creation and evaluation based on metadata of statistical method inputs and
outputs and packaged data [@lenhardt_data_2014]. Relationships between data
and statistical software may be structured in a sufficiently systematic way to
permit systematic documentation.

<!---
https://github.com/tdwg/vocab/blob/master/sds/documentation-specification.md
--->

<!---
Each debian release must include a space-separated list of bug report
   numbers closed by that release.
--->

### Testing {#overview-testing}

Testing is a critical area for standards, as tests are a concrete manifestation
of standards and the means by which authors may demonstrate compliance. While
testing is considered best practice and test coverage often used as a measure of
test completeness, guidance on *what* to test is rare, especially in the context
of R packages. Thus, standards will need to provide guidance on the types and
methods of tests required for different statistical software categories. (The
"Turing Way" has a useful discussion of [different kinds of software
tests](https://the-turing-way.netlify.com/testing/testing.html).)

In addition, statistical software may benefit from means or modes of testing
beyond the common frameworks used in and for R packages (e.g. R RMD check,
testhtat). A variety of other frameworks and workflows from other languages and
contexts may be relevant. Almost all testing as currently implemented in R is
"concrete testing" (Mili 2015), and little consideration has been given in R to
"stochastic" or "property-based" testing, in which expectation values of inputs
and outputs are tested, rather than concrete instantiations of such (the
notably exception of the apparently abandoned [`fuzzr`
package](https://github.com/mdlincoln/fuzzr) notwithstanding). Other languages
have developed grammars for stochastic or property-based testing, notably
through the [hypothesis package for
python](https://github.com/HypothesisWorks/hypothesis). These grammars enable
specification of test assumptions as well as expected test outputs. Assumptions
in `hypothesis` are declared through simple `@given` statements that might, for
example, quantify an assumed probability distribution for input data, while
outputs are specified through equivalent `@expect` statements that might, for
example, specify expected *distributional properties* of an output rather than
just concrete values.

The following are likely key questions which we will need to address regarding
testing:

-   To what extent should testing focus on *functional* or *integration* rather
    than *unit* testing?

-   Is it sufficient to consider test execution as an integral part of
    `R CMD check` only? Or might there by a case for developing alternative test
    execution environments and approaches? For instance, should there be an
    alternate workflow for long-running tests, tests requiring large data, or
    tests intended to be executed for other purposes?

-   Is it worthwhile concretely defining one or more goals of testing? (Such as
    error detection, error frequencies, error tolerance, accuracy.)

-   What are the test data? And how easy is it to input alternative data to
    tests?

-   Is there scope for "stochastic" or "property-based" testing?

-   What test reporter should be used? Does the `testthat` package and similar
    suffice? Or might it be worth considering new test reporting systems?

-   What aspects of tests and test data (both actual and permissible) might be
    worthwhile documenting in some kind of metadata format?

Extant R package which address some of these issues include
[`tinytest`](https://github.com/markvanderloo/tinytest),
[`roxytest`](https://github.com/mikldk/roxytest), and
[`xpectr`](https://github.com/LudvigOlsen/xpectr).


### Documentation

Standards will include requirements for form and completeness of documentation.
As with interface, several sources already provide starting points for
reasonable documentation. Some documentation requirements will be specific to
the statistical context. For instance, it is likely we will have requirements
for referencing appropriate literature or references for theoretical support of
implementations. Another area of importance is correctness and clarity of
definitions of statistical quantities produced by the software, e.g., the
definition of null hypotheses or confidence intervals. Data included in
software -- that used in examples or tests -- will also have documentation
requirements. It is worth noting that the
[`roxygen`](https://roxygen2.r-lib.org/) system for documenting R packages is
readily extensible, as exemplified through the [`roxytest`
package](https://github.com/mikldk/roxytest) for specifying tests *in-line*.


## Standards Specific to Statistical Software

The applicability of any concrete set of standards is likely to differ between
different categories of statistical software. For example, metrics of numerical
accuracy will likely differ between categories primarily describing analytical
algorithms and those describing less tractable routines which produce less
directly reproducible results. Or consider metrics derived from tests, which
must be interpreted in *qualitatively* different ways for packages entirely
dependent on their own internal code versus packages largely dependent on the
results of calls to external data providers (along with additional differences
between, for example, locally-installed "external" providers versus online
sources of external data).

Different standards must thus be considered to be differentially applicable to
different categories of software, and thus the interplay between the scope of
statistical software considered above and throughout this project, and the
standards emerging from the project, will be of critical importance throughout
the project. Such considerations lead to the following kinds of questions which
will likely have to be addressed:

-   To what extent ought we aim for general standards at the expense of specific
    abilities to assess particular categories of statistical software?

-   To what extent ought we strive for automation of software assessment, given
    the inherent risk of overseeing qualitative differences between different
    categories?

-   How much effort should be expended both developing a categorization of
    statistical software, and understanding the potential effects of such a
    categorization?

The following exemplify a few categories of statistical standards which may be
considered, emphasising restrictions of applicability to alternative kinds of
software.

-   **Numerical standards such as precision or convergence.** These will be
    applicable only to some restricted subset of all potential categories of
    statistical software (likely including but not limited to analytic and, to
    some extent, predictive routines) Moreover, even these two categories alone
    will likely require differing standards for precision or convergence.

-   **Method validity** It may be necessary or useful to develop standards for
    the *validity* of a chosen method, independent of its implementation.
    Questions of validity are commonly related to domains of application, and
    therefore must relate directly to any system for categorising statistical
    software. A method may (have been demonstrated to) be valid for some
    particular domain of application, and a software routine may be developed to
    adapt that method to some previously untried domain. It may then be
    necessary to consider potential (in)validity of that software, along with
    potential validity in other domains, themselves potentially not explicitly
    considered by the software authors.

-   **Software scope** The preceding considerations extend directly to general
    concerns of *scope*, whether in terms of domains of applicability,
    properties of input or output data, authorial intentions, or other
    contextual factors. Scope in all of these senses obviously must directly
    affect and determine the kinds of standards which may or may not apply to
    software, just as defining scope in these senses is also effectively an
    exercise in categorization of the kind described above.

-   **Reference standards** For software which implements or relies on standard
    routines, it may be necessary to designate reference data or
    implementations against which to compare outcomes, or guidance in selecting
    such references. For instance, the National Institute of Standards and
    Technology of the U.S. provides [a collection of reference data
    sets](https://www.itl.nist.gov/div898/strd/) with certified computational
    results which statistical software should be able to reproduce.


The project may benefit from collaboration with the ongoing development of the
[*Transparent Statistics
Guidelines*](https://transparentstats.github.io/guidelines/), by the "HCI
(Human Computer Interaction) Working Group". While currently only in its
beginning phases, that document aims to provide concrete guidance on
"transparent statistical communication." If its development continues, it is
likely to provide useful guidelines on best practices for how statistical
software produces and reports results.

Specific standards for neural network algorithms have been developed as part of
a [google 2019 Summer Of Code project](http://www.inmodelia.com/gsoc2019.html),
resulting in a dedicated R package,
[`NNbenchmark`](https://akshajverma.com/NNbenchmarkWeb/index.html), and
accompanying results---their so-called
["notebooks"](https://akshajverma.com/NNbenchmarkWeb/notebooks.html)---of
applying their benchmarks to a suite of neural network packages.

We envision the present project proceeding from this initial stage by
developing parallel definitions for both categories of software (defining both
*in*-scope and *beyond*-scope), and specific standards. A simple way to
proceed may be to develop lists for both, along with a representation of
inter-connections between categories and standards.

### Demonstration of innovation, novelty, or advancement

The standards listed above largely refer to _minimum_ requirements for software,
but following common practice in academic publishing, one may also possibly require
that a piece of software is demonstrably superior to otherwise equivalent software in at least
one (or perhaps more?) specific way(s).  (In current rOpenSci standards, packages
are required to 
[demonstrate signicant improvement](https://devguide.ropensci.org/policies.html#overlap)
over similar packages). If such a "relative improvement" requirement is included
in the process, authors may be required to demonstrate how their software
exceeds existing or reference implementations of similar tools in some of the
following ways:

-  **Efficiency:** Is the software more efficient (faster, simpler, other
  interpretations of "efficient") than reference implementations?
-  **Reproducibility or Reliability:** Does the software reproduce
  sufficiently similar results more frequently than reference implementations
  (or otherwise satisfy similar interpretations of reproducibility)?
-  **Accuracy or Precision:** Is the software demonstrably more accurate or
  precise than reference implementations (such as ?
-  **Simplicity of Use:** Is the software simpler to use than reference
  implementations?
-  **Algorithmic Characteristics:** Does the algorithmic implementation
  offer characteristics (such as greater simplicity or sensitivity) superior to
  reference implementations? If so, which?
-  **Convergence:** Does the software provide faster or otherwise better
  convergence properties than reference implementations?
-  **Method Validity:** Does the software overcome demonstrable flaws in
  previous (reference) implementations? If so, how?
-  **Method Applicability:** Does the software enable a statistical method
  to be applied to a domain in which such application was not previously
  possible?
-  **Automation** Does the software automate aspects of statistical analyses
  which previously (in a reference implementation) required manual intervention?
-  **Input Data:** Does the software "open up" a method to input data
  previously unable to be treated by a particular algorithm or method?
-  **Output Data:** Does the software provide output in forms previously
  unavailable by reference implementations?
-  **Reference Standards:** Are there any reference standards, such as the
  US National Institute of Standards and Technology's
  [collection of reference data sets](https://www.itl.nist.gov/div898/strd)
  against which the software may be compared? If so, which?


## Proposals

1. We develop a concrete list of standards like those of the [Software
   Sustainability Institute](https://www.software.ac.uk/) given above.
2. We identify which items in the resultant list are amenable to automatic
   assessment, and implement procedures to automate such assessment as far as
   practicable.
3. Our standards will be versioned, and software will be aligned with the most
   recent version of these standards with which it complies.
4. We initially develop a minimal set of standards applicable to different
   categories of statistical software, and aim to develop such
   category-specific standards throughout the ongoing development of the
   project.

