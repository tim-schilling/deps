===============================================
DEP 0010: New governance for the Django project
===============================================

:DEP: 0010
:Author: James Bennett
:Implementation Team: James Bennett, others to be determined
:Shepherd: Aymeric Augustin
:Status: Final
:Type: Process
:Created: 2018-09-22

.. contents:: Table of Contents
   :depth: 3
   :local:

.. note::

    This is a historical document, describing the changes from Django's BDFL
    structure to its Technical Board leadership, later updated by `DEP 12`_ to
    the Steering Council. See Django's documentation for `operational documentation
    of the Steering Council and how it works`_.

.. _DEP 12: https://github.com/django/deps/blob/main/final/0012-steering-council.rst
.. _operational documentation of the Steering Council and how it works: https://docs.djangoproject.com/en/dev/internals/organization/#steering-council

Abstract
========

This is a proposal to reform the organization of the Django
open-source project, by dissolving the current team of committers and
replacing it with a new governance model.

The following Q&A is informative, and describes the proposal in a
general way; for full details, please see the "Specification" section
below.


What roles will there be in the project after this change?
----------------------------------------------------------

?


How will code get added to Django?
----------------------------------

For smaller changes such as documentation, bugfixes and minor features,
Mergers will use their judgment to determine if there's consensus that the
change is good, and merge it if so. The Django Security
Team can authorize the merge of code to fix security issues.

For larger changes, the `new-features repo`_ should be used.


Who decides when Django gets released?
--------------------------------------

See `DEP 44`_.


Who decides the technical direction of Django?
----------------------------------------------

See `new-features repo`_.

Terminology
===========

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT",
"SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this
document are to be interpreted as described in `RFC 2119
<https://www.ietf.org/rfc/rfc2119.txt>`_.

For clarity, this DEP uses the following terms to refer to existing
groups:

* "Django Core": the set of people who have or have had permission to
  push to <https://github.com/django/django/> or the previous
  Subversion repository, or who have been members of the django-core
  mailing list, the #django-core IRC channel, or identified as members
  of "Django Core" on the djangoproject.com website.

* "DSF" and "DSF Board": the Django Software Foundation and its Board
  of Directors, respectively.

* "Django Fellows": a list of multiple people who have been or still
  are paid by the Django Software Foundation to perform various tasks,
  including triaging issues, reviewing and merging pull requests, and
  managing Django's releases.

* "Django Security Team": a group of people who respond to security
  issues handled under `Django's security process
  <https://www.djangoproject.com/security/>`_.

* "Django Forum": the discussion forum at `forum.djangoproject.com
  <https://forum.djangoproject.com/>`_.

The following terms are used in this document to refer to types of
changes made to Django's codebase:

* "Minor Change" means fixing a bug in, or adding a new feature to,
  Django of a scope small enough not to require the use of `the DEP
  process
  <https://github.com/django/deps/blob/main/final/0001-dep-process.rst>`_.

* "Major Change" means any change to Django's codebase of scope
  significant enough to require the use of the DEP process.

The following terms are used in this document to refer to types of
releases of Django:

* "Major Release Series" means the x.0 through x.2 releases of Django,
  for a given x. For example, Django 3.0, 3.1, and 3.2 collectively
  form a Major Release Series.

* "Feature Release" means an x.y.0 release of Django, where x.0 began
  a major release series and y is either 0, 1, or 2. For example,
  Django 3.1.0 is a Feature Release.

* "Bugfix Release" means an x.y.z release of Django, where x.y.0 was a
  Feature Release, and z is not 0. For example, Django 3.1.4 is a
  Bugfix Release. A Bugfix Release is "for" a particular Feature
  Release if, when considering the version number in the format x.y.z,
  x and y have the same values for the Bugfix Release as they do for
  the Feature Release. For example, Django 3.1.4 is a Bugfix Release
  for the Django 3.1.0 Feature Release.

* "Security Release" means a Bugfix Release which included a fix for a
  security issue in Django being handled under `Django's security
  process <https://www.djangoproject.com/security/>`_.

