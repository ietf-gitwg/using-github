---
title: Using Github at the IETF
abbrev: Github Usage
docname: draft-thomson-github-bcp-latest
category: bcp
area: General
workgroup: Network

stand_alone: yes
pi: [toc, sortrefs, symrefs, docmapping]

author:
 -
   ins: M. Thomson
   name: Martin Thomson
   org: Mozilla
   email: martin.thomson@gmail.com
   role: editor
 -
   ins: A. Atlas
   name: Alia Atlas
   org: Juniper Networks
   email: akatlas@gmail.com
   role: editor


--- abstract

This document describes best practices for working groups that use Github for
their work.


--- note_Note_to_Readers

Discussion of this document takes place on the github@ietf mailing list
(ietf-and-github@ietf.org), which is archived at
<https://mailarchive.ietf.org/arch/search/?email_list=ietf-and-github>.


--- middle

# Introduction

Developing a specification shares a great deal in common with the development of
software.  Modern engineering practices that favor rapid iteration find that the
use of version control systems is critical in managing changes.

This document describes how the IETF uses Github through the development of
Internet-Drafts.  This concentrates on the work that occurs within IETF working
groups.  Recommendations for working groups and their chairs are made for
integrating these tools with their processes.

This document is meant as a companion to RFC 2418 {{?RFC2418}}.  It provides
guidance to working group chairs and participants on how they can best use
Github.  The small number of rules in this document are there to ensure common
usage patterns between working groups and to avoid issues that have been
encountered in the past.


## What is git?

Git is a distributed version control system.  Each instance of a repository
contains a number of revisions.  Each revision stores the complete state of a
set of files.  Users are able to create new revisions in their copy of a
repository and share revisions between copies of repositories.


## What is Github?

