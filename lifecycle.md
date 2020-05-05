
#  (PART) Software Review Process and Software Assessment {-}

# <span style="color:red;">Software Review and Life Cycle Models [Seeking Feedback]</span> {#lifeycle}

Prior to describing the review system we intend to develop, we briefly digress
to describe analogous review systems, aiming to emphasise aspects which may be
useful to adopt within our system. This chapter concludes with succinct
proposals of aspects of these prior systems which we intend to adopt within our
system, and for which we are explicitly seeking feedback. There are notable
differences between the systems described here, with contrasts between them
often providing convenient reference points in considering many of the
subsequent review phases we envision developing. The present chapter then
concludes with brief consideration of what a model of the life cycle of open
source software might look like. This is important in guiding the structure of
the proposed review process.

## Other systems for software and peer review

### rOpenSci

rOpenSci's current software peer-review process, detailed in our [developer
guide](https://devguide.ropensci.org/softwarereviewintro.html), is based on a
blend of practices from peer review of academic practices and code review in
open-source projects. Review takes place via an issue thread in our
["software-review" repository on
GitHub](https://github.com/ropensci/software-review). The review process is
entirely open, with each issue thread used to manage the entire process,
coordinated by rOpenSci's editors. After initial screening for scope and minimal
qualification by editors, two reviewers provide comments and feedback on software
packages. After one or more rounds of revisions, packages reach a point of
approval, at which point they are "accepted" by rOpenSci, symbolized both
through a badge system, and (generally) through transferring the software from
the authors' private domain to the
[github.com/ropensci](https://github.com/ropensci) domain.

### The Journal of Open Source Software

The [Journal of Open Source Software (JOSS)](https://joss.theoj.org/) was based
on rOpenSci and follows a similar approach, with greater automation and broader
scope. The Journal of Statistical Software conducts a closed review of both
manuscript and software, with fewer prescriptive standards. In reviewing
packages for acceptance into its repository,
[BioConductor](https://www.bioconductor.org) conducts an [open
review](https://www.bioconductor.org/developers/package-submission/) primarily
aimed at maintaining minimum standards and inter-compatibility.


### Academic Journal Reviews

One ubiquitous model for processes of peer review is that of "standard"
academic journals, for which we now highlight two relevant aspects.

#### Primary and Secondary Editors

Academic journals commonly have a board of (primary) editors, and a field of
(secondary) subject or specialist editors. The initial and terminal points of
review processes are commonly handled by the primary editors, who delegate
subject editors to both solicit appropriate reviewers, and to manage the review
process. Upon completion, the primary editor generally signifies ultimate
acceptance. 

Such a model would also likely be beneficial for the present project, in spite
of potential difficulties we may face in attracting sufficient numbers of
subject editors. Division of labour between primary and secondary editors would
offer distinct advantages, foremost among which would be an ability to appoint
a reasonably large number of "subject editors" (or equivalent), for whom such
an official designation would be able to be used to boost their own careers. As
a contrast, rOpenSci's editorial processes are handled by a single cohort of
eight editors, of whom four are staff members, while JOSS currently has [six
primary editors and 31 "topic"
editors](https://joss.theoj.org/about#editorial_board).

The preceding consideration of [categories](#scope) suggests we may end up with
around a dozen categories, and so potentially be able to offer around this
number (or more) of honorary subject editor positions, along with a concomitant
reduction in workload for each of these. Engaging such a range of subject
editors would also lessen the burden on primary editors, perhaps enabling the
system to be initially trialled with the two or three people primarily engaged
in its current developmental phase. The engagement of a wider range of subject
editors would also enlarge the network of people directly engaged with the
project, as well as extending its sphere of influence to encompass the
professional networks of all those involved.

#### Invited and Mentored Submissions

Many journals enable editors to personally invite selected authors to submit
manuscripts on some particular topic, often compiled within single "special
issues". While special issues may not be relevant here, the notion of invited
submissions may prove particularly useful in fostering integration between
software packages. One likely defining distinction between rOpenSci and RStudio
may be the ability of the latter organisation to strategically plan the
development of software that links pre-existing software into more coherent or
thematically-aligned "suites" of software (the
[`tidyverse`](https://tidyverse.org) likely being the prime example). In
contrast, rOpenSci's software profile is very largely dependent on the whims of
largely independent developers, and the software they autonomously elect to
submit. (rOpenSci staff may themselves also develop software, and so strive to
create more focussed suites of related packages, but this is then by definition
more an individual than community effort.) The ability to solicit software
within particular categories, or fulfilling particular functionality, may
greatly aid an ability for this project to develop a coherent and singularly
identifiable suite of packages for use in statistical analyses.

One potential ways by which submissions could be invited would be through all
regular meetings of the editors and board having a fixed discussion point on
potential categories in which submissions may be desired. Agreement on the
importance or usefulness of particular categories or themes may be relatively
rare, but having this as a fixed item would allow progressive contemplation
ultimately leading to sporadic consensus. Following meetings during which such
consensus emerges, a general call for themed submissions may be issued, and/or
specific potential package authors may be individually approached.

The solicitation of themed submissions may also involve editors, members of the
board, or other community members, offering their services as mentors or
advisors throughout processes of package development. Invited submissions would
then also serve as an opportunity for dissemination of the knowledge and
expertise built up and held by individuals prior to and throughout the life of
this project.

Extending on from that idea, it may be worthwhile examining a "mentorship"
system, whereby people who might feel they lack the skills necessary to develop
a package of suitable standards might apply via an alternative form of
pre-submission enquiry (in this case something more like a "pre-development
enquiry") as to whether anybody might be willing to mentor the development of
a particular package idea. Such a system would of course require individuals to
be willing to volunteer their services as mentors, but would have potentially
significant advantages in expanding the entire system well beyond the
boundaries of the limited few who have sufficient confidence in their abilities
to develop packages.


***Proposal***

1. We adopt a model of primary and secondary editors, through having the
   rOpenSci staff directly involved in the development of this project serve as
   primary editors, and we seek to find and nominate subject editors as soon as
   we have reached agreement on categories of statistical software.
2. Members of the board may also offer their services in either as primary or
   secondary editorial capacity.
3. Once the system has started, we implement a fixed discussion point of every
   meeting on potential themes for invited submissions, and sporadically issue
   open (and directed) invitations for submissions of category-specific
   software.
4. We offer a separate stream of "pre-development enquiry" as a kind of "ideas
   lab" to which people may submit and discuss ideas, with the system
   explicitly designed to connect ideas to potential mentors who may guide
   development towards full packages.

### The Debian System

The development of software for the open-source [Debian Operating
System](https://debian.org) is guided by Debian Developers and Debian
Maintainers. Expressed roughly, maintainers are individuals responsible for the
maintenance of particular pieces of software, while developers engage with
activities supporting the development of the operating system as a whole. The
submission and review process for Debian is almost entirely automated, based on
tools such as their own software checker,
[`lintian`](https://lintian.debian.org). Debian differs fundamentally from the
system proposed here in being centred around the trust and verification of
people rather than software. Submission of software to Debian is largely
automatic, and bug-free software may often progress automatically through
various stages towards acceptance. Software may, however, only be submitted by
official Debian Maintainers or Developers. People can only become developers or
maintainers through being sponsored by existing members, and are then subject
to review of the potential contribution they may be able to make to the broader
Debian community. (Details can be seen in [this chapter of the Debian
handbook](https://debian-handbook.info/browse/stable/sect.becoming-package-maintainer.html).)

While the general process for software submission and acceptance in Debian may
not be of direct relevance, their versioning policy may provide a useful mode.
The ongoing development of both the Debian system and all associated packages
proceeds in accordance with a versioned [policy
manual](https://www.debian.org/doc/debian-policy/index.html). All new packages
must comply to the current standards at the time of submission, and are
labelled with the latest version of the standards to which they comply, [noting
that](https://www.debian.org/doc/debian-policy/ch-source.html#standards-conformance),

> For a package to have an old Standards-Version value is not itself a bug ...
It just means that no-one has yet reviewed the package with changes to
the standards in mind.

Each new version of the standards is accompanied by a simple
[checklist](https://www.debian.org/doc/debian-policy/upgrading-checklist.html)
of differences, explicitly indicating differences with and divergences from
previous versions. As long as software continues to pass all tests, upgrading
to current standards remains optional. Failing tests in response to any
upgrading of standards serve as a trigger for review of software. The nominated
standards version may only be updated once review has confirmed compliance with
current standards. We propose to adapt some of these aspects of the Debian
system in the present project, as described below.

### Other Potential Models

The Linux [Core Infrastructure Initiative](https://www.coreinfrastructure.org/)
provides badges to projects meeting [development best
practices](https://github.com/coreinfrastructure/best-practices-badge/blob/master/doc/criteria.md).
Badges are graded (passing/silver/gold), and awarded by package authors
self-certifying that they have implemented items on a checklist. 


## Software Life Cycle Considerations

The importance of considering Software "life cycles" has long been recognized for
closed-source proprietary software, yet life cycles have only been given scant
consideration in contexts of open source software [exceptions include
@stokes_21_2012;@lenhardt_data_2014]. A long history and tradition in both
practice and published literature on software review [for example,
@mili_software_2015;@ammann_introduction_2017] generally concludes that
software review is most effective when it is an ongoing process that is
structurally embedded within a software life cycle, and when review occurs as
frequently as possible. Such practices contrast strongly with the singular
nature of review as currently implemented by rOpenSci.

An effective system for peer review of statistical software is thus may lie
somewhere between the current "one-off" practices of rOpenSci and the JOSS, and
frequent, ongoing review typical of software development in active teams. An
[analysis of the effects of rOpenSci's review process on a few metrics of
software development
activity](https://github.com/mpadge/statistical-software/tree/master/ros-review-effects)
revealed that software development tends to stagnate following review. This may
be interpreted to reflect software having reached a sufficiently stable state
requiring relatively little ongoing maintenance. However, we note that metrics
of community engagement with software are generally positively related to the
metrics of development activity considered there. Slowing of software
development following review may also accordingly reflect or result in
decreases in community engagement.

Potential systems to enhance review of the kind current practiced by rOpenSci,
and particularly to encourage and enable more ongoing review on smaller scales
and shorter time frames---and ultimately to encourage the ongoing and active
development of software following review---include pull-request reviews, and
systems for providing inline code reviews (such as
[watson-ruby](https://github.com/nhmood/watson-ruby)). In addition, ongoing
"review" may be explicit in considering the role of user feedback, for
instance, in defining and updating the scope of statistical routines (see
"Standards for Statistical Software" below).