* A member "in good standing" of a venue for discussing the technical
  direction of Django is any member of that venue whose participation
  privileges have not been revoked, either by moderators of that
  venue, by the operator of the venue if operated by a third-party
  service or administrator, or by the Code of Conduct committee of the
  DSF.

Specification
=============

This section and its sub-sections are normative.

The current governance of the Django project will be replaced. To
accomplish this, the following steps will be taken:

1. Push access to <https://github.com/django/django/> SHALL be removed
   from all persons not designated as Mergers. Access to upload
   releases of Django to the Python Package Index and to
   djangoproject.com SHALL be removed from all persons not designated
   as Releasers.

2. The django-core mailing list and the #django-core IRC channel SHALL
   be closed, though archives accessible to the former members MAY be
   maintained.

3. The new roles described below SHALL be implemented appropriately.

4. The existing roles repurposed below SHALL be repurposed as
   described.

The following new roles are added:

* Merger

* Releaser

* Triage & Review Team

The following roles are repurposed:

* Django Core Developer

* Technical Board


Repurposed role: Technical Board
--------------------------------

The Technical Board provides oversight of Django's development and
release process, assists in setting the direction of feature
development and releases, selects Mergers and Releasers, and has a
tie-breaking vote when other decision-making processes fail.

The powers of the Technical Board are:

* To make a binding decision regarding any question of a technical
  change to Django.

* To manage the Steering Council's membership via an election with the
  DSF Board secretary.

* To create/update technical teams

The Technical Board SHALL consist initially of five members. To be
qualified for election to the Technical Board, see `DEP 12`_.


How Django is developed
-----------------------

Any person who signs the contributor CLA can write code for Django. Everyone is encouraged to open tickets, triage tickets and perform code reviews.

Commits can only be merged in by the Mergers team. A Merger can merge their own commits if it's been reviewed by another Merger, the Triage & Review Team or Security Team. Releasers can also merge commits when they are related to releases.

Changes that fail to reach "minor consensus" can be escalated to the Steering Council for a final decision to merge.

How Django is released
----------------------

Only members of the Releasers team may perform a release. 

Django follows the time-based release schedule, as outlined in `DEP 44`_.

The Security Team may request a Security Release of Django. This should be performed at or as close as is practicable to the time of release requested by the Security Team.


How Django's technical direction is determined
----------------------------------------------

Everyone is encouraged to propose and provide feedback on new features for Django at any time on the new-features repo.

For features which qualify as a Major Change, proposers may be asked to use the DEP process.

If discussion of a Minor Change has failed to produce consensus, a member may ask the
Steering Council to make a decision.

Vetoed discussions and features are eligible to be revisited after six months.

Decision making process of the Technical Board
----------------------------------------------

When asked to make a technical decision, the Technical Board should first discuss this
amongst themselves. If there's agreement on a course of action, a single member will
respond the forum, ticket, or new-features repo on behalf of the Technical Board. It
may optionally include a dissenting opinion if someone wishes to include one.

If the Technical Board can't arrive at an agreement, a formal vote may be invoked.

Voting process of the Technical Board
-------------------------------------

When a vote of the Technical Board is held, they SHALL use the
following process:

1. A proposal is proposed to the Steering Council in the form of a yes
   or no question. For example: "Shall the Django project accept and
   begin implementation of DEP 10?"

2. The possible outcomes of a vote are:

   * Accept: the "yes" option of the question is to be taken.

   * Veto: the "no" option of the question is taken, and the proposal
     is subject to the waiting period for reconsideration.

3. Members of the Steering Council will vote privately or respond with a timeline to vote within a week.

4. To be accepted, the proposal must have a majority of Steering Council members voting yes.

5. The outcome of the proposal will be published on the forum, ticket, or new-features repo. It should contain the reasoning for the decision, the concerns considered and optionally any dissenting opinions.

Votes of the Steering Council are binding, meaning all Django contributors must abide by the decision.


