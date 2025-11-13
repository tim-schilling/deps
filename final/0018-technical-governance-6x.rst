=====================================================
DEP 0018: Technical governance for the Django project
=====================================================

:DEP: 0018
:Author: Carlton Gibson, Emma Delescolle, Frank Gibson, Lily Acorn,
  Tim Schilling
:Implementation Team: Carlton Gibson, Emma Delescolle, Frank Gibson,
  Lily Acorn, Tim Schilling
:Shepherd: TBD
:Status: Draft
:Type: Process
:Created: 2025-12-01

.. contents:: Table of Contents
   :depth: 3
   :local:

Abstract
========

This defines the technical governance for the Django project. It describes
how Django is developed, how decisions are made, the organization of the
community from a technical perspective and how these are changed.

Terminology
===========

For clarity, this DEP uses the following terms to refer to existing
groups:

* "DSF" and "DSF Board": the Django Software Foundation and its Board
  of Directors, respectively.

* "DSF Individual members": the group of people who are members of
  the Django Software Foundation. `The current list can be found here
  <https://www.djangoproject.com/foundation/individual-members/>`_.

* "Django Fellows": a list of multiple people who have been or still
  are paid by the Django Software Foundation to perform various tasks,
  including triaging issues, reviewing and merging pull requests, and
  managing Django's releases.

* "Technical Team": A group of people who are delegated some
  responsibility by the Steering Council and DSF Board. The list
  of teams can be found at the `django/dsf-working-groups repo`_.

* "`Security Team`_": a group of people who respond to security
  issues handled under `Django's security process
  <https://www.djangoproject.com/security/>`_.

* "`Mergers Team`_": A group of people who merge pull requests to the
  `Django Git repository <https://github.com/django/django>`_.

* "`Releasers Team`_": A group of people who `build Django releases
  <https://docs.djangoproject.com/en/dev/internals/howto-release-django/>`_.

* "`Triage & Review Team`_": A group of people who assist with the
  processing of pull requests.

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

* "Security Release" means a Bugfix Release which included a fix for a
  security issue in Django being handled under `Django's security
  process <https://www.djangoproject.com/security/>`_.


Specification
=============

How Django is developed
-----------------------

Any person who signs the contributor CLA can write code for Django. Everyone is encouraged to open tickets, triage tickets and perform code reviews.

Commits can only be merged in by the `Mergers Team`_. A Merger can merge their own commits if it's been reviewed by another Merger, the `Triage & Review Team`_ or `Security Team`_. Members of the `Releasers Team`_ can also merge commits when they are related to releases.

Changes that fail to reach "minor consensus" can be escalated to the Steering Council for a final decision to merge.


How Django's technical direction is determined
----------------------------------------------

Everyone is encouraged to propose and provide feedback on new features for Django at any time on the new-features repo.

For features which qualify as a Major Change, proposers may be asked to use the DEP process.

If discussion of a Minor Change has failed to produce consensus, a member may ask the
Steering Council to make a decision.

Vetoed discussions and features are eligible to be revisited after six months.


How Django is released
----------------------

Only members of the `Releasers Team`_ may perform a release.

Django follows the time-based release schedule, as outlined in `DEP 44`_.

The `Security Team`_ may request a Security Release of Django. This should be performed at or as close as is practicable to the time of release requested by the `Security Team`_.


Steering Council role
---------------------

The Steering Council provides oversight of Django's development and
release process, assists in setting the direction of feature
development and releases, selects Mergers and Releasers, and has a
tie-breaking vote when other decision-making processes fail.

The Steering Council consists of five members.

The powers of the Steering Council are:

* To make a binding decision regarding any question of a technical
  change to Django.

* To manage the Steering Council's membership via an election with the
  DSF Board secretary.

* To create/update `technical teams`_

Steering Council's goals
++++++++++++++++++++++++

The Council's goal is twofold - to safeguard big decisions that affect
Django projects at a fundamental level, and to help shepherd the project's
future direction.

