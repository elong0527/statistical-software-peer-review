


#  Some Light Reading: An Annotated Bibliography {#reading}

Below is an annotated bibliography of sources that have been useful in developing
this document and the statistical software peer-review standards.  Note this page
is auto-generated from a Zotero collection.  See
[Contributing to the Bibliography](#contributing-to-the-biblopgraphy) below
to add more sources.

## Books

There is an enormous wealth of books published on software review, software
assessment (often referred to via concepts of "validation" and/or
"verification"), and related concepts. Most importantly in the present context,
almost all such books address closed-source, proprietary software, with no
published books specifically dedicated to review or assessment of open-source
software.

---



*Software testing automation tips: 50 things automation engineers should know.*
 [Alpaev, Gennadiy  ( 2017 ).  ](http://www.books24x7.com/marc.asp?bookid=135445) 
A neat list of just what the title suggests, grouped into general topics of Scripting, Testing, Environment, Running Logging Verifying, and Reviewing.


---


*Introduction to software testing.*
 [Ammann, Paul; and Offutt, Jeff  ( 2017 ).  ]() 
Has useful definitions of *Verification* as "The process of determining whether the
products of a phase of the software development process fulfill the requirements established during the previous phase;" and  *Validation* as "The process of evaluating software at theend of software development to ensure compliance with intended usage."


 


Also includes extensive consideration of testing, in particular chapters on "Model-driven test design" (2), and "Writing Test Plans" (11).


 


---


*Software Verification and Validation: An Engineering and Scientific Approach.*
 [Fisher, Marcus S.  ( 2007 ).  ](https://www.springer.com/gp/book/9780387327259) 
Really useful considerations of risk as likelihood times consequence, with extensive worked examples of how these factors might be scaled (with most examples on simple four-point scales which prove to be sufficient to yield fruitful insight).


 


---


*Transparent Statistics Guidelines.*
 [Group (http://transparentstatistics.org/), Transparent Statistics in HCI Working  (  ).  ](https://transparentstats.github.io/guidelines/index.html) 
Currently only just begun, but aims to work towards what might be a very useful guide on how statistics might best be reported.


---


*Software Quality Approaches: Testing, Verification, and Validation: Software Best Practice 1.*
 [Haug, Michael; Olsen, Eric W; and Consolini, Luisa  ( 2001 ).  ](https://doi.org/10.1007/978-3-642-56612-7) 
A huge EU project, drawn from results of a host of "Process Improvement Experiments" (PIEs), all of which were controlled experiments built on a generic model, and involved manipulating some standard baseline practice and analysing effects.


 


---


*Software testing: concepts and operations.*
 [Mili, Ali  ( 2015 ).  ]() 
Describes some problems facing modern software development (p9), including "Absence of Reuse Practice", and lack of standard software architecture. Neither of these are applicable to R packages. Then goes on to describe (p11) "The Absence of Automation", and "Limited Quality Control", both of which are definitely still applicable.


---


*The art of software testing.*
 [Myers, Glenford J; Badgett, Tom; and Sandler, Corey  ( 2012 ).  ]() 
Glenford Myers originally published "The Art of Software Testing" in 1979. Most of the book is either pretty straightforward, or overly specific to be able to be directly transferred or translated to open source software.


 


---


*Conventions for R Modeling Packages.*
 [tidyverse  (  ).  ](https://tidymodels.github.io/model-implementation-principles/) 
"The goal of this document is to define a specification for creating functions and packages for 
new modeling packages
. These are opinionated specifications but are meant to reflect reasonable positions for standards based on prior experience. A number of these guidelines are specific to the tidyverse (e.g. “Function names should use snake_case instead of camelCase.”). However, the majority are driven by common sense and good design principles (e.g. “All functions must be reproducible from run-to-run.”)."


---


*Medical device software verification, validation and compliance.*
 [Vogel, David A  ( 2011 ).  ](http://site.ebrary.com/id/10436227) 
In spite of the applied focus, a highly relevant and insightful book. Of particular relevance are the extensive considerations of software lifecycles, verification and validation and associated metrics, and considerations of software testing in relation to the US FDA's General Principles of Software Validation.0


---


*The tidyverse style guide.*
 [Wickham, Hadley  (  ).  ](https://style.tidyverse.org/) 
"All style guides are fundamentally opinionated. Some decisions genuinely do make code easier to use (especially matching indenting to programming structure), but many decisions are arbitrary. The most important thing about a style guide is that it provides consistency, making code easier to write because you need to make fewer decisions."


---


## Journal Articles

---



*Reconciling modern machine learning practice and the bias-variance trade-off.*
 [Belkin, Mikhail; Hsu, Daniel; Ma, Siyuan; and Mandal, Soumik  ( 2019-09-10 ).  arXiv:1812.11118 [cs, stat]](http://arxiv.org/abs/1812.11118) 
A very good reference for the ubiquity of over-fitting in machine learning algorithms, which is nevertheless mostly dedicated to demonstrating a very practical approach to overcoming over-fitting.


---


*Datasheets for Datasets.*
 [Gebru, Timnit; Morgenstern, Jamie; Vecchione, Briana; Vaughan, Jennifer Wortman; Wallach, Hanna; Daumeé III, Hal; and Crawford, Kate  ( 2019-04-14 ).  arXiv:1803.09010 [cs]](http://arxiv.org/abs/1803.09010) 
Comment: Working Paper, comments are encouraged


---


*Four simple recommendations to encourage best practices in research software.*
 [Jiménez, Rafael C.; Kuzak, Mateusz; Alhamdoosh, Monther; Barker, Michelle; Batut, Bérénice; Borg, Mikael; Capella-Gutierrez, Salvador; Chue Hong, Neil; Cook, Martin; Corpas, Manuel; Flannery, Madison; Garcia, Leyla; Gelpí, Josep Ll.; Gladman, Simon; Goble, Carole; González Ferreiro, Montserrat; Gonzalez-Beltran, Alejandra; Griffin, Philippa C.; Grüning, Björn; Hagberg, Jonas; Holub, Petr; Hooft, Rob; Ison, Jon; Katz, Daniel S.; Leskošek, Brane; López Gómez, Federico; Oliveira, Luis J.; Mellor, David; Mosbergen, Rowland; Mulder, Nicola; Perez-Riverol, Yasset; Pergl, Robert; Pichler, Horst; Pope, Bernard; Sanz, Ferran; Schneider, Maria V.; Stodden, Victoria; Suchecki, Radosław; Svobodová Vařeková, Radka; Talvik, Harry-Anton; Todorov, Ilian; Treloar, Andrew; Tyagi, Sonika; van Gompel, Maarten; Vaughan, Daniel; Via, Allegra; Wang, Xiaochuan; Watson-Haigh, Nathan S.; and Crouch, Steve  ( 2017-6-13 ).  F1000Research: 876](https://f1000research.com/articles/6-876/v1) 
The four recommendations are:


1. Make source code publicly accessible from day one


2. Make software easy to discover by providing software metadata via a popular community registry


3. Adopt a licence and comply with the licence of third-party dependencies


4. Define clear and transparent contribution, governance, and communication processes


---


*Towards FAIR principles for&nbsp;research&nbsp;software.*
 [Lamprecht, Anna-Lena; Garcia, Leyla; Kuzak, Mateusz; Martinez, Carlos; Arcila, Ricardo; Martin Del Pico, Eva; Dominguez Del Angel, Victoria; van de Sandt, Stephanie; Ison, Jon; Martinez, Paula Andrea; McQuilton, Peter; Valencia, Alfonso; Harrow, Jennifer; Psomopoulos, Fotis; Gelpi, Josep Ll; Chue Hong, Neil; Goble, Carole; and Capella-Gutierrez, Salvador  ( 2019/01/01 ).  Data Science (Preprint): 1-23](https://content.iospress.com/articles/data-science/ds190026) 
An important reference for adapting FAIR (Findability, Accessibility, Interoperability, and Reusability) principles to software. All of these principles are effectively already met by rOpenSci's current review system, noting in particular that the majority of them pertain to the creation, existence, and curation of metadata.


---


*Data Management Lifecycle and Software Lifecycle Management in the Context of Conducting Science.*
 [Lenhardt, W.; Ahalt, Stanley; Blanton, Brian; Christopherson, Laura; and Idaszak, Ray  ( 2014-07-09 ).  Journal of Open Research Software (1): e15](http://openresearchsoftware.metajnl.com/articles/10.5334/jors.ax/) 
A relatively brief exploration of parallels between relatively well-established notions of lifecycle in regard to data management and curation, and less-established considerations of lifecycle in regard to software. Primarily an argument curation of appropriate metadata, it makes frequent reference to a variety of ISO standards.


---


## Technical Reports

---



*Software Evaluation Guide | Software Sustainability Institute.*
 [Jackson, Mike; Crouch, Steve; and Baxter, Rob  ( 2011 ).  ](https://www.software.ac.uk/resources/guides-everything/software-evaluation-guide) 
Divides considerations into the following categories and sub-categories:


 


1. Usability


    - 1.1 Understandability


    - 1.2 Documentation


    - 1.3 Learnability


    - 1.4 Buildability


    - 1.5 Installability


    - 1.6 Performance


2. Sustainability &amp; Maintainability


    - 2.1 Identity


    - 2.2 Copyright &amp; Licensing


    - 2.3 Accessibility


    - 2.4 Community


    - 2.5 Testability


    - 2.6 Portability


    - 2.7 Supportability


    - 2.8 Analysability


    - 2.9 Changeability


    - 2.10 Reusability


    - 2.11 Security &amp; Privacy


    - 2.12 Interoperability


    - 2.13 Governance


 


The main document divides each of these into numerous explicit categories, with the resultant document serving as likely a useful comparison or contrast to the Core Infrastructure Best Practices checklist.


---


*Automated Source Code CISQ Maintainability Measure Specification Version 1.0.*
 [Objcect Management Group  ( 2016 ).  ](https://www.omg.org/spec/ASCMM/) 
Considers a number of very specific metrics, including the following:


1. Control Flow Transfer Control Element outside Switch Block


2. Class Element ExcessiveInheritance of Class Elements with Concrete Implementation


3. Storable and Member DataElement Initialization with Hard-Coded Literals


4. Callable and Method ControlElement Number of Outward Calls


5. Loop Value Update within the Loop


6. Commented-out Code Element Excessive Volume (with default threshold of 2%)


7. Inter-Module Dependency Cycles


8. Source Element Excessive Size (with default of 1,000 lines per file)


9. Horizontal Layer Excessive Number (with default of 8)


10. Named Callable and Method Control Element Multi-Layer Span ("Avoid unclear allocation of software elements to a single architectural layer")


11. Callable and Method Control Element Excessive Cyclomatic Complexity Value (with default threshold of 20).


12. Named Callable and Method Control Element with Layer-Skipping Call (Aim: Avoid calls from an upper layer to lower layers that are not adjacent).


13. Callable and Method Control Element Excessive Number of Parameters (with default threshold of 7)


14. Callable and Method Control Element Excessive Number of Control Elements Involving Data Element from Data Manager or File Resource (Aim: Reduce numbers of external data dependencies, with default threshold of 7).


15. Public Member Element


16. Method Control Element Usage of Member Element from other Class Element


17. Class Element Excessive Inheritance Level (with default threshold of 7)


18. Class Element Excessive Number of Children (with default threshold of 10)


19. Named Callable and Method Control Element Excessive Similarity (based on assessment of numbers of identical compiled tokens within a unit)


20. Unreachable Named Callable or Method Control Element (Aim: Avoid inactive code blocks)


---


*ESIP Software Guidelines Draft.*
 [Scott, Soren  ( 2016 ).  ](https://esipfed.github.io/Software-Assessment-Guidelines/guidelines.html) 
Earth Science Information Partners (ESIP) guidelines, divided among the primary categories of


1. Sustainable Code


    1.1 Clean, standardized code


    1.2 Versioned code


    1.3 Redistributable


    1.4 Tested


2. Interoperable


3. Usable


    3.1 Clear, understandable interface


    3.2 Performant and stable


4. Documented


    4.1 Source code is documented


    4.2 Codebase includes documentation to support adaptation and reuse


    4.3 Software is documented


    4.4 Code or software requirements are documented


    4.5 Project is documented


5. Secure


6. Shareable


7. Governed


    7.1 Contribution policies are provided


    7.2 Development activities are transparent


8. Progression, sustainability, and reusability/adoption


---


*CLARIAH/software-quality-guidelines.*
 [van Gompel, Maarten; Noordzij, Jauco; de Valk, Reinier; and Scharnhorst, Andrea  ( 2016 ).  ](https://github.com/CLARIAH/software-quality-guidelines) 
Divides considerations into the categories and sub-categories derived by the [Software Sustainability Institute](
https://www.software.ac.uk/resources/guides-everything/software-evaluation-guide)
 in 2011.


Each of these has several explicit sub-components, with each of them scored on a 5-point scale. The entire document provides an outstandingly strong and usable reference or benchmark from which a set of standards for software quality might be adapted.


---


## Computer Programs

---



*lifecycle: Manage the Life Cycle of your Package Functions.*
 [Henry, Lionel; and RStudio,   ( 2020-03-06 ).  ](https://CRAN.R-project.org/package=lifecycle) 
A good potential candidate for recommended ways to manage software lifecycles


---


*RWsearch: Lazy Search in R Packages, Task Views, CRAN, the Web. All-in-One Download.*
 [Kiener, Patrice  ( 2020-02-15 ).  ](https://CRAN.R-project.org/package=RWsearch) 
May be useful for it's ability to download and search package documentation.


---


*microsoft/nni.*
 [Microsoft  ( 2020-03-16T12:25:52Z ).  ](https://github.com/microsoft/nni) 
Potentially useful as a benchmarking tool for ML implementations based on Neural Networks (see also `uber/ludwig`)


---


*The Turing Way: A Handbook for Reproducible Data Science.*
 [The Turing Way Community, ; Becky Arnold, ; Louise Bowler, ; Sarah Gibson, ; Patricia Herterich, ; Rosie Higman, ; Anna Krystalli, ; Alexander Morley, ; Martin O'Reilly, ; and Kirstie Whitaker,   ( 2019-03-25 ).  ](https://zenodo.org/record/3233986) 
A useful reference for various aspects of reproducible science


---


*uber/ludwig.*
 [uber  ( 2020-03-16T10:25:42Z ).  ](https://github.com/uber/ludwig) 
Potentially useful as a benchmarking tool for ML implementations (see also `microsoft/nni`)


---


### Computer Programs (Testing)

Software specifically designed for testing.

---



*mikldk/roxytest.*
 [Andersen, Mikkel Meyer  ( 2020-03-04T21:43:17Z ).  ](https://github.com/mikldk/roxytest) 
Very useful extension of R testing through enabling tests to be specified *in-line* via `roxygen` entries, either through explicit specification (via `@test` hooks), or through converting examples to tests (via `@testexamples` hooks).


---


*markvanderloo/tinytest.*
 [Loo, Mark van der  ( 2020-03-04T15:20:41Z ).  ](https://github.com/markvanderloo/tinytest) 
Implements the unique (in R) and useful approach of treating test results as data amenable to analysis, rather than just throwing interrupt signals.


---


*Most testing is ineffective - Hypothesis.*
 [MacIver, David  (  ).  ](https://hypothesis.works/) 
"Hypothesis is a family of testing libraries which let you write tests parametrized by a source of examples. A Hypothesis implementation then generates simple and comprehensible examples that make your tests fail. This simplifies writing your tests and makes them more powerful at the same time, by letting software automate the boring bits and do them to a higher standard than a human would, freeing you to focus on the higher level test logic."


---


*LudvigOlsen/xpectr.*
 [Olsen, Ludvig Renbo  ( 2020-03-02T09:31:14Z ).  ](https://github.com/LudvigOlsen/xpectr) 
R package for generating expectations for 
testthat
 unit testing. The main utility is via functions which *automatically* generate tests appropriate to the input structure of functions.


---


*r-lib/waldo.*
 [Wickham, Hadley  ( 2020-03-30T13:36:53Z ).  ](https://github.com/r-lib/waldo) 
Uses `diffobj` to create and return inline diffs between objects. Likely to be particularly useful in tests.


---


## Web Pages

---



*Jakob Bossek - PhD candidate.*
 [Bossek, Jakob  (  ).  ](http://www.jakobbossek.de/software/) 
List of software packages developed by Jakob Bossek, most of which are devoted to providing benchmarking abilities for comparison of graphs and graph algorithms.


---


*coreinfrastructure/best-practices-badge.*
 [Core Infrastructure  (  ).  ](https://github.com/coreinfrastructure/best-practices-badge) 
A definitive reference for general standards in open-source software, as detailed in the [`doc/criteria.md` document](https://github.com/coreinfrastructure/best-practices-badge/blob/master/doc/criteria.md). That said, it is a github-based document, and many of the standards directly describe github-based attributes and workflows.


 


Sections considered are:

- Basic
- Website
  - License
  - Documentation
  - Other
- Must use https
  - Must provide for discussion
  - Must be in English
  - Change Control
- Public version control repo
  - Unique version numbering
  - Semantic versioning
  - Release notes
  - Reporting
- Bug reporting
  - Vulnerability reporting
  - Quality
- Working build system
  - Automated test suite (cover most branches, input fields, and functionality)
  - Continuous integration
  - New functionality testing
  - Warning flags / linter
  - Security
  - Analysis
- Static code analysis (with links to lots of language-specific tools)
  - Dynamic code analysis (with links to lots of language-specific tools)
  - Use of memory check tools, or memory-safe languages


---


*testing statistical software.*
 [Hayes, Alex  (  ).  ](https://www.alexpghayes.com/blog/testing-statistical-software/) 
Discusses four types of tests for statistical software:


- Correctness Tests


- Parameter Recovery Tests


- Convergence Tests


- Identification Tests (uniqueness/stability of solution)


---


*CODECHECK process.*
 [Nüst, Stephen Eglen & Daniel  (  ).  ](https://codecheck.org.uk//process/) 
A badging service indicating whether or not code used to support published scientific manuscripts is reproducible or not.


---


*A Risk-based Approach for Assessing R package Accuracy within a Validated Infrastructure.*
 [R Validation HUb  (  ).  ](/white-paper//) 
The White Paper from the R Validation Hub project for validation pharmaceutical software. "R Validation Hub is a cross-industry initiative whose mission is to enable the use of R by the Bio-Pharmaceutical Industry in a regulatory setting, where the output may be used in submissions to regulatory agencies." It describes the motivations and principles of their risk-based assessment of statistical software, much of which is directly implemented in the [`riskmetric` package](https://github.com/pharmaR/riskmetric).


---


*Pull Request review process - Reside-IC.*
 [Reside-IC  (  ).  ](https://reside-ic.github.io/articles/pull-requests/) 
A useful description of the pull request workflow developed by the Research Software for Infection Disease Epidemiology group at Imperial College, London.


---


*Shields.io: Quality metadata badges for open source projects.*
 [sheilds.io  (  ).  ](https://shields.io/) 
shields.io provides a badging service for many aspects of code, divided into the following general categories:


1. Build


2. Code coverage


3. Analysis


4. Chat


5. Dependencies


6. Size


7. Downloads


8. Funding


9. Issue Tracking


10. License


11. Rating


12. Social


13. Version


14. Platform &amp; Version Support


15. Monitoring


16. Activity


---


*PEP 8 -- Style Guide for Python Code.*
 [van Rossum, Guido; Warsaw, Barry; and Coghlan, Nick  (  ).  ](https://www.python.org/dev/peps/pep-0008/) 
The most widely used style guide for python code


---


## Contributing to the bibliography {#contributing-to-the-biblopgraphy}

This annotated bibliography is automatically generated from entries containing
"Note" fields in the [zotero library accompanying this
project](https://www.zotero.org/groups/2416765/statistical-software?). Please
feel free to add any additional entries you may see fit to this open library
according to the following steps:

1. Open your local [zotero client](https://zotero.org) and get a local copy of
   the [project
   library](https://www.zotero.org/groups/2416765/statistical-software?);
2. Enable zotero in your web browser so that you can click on any webpage to
   add an entry to the shared library;
3. Manually add a "Note" to any new entries and they'll automatically appear
   here the next time this page is updated.

This annotated bibliography extracts all text in all `Note` fields **up to the
first markdown section break**, itself defined by a single line with a least
three consecutive dashes as in the following example:


```markdown
Add some note text to appear in this annotated bibliography

---

This text below the three dashes and any subsequent lines will not appear here.
```

Notes which do not contain a section break will appear here in their entirety.