Process of selecting the Technical Board
----------------------------------------

The initial Technical Board shall be made up of the final technical
board elected under Django's prior governance process.

Whenever an election of the Technical Board is triggered, via any of
the mechanisms described in this document, the Technical Board will be limited in the following ways until the election is complete:

* The Technical Board must not accept any DEPs or changes to DEPs, and
  must not change the governance process described in this document.

Elections of the Technical Board are triggered by any of the following
events:

* One week after the actual release of
  the final Feature Release of a Major Release Series of Django, if no
  election of the Technical Board has yet occurred during that Major
  Release Series.

* When the current members contains less than three members who were
  elected in the most recent election of the Technical Board.

* At any other time, if the Technical Board votes to produce an Accept
  outcome on the question "Shall an election of the Technical Board
  occur?"

Only Individual members of the DSF are
eligible to vote in elections of the Technical Board.

The privilege to vote in elections of the Technical
Board may be revoked at any time by one of the following:

* The Code of Conduct committee of the DSF for a violation of the Django
Code of Conduct

* The Code of Conduc Committee has deemed someone ineligible to participate in the community spaces of the Django project

The roll of voters for elections of the Technical Board SHALL be
maintained by the DSF Board and will act as a neutral arbiter and
judge of Technical Board elections. Members of the DSF Board may stand
for election to the Technical Board if qualified, but any DSF Board
member who is a current member of the Technical Board or a candidate
in an upcoming election must abstain from taking part in the DSF
Board's oversight of that Technical Board election. The DSF Board may
delegate aspects of its oversight responsibilities (such as the
technical details of constructing registration and voting forms),
but only the DSF Board may ratify the results of a
Technical Board election.

The process of electing a Technical Board is as follows:

1. When an election is triggered, the Technical Board SHALL
   direct one of its members to notify the Secretary of the DSF, in
   writing, of the triggering of the election, and the condition which
   triggered it. The Secretary of the DSF then will post to the
   Django Forum and other appropriate venues to announce the election and its timeline.

2. As soon as the election is announced, the DSF Board shall begin a
   period of candidate registration. Any qualified person may register as a candidate; the
   candidate registration form and roster of candidates SHALL be
   maintained by the DSF Board, and candidates MUST provide evidence
   of their qualifications as part of registration. The DSF Board MAY
   challenge and reject the registration of candidates it believes do
   not meet the qualifications of members of the Technical Board, or
   who it believes are registering in bad faith.

3. Registration of candidates will close two weeks after it has
   opened. One week after registration of candidates closes, the
   Secretary of the DSF will publish the roster of candidates to the
   the Django Forum and any other appropriate venues, and the
   election will begin. The DSF Board will provide a voting form
   accessible to registered voters.

4. Voting will be by secret ballot. Each voter will be presented with
   a ballot containing the roster of candidates, and any relevant
   materials regarding the candidates, in a randomized order. Each
   voter may vote for up to five candidates on the ballot.

5. The election will conclude one week after it begins. The DSF Board
   will tally the votes and produce a summary, including the
   total number of votes cast and the number received by each
   candidate. This summary will be ratified by a majority vote of the
   DSF Board, then posted by the Secretary of the DSF to the
   the Django Forum and any other appropriate venues. The five
   candidates with the highest vote totals SHALL immediately become
   the new Technical Board.

Once elected, a member of the Technical Board MAY be removed in either
of two ways:

* They become ineligible due to actions of the Code of Conduct
  committee of the DSF. If this occurs, the affected person
  immediately ceases to be a member of the Technical Board. If that
  person's ineligibiliity ends at a later date, they may become a
  candidate for the Technical Board again in an election occurring
  after that date.

* It is determined that they did not possess the qualifications of a
  member of the Technical Board. This determination must be made
  jointly by the other members of the Technical Board, and the DSF
  Board. A valid determination of ineligibility requires that all
  other members of the Technical Board vote "+1" on the question
  "Shall this person be declared ineligible for the Technical Board?",
  and that all members of the DSF Board who can vote on the issue (the
  affected person, if a DSF Board member, MUST NOT vote) vote "yes" on
  a motion that the person in question is ineligible.