While the Council should not define this direction entirely by itself,
it should be the catalyst within the community for doing so - as such, it is
expected for Council members to actively participate in engaging with the
community, canvassing for ideas about big new features or directions to take
the framework, and reporting back to the community and the DSF Board on these
ideas and if the Council believes they should be followed.


Decision making process of the Steering Council
+++++++++++++++++++++++++++++++++++++++++++++++

When asked to make a technical decision, the Steering Council should first discuss this
amongst themselves. If there's agreement on a course of action, a single member will
respond the forum, ticket, or new-features repo on behalf of the Steering Council. It
may optionally include a dissenting opinion if someone wishes to include one.

If the Steering Council can't arrive at an agreement, a formal vote may be invoked.

Voting process of the Steering Council
++++++++++++++++++++++++++++++++++++++

When a vote of the Steering Council is held, they use the
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


Steering Council eligibility
++++++++++++++++++++++++++++

To be qualified for the Steering Council, a person must demonstrate:

* A history of substantive contributions to Django or the Django
  ecosystem. This history must begin at least 18 months prior to the
  individual's candidacy for the Steering Council, and include substantive
  contributions in at least two of these bullet points:

  * Code contributions on Django projects or major third-party packages in
    the Django ecosystem

  * Reviewing pull requests and/or triaging Django project tickets

  * Documentation, tutorials or blog posts

  * Discussions about Django on the django-developers mailing list or the
    Django Forum

  * Running Django-related events or user groups

* A history of engagement with the direction and future of Django.
  This does not need to be recent, but candidates who have not engaged in the
  past three years must still demonstrate an understanding of Django's changes
  and direction within those three years.


Steering Council elections
++++++++++++++++++++++++++

Whenever an election of the Steering Council is triggered, the following limits are put in place until the election process is complete:

* Any appointments to the roles of Merger and/or Releaser, other than
  of Django Fellows, are be temporary, and will require confirmation by
  the newly elected Steering Council.

* The Steering Council must not accept any DEPs or changes to DEPs, and
  must not change the governance process described in this document.

Steering Council election triggers
**********************************

Elections of the Steering Council are triggered by any of the following
events:

* The final Feature Release of a Major Release Series of Django if no
  election of the Steering Council has yet occurred during that Major
  Release Series.

* The resignation or another event that leaves Steering Council with
  fewer than three elected members. This can happen when the rest of
  the Steering Council would be replacement members via appointments.

* The Steering Council votes to hold an election.

Steering Council voting eligibility
***********************************

Only Individual members of the DSF are eligible to vote in elections of
the Steering Council.

The privilege to vote in elections of the Steering Council may be revoked at any time by one of the following:

* The Code of Conduct committee of the DSF for a violation of the Django
  Code of Conduct.

* The Code of Conduct Committee has deemed someone ineligible to participate
  in the community spaces of the Django project.

Steering Council election process
*********************************

The DSF shall manage the election process. Members of the DSF Board can stand
for election to the Steering Council if qualified, but any DSF Board
member who is a current member of the Steering Council or a candidate
in an upcoming election must abstain from taking part in the DSF
Board's oversight of that Steering Council election. The DSF Board can
delegate some responsibilities, but only the DSF Board can ratify the
results of a election.

The process of electing a Steering Council is as follows:

1. When an election is triggered, the Steering Council will notify the Secretary of the DSF, in
   writing, of the triggering of the election, and the condition which
   triggered it. The Secretary of the DSF then will post to the
   Django Forum and other appropriate venues to announce the election and its timeline.

2. As soon as the election is announced, the DSF Board shall begin a
   period of candidate registration. Any qualified person may register as a candidate; the
   candidate registration form and roster of candidates will be
   maintained by the DSF Board, and candidates must provide evidence
   of their qualifications as part of registration. The DSF Board can
   challenge and reject the registration of candidates it believes do
   not meet the qualifications of members of the Steering Council, or
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
   candidates with the highest vote totals will immediately become
   the new Steering Council.