Github is a service operated at [https://github.com/](https://github.com/).  Github provides a
centralized store for git repositories.

The primary function of Github is to provide a simplified interface to the
underlying revision control system.  In addition, Github provides basic user
management, an issue tracker, a wiki, and web hosting for projects.

This document contains some content that is quite specific to Github.  A working
group that decides to adopt one of the several different alternative services
can still benefit from the general guidance in this document.


## Notational Conventions

The words "MUST", "MUST NOT", "SHOULD", and "MAY" are used in this document.
It's not shouting; when they are capitalized, they have the special meaning
defined in {{!RFC2119}}.


# Deciding to Use Github

The decision to use Github formally is the responsibility of a working group
chair.  Chairs SHOULD involve area directors in this decision if they intend to
use Github for anything more than managing of edits.

A document editor can still use Github independently for documents that they
edit even if the working group does not expressly choose to use Github.  This
recognizes that editors have traditionally chosen their own methods for managing
the documents they edit.


## What to Use Github For {#usage}

Working group chairs have to decide what Github features the working group will
rely upon.  {{features}} contains a more thorough discussion on the different
features that can be used.

Once a document is published in a repository on Github, many features like pull
requests, issue tracking or the wiki can be individually disabled.  If specific
features are not used by the working group in the development of the document,
disabling those features avoids creating confusion in the wider community about
what can be used.


## Communicating Policies

Working group chairs that decide to use Github MUST inform their working groups
of their decision using the working group mailing list .  An email outlining how
the working group intends to use Github is sufficient, though it might be
helpful to occasionally remind new contributors of these guidelines.

Working group chairs are responsible for ensuring that any policy they adopt is
enforced and maintained.

Updating the README file with details of the process ensures that the process is
recorded in a stable location other than the mailing list archive.  This also
makes any working group policies available to casual contributors who might only
interact with the Github repository.

Github also provides a feature whereby a file named CONTRIBUTING is linked to
prominently on certain pages.  This file can also be used to inform new
contributors of any policies.


## Note Well

One important policy is the IETF IPR policy (see {{!RFC5378}}, {{!RFC3979}}, and
{{!RFC4879}}).  Part of this policy requires making contributors aware of the
policy.  The following text MUST be included prominently in any document
repository:
{:br }

> This repository relates to activities in the Internet Engineering Task
  Force(IETF). All material in this repository is considered Contributions to
  the IETF Standards Process, as defined in the intellectual property policies
  of IETF currently designated as [BCP
  78](https://www.rfc-editor.org/info/bcp78), [BCP
  79](https://www.rfc-editor.org/info/bcp79) and the IETF [Trust Legal
  Provisions (TLP) Relating to IETF
  Documents](http://trustee.ietf.org/trust-legal-provisions.html).

> Any edit, commit, pull request, issue, comment or other change made to this
  repository constitutes Contributions to the [IETF Standards
  Process](https://www.ietf.org/).

> You agree to comply with all applicable IETF policies and procedures,
  including, BCP 78, 79, the TLP, and the TLP rules regarding code components
  (e.g. being subject to a Simplified BSD License) in Contributions.

This boilerplate text represents what is minimally included, but in many cases
there is a benefit to including pointers to other working groups material, the
datatracker, specific drafts, or websites.  Adding such text is at the
discretion of the working group chairs.

Including this information in the CONTRIBUTING file is sufficient.  A link to
this text from the README file ensures that new contributors are most likely to
see the message.


# Management and Structure

Working groups that choose to use Github SHOULD create a new organization for
the working group.  Managing a single IETF- or Area-wide organization creates
too much overhead for general management tasks.

Working group chairs and area directors MUST be assigned administrator or owner
privileges for the organization.  Administrator privileges are preferred, since
this does not also include the ability to push to all repositories.

## Repositories

New repositories can be created within the working group organization at the
discretion of the chairs.  Chairs could decide to only create new repositories
for adopted working group items, or they might create repositories for
individual documents on request.

All repositories for working group documents MUST be public.  Repositories for
private documents MAY be kept private, but only where there is a specific reason
for doing so.  For instance, a document that details a security vulnerability
might be kept private prior to its initial publication as an Internet-Draft.
Once an Internet-Draft is published, repositories SHOULD be made public.

The adoption status of any document MUST be clear from the contents of the
repository.  This can be achieved by having the name of the document reflect
status (that is, draft-ietf-\<wg>-... indicates that the document was adopted),
or through a prominent notice (such as in the README).

Experience has shown that maintaining separate repositories for independent
documents is most manageable.  This allows the work in that repository to be
focused on a single item.

Closely related documents, such as those that together address a single
milestone, might be placed in a single repository.  This allows editors to more
easily manage changes and issues that affect multiple documents.

Maintaining multiple documents in the same repository can add overheads that
negatively affect individual documents.  For instance, issues might require
additional markings to identify the document that they affect.  Also, because
editors all have write access to the repository, managing the set of people with
write access to a larger repository is more difficult.


## Access Controls

Working group chairs MUST give document editors write access to document
repositories.  This can be done by creating teams with write access and
allocating editors to those teams, or by making editors collaborators on the
repository.

Working group chairs MAY also grant other individuals write access for other
reasons, such as maintaining supporting code or build configurations.  Working
group chairs, as administrators or owners of the organization might also have
write access to repositories.  Users other than document editors, including
chairs, SHOULD NOT write to working group documents unless with prior
coordination with document editors.


## Document Formats

In addition to the canonical XML format {{?RFC7991}}, document editors might
choose to use a different input form for editing documents, such as markdown.
The choice of input format is left to document editors.


# Contribution Methods {#features}

Contributions to documents come in many forms.  Github provides a range of
options in addition to email.  Input on Github can take the form of new issues
and pull requests, comments on issues and pull requests, and comments on
commits.


## Issues

The Github issue tracker can be an effective way of managing the set of open
issues on a document.  The record of issues - both open and closed - can be a
useful way of recording decisions made by a working group.

Issues can be given arbitrary labels, assigned to contributors, and assembled
into milestones.  The issue tracker is integrated into the repository; an issue
can be closed using a special marker in a commit message.

Working group chairs MUST decide how the Github issue tracker are used.  Use of
the issue tracker could be limited to recording the existence of issues, or it
might be used as the venue for substantial technical discussion between
contributors.

Working groups have found that a system of labelling issues can be effective in
managing issues.  For instance, marking substantive issues separately from
editorial can be helpful.  Using labels can also be helpful in identifying
issues for which consensus has been achieved, but that require editors to
integrate the changes into a document.  Labels might also be used to identify
particular categories of issues.

If labels are a core part of working group process, chairs MUST communicate any
process to the working group.  This includes the semantics of labels, and who
can apply and remove these labels.

Editors have write access to repositories, which also allows them to close
issues.  The user that opens an issue is also able to close the issue.  Chairs
MUST determine who is permitted to close an issue and under what conditions.


## Pull Requests

Pull requests are the Github feature that allow users to request changes to a
repository.  A user does not need to have write access to a repository to create
a pull request.  A user can create a "fork", or copy, of any public repository.
The user has write access to their own fork, allowing them to make local
changes.  A pull request asks the owner of a repository to merge a specific set
of changes from a fork (or any branch) into their copy.

Editors SHOULD make pull requests for all substantial changes rather than
commiting directly to the "master" branch of the repository.

As with issues, using pull requests creates a record of actions taken.  For
significant changes, leaving the pull request open allows for a period of
discussion within the working group.

Groups of editors could adopt a practice of having one editor create a pull
request and another merge it.  This ensures that changes are reviewed by
editors.  Editors are given discretion in how they manage changes.

Working groups MUST determine who is permitted to merge pull requests.  Document
editors SHOULD be permitted to merge pull requests at their discretion.  This
requires that editors exercise some judgment.  Working group chairs MAY
occasionally identify a pull request and request that editors withhold merging
until working group consensus has been assessed.

Note that the copy of a document that is maintained on Github does not need to
be a perfect reflection of working group consensus at every point in time.
Document editors need some flexibility in how they manage a document.


## Monitoring Activity

Several working groups have created read-only mailing lists that subscribe to
activity notifications on repositories.  The volume of information on these
lists can be too high to monitor actively, but access to an archive of actions
can be useful.

A working group that uses Github SHOULD provide this facility.  However, setting
up this mailing list can be onerous and better solutions are still being sought.


# Internet-Drafts

During the development of a document, individual revisions of a document can be
built and formally submitted as an Internet-Draft.  This creates a stable
snapshot and makes the content of the in-progress document available to a wider
audience.

Editors SHOULD endeavour to create a new Internet-Draft submission two weeks
prior to every session (see Section 7.1 of {{?RFC2418}}).  Participants in a
session can't be expected to monitor changes to documents in real-time; an
Internet-Draft ensures that there is a common, stable state that is known to all
participants.

Working group chairs MAY request the creation of an Internet-Draft at any time,
in consultation with document editors.


# Assessing Consensus

The work that occurs on Github could be part of the consensus process, but the
ultimate decision on consensus regarding a document is made by the chairs
{{!RFC2026}}.

Monitoring activity on Github could require a greater time commitment than
following a mailing list.  This is because there is an increased volume of
activity to follow.  Participants who wish to limit this time commitment might
follow Github activity selectively, either by following only specific issues or
by occasionally reviewing the state of the document.  Chairs are reminded that
assessing consensus based on Github content alone might not always reach all
interested participants.

A working group chair SHOULD consult the working group mailing list for any
issue that is potentially contentious.  Relying on input provided through Github
alone might result in gaining input from a narrower set of participants.  This
includes important milestones like working group last-call, where review from
the widest possible audience ensures a higher quality document.


# Continuous Integration

Various third-party services offer the ability to run tests and other
computation when changes are made to a document.

One common practice is to use these continuous integration services to build a
text or HTML version of a document.  This is then published to Github Pages,
which allows users to view a version of the most recent revision of a document.

Continuous integration can also validate pull requests and other changes for
errors.  The most basic check is whether the source file can be transformed
successful into a valid Internet-Draft.  For example, this might include
checking that XML source is syntactically correct.

For documents that use formal languages a part of specifications, such as schema
or source code, a continuous integration system might also be used to validate
any formal language that the document contains.  Tests for any source code that
the document contains might be run, or examples might be checked for
correctness.


# Github Limitations

At the time of writing, github.com is not reachable using IPv6.  This is an
affront to all that the IETF stands for and a slap in the face to all the people
who worked so hard to design and deploy the latest version of the Internet
Protocol.  While we can collectively be ashamed and disappointed that this is
the situation, that doesn't necessarily make the service any less useful.


# Security Considerations

Continuity of operations is always a consideration when taking a dependency on
an external service.  If Github were to fail in some way, anyone relying upon
its services would be seriously affected.

Consistent use of git reduces the exposure to a system failure because the
primary repository is replicated in multiple locations.  This extends to web
pages that are hosted because the content of the page is saved in the main
repository.  Maintaining a mirror of a repository that is hosted on Github is
relatively simple and might be considered as a way to provide a backup for the
primary repository.

However, other information maintained on Github is more vulnerable to loss.
This includes issues and discussion on those issues, discussion and reviews of
commits and pull requests, and any content hosted on the wiki.  Tools exist for
extracting this information for backup.

Malicious actions by compromised or malcontent editors, chairs and area
directors are relevant in maintaining the integrity of the content that Github
hosts.  Backups allow for recovery of content, and regular submissions as
Internet-Drafts ensure that work is not lost completely.


# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments

Mark Nottingham has done a lot to pioneer the use of github at the IETF.