A member of the Technical Board MAY resign from the Technical Board by
notifying the other members of the Technical Board of their intent to
resign.

The Technical Board should try to fill a vacancy on the
Technical Board. To do so, the other members of the Technical Board
(and the departing member(s), if eligible and willing), SHALL use this
process:

* Any member of the Technical Board, including an otherwise eligible
  but departing member, may nominate a candidate to fill a vacancy.

* The Technical Board will notify the Secretary of the DSF, in writing, of the nomination. The DSF
  Board SHALL check the qualifications of the person nominated, and
  the Secretary of the DSF will notify the Technical Board of the
  result. If the DSF Board determines the nominated person is not
  qualified, the nomination must be discarded.

* Otherwise, the Technical Board then SHALL vote on the question:
  "Shall this candidate fill the vacancy on the Technical Board?" As
  an exception to the Technical Board voting process described above,
  this vote SHALL have only a single one-week voting period, SHALL
  have an outcome of "Accept" if all eligible voting members of the
  Technical Board vote "+1" in that period, and SHALL have an
  outcome of "Reject" otherwise.


Interaction of the Technical Board and the Django Security Team
---------------------------------------------------------------

The Django Security Team has the following powers:

* To request a Merger merge code to fix a security issue being handled
  under Django's security process.

* To request a Releaser issue a release of Django containing code to
  fix a security issue being handled under Django's security process.

In the event that the Technical Board feels the Django Security Team
has used the above powers inappropriately, the Technical Board MAY
appeal to the DSF Board to mediate the issue. Any member of the DSF
Board who is also a member of the Django Security Team or of the
Technical Board MUST abstain from participation in the DSF Board's
decision-making in such mediation. The decision of the DSF Board in
the dispute SHALL be binding on both the Technical Board and the
Django Security Team.


Interaction of the Technical Board and other teams
--------------------------------------------------

*See django/dsf-working-groups for other teams and working groups*

The Technical Board may oversee or have a liaison on various teams
and working groups in the Django community. The team or working group
may have powers delegated directly from the Steering Council. In all cases
the following interactions should occur:

* The Technical Board MAY make requests of those teams, and those
  teams SHOULD accommodate those requests when reasonable and
  practicable.

* Those teams MAY make requests of the Technical Board, and the
  Technical Board SHOULD accommodate those requests when reasonable
  and practicable, provided that accommodating the request falls
  within the powers of the Technical Board.

In the event of a dispute between the Technical Board and a team not
under the governance of the Technical Board, the DSF Board shall serve
as mediator. Any member of the DSF Board who is also a member of the
Technical Board or of the affected team MUST abstrain from the DSF
Board's decision-making in such mediation. The decision of the DSF
Board in the dispute SHALL be binding on both the Technical Board and
the affected team.


Changing this governance process
--------------------------------

Changes to this governance process shall be treated initially as Major
Changes to Django, and as such shall require the use of the DEP
process as described in DEP 1, with modifications as described below.

1. To reach the "accepted" state, a DEP proposing changes to this
   governance process must receive an outcome of "Accept" in a vote of
   the Technical Board with a score of at least 4, rather than the
   usual 3.

2. Once such a DEP reaches "accepted" status, the Technical Board will
   direct one of its members to notify the Secretary of the DSF, in
   writing, of the existence of an accepted DEP for changing the
   governance process.

3. The DSF Board SHALL hold a vote, at its earliest convenience, on a
   motion to adopt the proposed change. If the DSF Board rejects the
   motion, the governance process will not change, and the Secretary
   of the DSF will notify the Technical Board, in writing, of the DSF
   Board's objections to the proposal. The DEP then returns to draft
   status. The DEP may be revised and restart the DEP approval process.