Removing a single Steering Council member
*****************************************

A member of the Steering Council can be removed in the following ways:

* They become ineligible due to actions of the Code of Conduct
  committee of the DSF. If this occurs, the affected person
  immediately ceases to be a member of the Steering Council. If that
  person's ineligibility ends at a later date, they may become a
  candidate for the Steering Council again in an election occurring
  after that date.

* It is determined that they did not possess the qualifications of a
  member of the Steering Council. This determination must be made
  jointly by the other members of the Steering Council, and the DSF
  Board. A valid determination of ineligibility requires that all
  other members of the Steering Council vote to declare the affected person
  ineligible and that all members of the DSF Board who can vote on the issue (the
  affected person, if a DSF Board member, can not vote) vote "yes" on
  a motion that the person in question is ineligible.

* A member of the Steering Council resigns from the Steering Council by
  notifying the other members of the Steering Council of their intent to
  resign.

The Steering Council should try to fill a vacancy on the
Steering Council. This may involve the departing member if they are eligible
and willing. The process is as follows:

* Any member of the Steering Council, including an otherwise eligible
  but departing member, may nominate a candidate to fill a vacancy.

* The Steering Council will notify the Secretary of the DSF, in writing, of the nomination. The DSF
  Board will check the qualifications of the person nominated, and
  the Secretary of the DSF will notify the Steering Council of the
  result. If the DSF Board determines the nominated person is not
  qualified, the nomination must be discarded.

* A qualified nominee will fill the vacancy if the Steering Council votes
  to appoint the nominee. As an exception to the Steering Council voting
  process described above, this vote must be completed within one-week
  and it must be unanimous approval.

Removing the entire Steering Council
************************************

Any Django Software Foundation individual member may make a public statement
of no-confidence in the Steering Council by identifying a material breach of
their duties as defined in the technical governance. Upon seconding by another
individual member of the DSF the DSF Board SHALL no later than the next
scheduled board meeting evaluate the merits of the statement of
no-confidence.

If the statement is found to be accurate and correct the Board shall inform
the Steering Council of the breach and provide 2 weeks to rectify said
breach. If the Steering Council fails to rectify the breach in the time
allotted, a new Steering Council election will be triggered. Current members
of the Steering Council may run in the new election.

Technical teams
---------------

The Steering Council and DSF Board delegate certain responsibilities
and powers to various teams. These teams can be created without changes
to the technical governance document.

To see the list of technical teams and the process of adding new technical
teams, please see the `django/dsf-working-groups repo`_.


Interaction of the Steering Council and the Security Team
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++

The `Security Team`_ has the following powers:

* To request a Merger merge code to fix a security issue being handled
  under Django's security process.

* To request a Releaser issue a release of Django containing code to
  fix a security issue being handled under Django's security process.

In the event that the Steering Council feels the Security Team
has used the above powers inappropriately, the Steering Council may
appeal to the DSF Board to mediate the issue. Any member of the DSF
Board who is also a member of the Security Team or of the
Steering Council will abstain from participation in the DSF Board's
decision-making in such mediation. The decision of the DSF Board in
the dispute will be binding on both the Steering Council and the
Security Team.


Interaction of the Steering Council and other teams
+++++++++++++++++++++++++++++++++++++++++++++++++++

The Steering Council may oversee or have a liaison on various teams
and working groups in the Django community. In all cases
the following interactions should occur:

* The Steering Council may make requests of those teams, and those
  teams should accommodate those requests when reasonable and
  practicable.

* Those teams may make requests of the Steering Council, and the
  Steering Council should accommodate those requests when reasonable
  and practicable, provided that accommodating the request falls
  within the powers of the Steering Council.