4. If the DSF Board accepts the motion, the DSF Board and the
   Technical Board will then hold separate votes on the question of
   whether the proposed change is significant enough to require
   approval by the community at large. If both the DSF Board and the
   Technical Board determine that the proposal is not significant
   enough to require such approval, the proposal then will be adopted
   and the DEP will immediately begin implementation.

5. If the DSF Board and/or the Technical Board determine that the
   proposal is significant enough to require approval by the community
   at large, the DSF Board will immediately call a special
   election. The qualifications of voters for the special election
   will be the same as those for elections of the Technical Board,
   and all persons eligibble to vote for the Technical Board will
   automatically be eligible to vote in the special election. One week after that
   registration period closes, the special election will begin. Voting
   will be by secret ballot. Each voter will be presented with a
   ballot containing a link to the DEP, and links to any associated
   materials, and the question: "Shall the change to Django's
   governance, indicated above, be adopted?" Voters MAY vote "Yes",
   "No", or "Abstain" on the question. The election will conclude one
   week after it begins. The DSF Board will tally the votes and
   produce a summary, including the total number of votes cast and the
   number of votes for each option. If at least a plurality of votes
   cast are for "Yes", the proposal then will be adopted and the DEP
   will immediately begin implementation. If "Yes" does not achieve
   at least a plurality of votes cast, the proposal then will not be
   adopted and the DEP will return to to draft status. The DEP may be revised
   and restart the DEP approval process.


Motivation
==========

This section is informative.

Django has been a very successful open-source project, but faces
certain threats to its long-term viability. Among those is the
stagnation of the core development team; new members are added rarely,
most people who have been members no longer actively participate, and
development has for some time seemed to proceed on "autopilot", with
the Django Fellows and a far smaller subset of contributors doing most
of the work.

This is unsustainable.

Recruitment of new core developers is difficult for several reasons:

* There is no clear path, currently, for a contributor to start out
  and then progress to eventual commit access and "core" status.

* The existence of current "Django Core" has repeatedly been described
  as a discouragement, with potential contributors comparing
  themselves to what they perceive as the standard of "core" and
  feeling that they are not good enough.

Additionally, despite the worldwide reach of Django, members of "core"
have tended to be relatively homogeneous, and no census of
contributors to Django of any level produces results close to the
actual demographics of Django's users.

This indicates that the current governance -- ad-hoc on the public
mailing list, with a nebulous and often-inactive "core" and a purely
reactive technical board -- is not succeeding in attracting
contributors in regions and populations among whom use of Django is
rapidly growing.

The primary goal of this proposal are:

1. To reform Django's governance to be more community-driven and less
   reliant (either in theory or in practice) on the people
   historically considered "core",

2. While preserving recognition of the historical contributions of the
   people in "core",

3. And formalizing the parts of Django's current governance that *are*
   working (such as a small number of people actually committing code)
   while replacing those which are not (such as the special status of
   "core" members in governance, and the purely reactive nature of the
   technical board).

It is accepted that this is only the *first* step in a process of
encouraging and growing the number and diversity of contributors to
Django, and that further steps will need to be taken. But although it
is not *sufficient* to solve all of the above problems, this proposal,
or something similar to it, is *necessary* to begin the process of
solving these problems.


Rationale
=========

This section is informative.

Dissolving or reorganizing Django core is a recurring issue within
Django core, the broader community of Django developers, and the
DSF. In particular, there seems to be a consensus to remove the
perceived bump in governance status associated with membership in
Django core, especially as many people who could claim this membership
are no longer active in contributing to or shepherding the development
of Django. This DEP attempts to act on that consensus by providing a
concrete proposal.


Backwards Compatibility
=======================

N/A


Reference Implementation
========================

N/A


Copyright
=========

This document has been placed in the public domain per the Creative Commons
CC0 1.0 Universal license (http://creativecommons.org/publicdomain/zero/1.0/deed).

(All DEPs must include this exact copyright statement.)

.. _DEP 44: https://github.com/django/deps/blob/main/accepted/0044-clarify-release-process.rst