In the event of a dispute between the Steering Council and a team,
the DSF Board shall serve as mediator. Any member of the DSF Board
who is also a member of the Steering Council or of the affected team
will abstain from the DSF Board's decision-making in such mediation.
The decision of the DSF Board in the dispute will be binding on both
the Steering Council and the affected team.


Changing this governance process
--------------------------------

Changes to this governance process shall be treated initially as Major
Changes to Django, and as such shall require the use of the DEP
process as described in DEP 1, with modifications as described below.

1. To reach the "accepted" state, a DEP proposing changes to this
   governance process must receive an outcome of "Accept" in a vote of
   the Steering Council with a score of at least 4, rather than the
   usual 3.

2. Once such a DEP reaches "accepted" status, the Steering Council will
   direct one of its members to notify the Secretary of the DSF, in
   writing, of the existence of an accepted DEP for changing the
   governance process.

3. The DSF Board will hold a vote on a
   motion to adopt the proposed change. If the DSF Board rejects the
   motion, the governance process will not change, and the Secretary
   of the DSF will notify the Steering Council, in writing, of the DSF
   Board's objections to the proposal. The DEP then returns to draft
   status. The DEP may be revised and restart the DEP approval process.

4. If the DSF Board accepts the motion, the DSF Board and the
   Steering Council will then hold separate votes on the question of
   whether the proposed change is significant enough to require
   approval by the community at large. If both the DSF Board and the
   Steering Council determine that the proposal is not significant
   enough to require such approval, the proposal then will be adopted
   and the DEP will immediately begin implementation.

5. If the DSF Board and/or the Steering Council determine that the
   proposal is significant enough to require approval by the community
   at large, the DSF Board will immediately call a special
   election. The qualifications of voters for the special election
   will be the same as those for elections of the Steering Council,
   and all persons eligible to vote for the Steering Council will
   automatically be eligible to vote in the special election. One week after that
   registration period closes, the special election will begin. Voting
   will be by secret ballot. Each voter will be presented with a
   ballot containing a link to the DEP, and links to any associated
   materials, and the question: "Shall the change to Django's
   governance, indicated above, be adopted?" Voters may vote "Yes",
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

This is a revisitation of Django's technical governance in which a
simplification and reduction was made to make it more approachable to more
people. The goals of these changes are the following:

- Make it easier to enact our governance
- Make it easier for others to understand our governance
- Make the governance more flexible, allowing more action with less procedure

It achieves those goals with the following:

- Presenting a merged governance document avoiding overruling
  governance documents (DEP 10 & 12)
- Reducing the number of sections and topics
- Including more headings
- Outsourcing specific topics such as releases and teams to other resources
- Removing the RFC 2119 language
- Reducing the scope of eligible voters to reflect and take advantages of the
  broader DSF Individual Membership eligibility


Rationale
=========

Similar to DEP 12, this is another iteration on our governance. While this is
a significant change in terms of content, the spirit and intent of Django's
technical governance remains the same. All governance requires periodic
cultivation, and this should be seen as one of those instances.


Backwards Compatibility
=======================

This document supersedes both DEP 10 and DEP 12.


Reference Implementation
========================

N/A


Copyright
=========

This document has been placed in the public domain per the Creative Commons
CC0 1.0 Universal license (http://creativecommons.org/publicdomain/zero/1.0/deed).

(All DEPs must include this exact copyright statement.)

.. _DEP 44: https://github.com/django/deps/blob/main/accepted/0044-clarify-release-process.rst
.. _Mergers Team: https://github.com/django/dsf-working-groups/blob/main/active/mergers-team.md
.. _Releasers Team: https://github.com/django/dsf-working-groups/blob/main/active/releasers-team.md
.. _Security Team: https://github.com/django/dsf-working-groups/blob/main/active/security-team.md
.. _Triage & Review Team: https://github.com/django/dsf-working-groups/blob/main/active/triage-and-review-team.md
.. _django/dsf-working-groups repo: https://github.com/django/dsf-working-groups
