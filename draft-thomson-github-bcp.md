---
title: Using github at the IETF
abbrev: github@IETF
docname: draft-thomson-github-bcp-latest
category: bcp
area: General

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

This document describes best practices for working groups that use github for
their work.


--- note_Note_to_Readers

Discussion of this draft takes place on the github@ietf mailing list
(ietf-and-github@ietf.org), which is archived at
<https://mailarchive.ietf.org/arch/search/?email_list=ietf-and-github>.


--- middle

# Introduction

Developing a specification shares a great deal in common with the development of
software.  Modern engineering practice blah blah


## What is git?

Distributed version control.


## What is Github?

Github is a service operated at https://github.com.  Github provides a
centralized store for git repositories and features that support the management
of source code projects.

In addition to providing an simplified interface to the underlying revision
control, Github provides basic user management, an issue tracker, a wiki, and
web hosting for projects.


## Notational Conventions

The words "MUST", "MUST NOT", "SHOULD", and "MAY" are used in this document.
It's not shouting; when they are capitalized, they have the special meaning
defined in {{!RFC2119}}.


# Ownership and Management


# Contribution Methods

## Issues

## Pull Requests

## Mailing Lists



# Continuous Integration




# Github Limitations

At the time of writing, github.com is not reachable using IPv6.  This is an
affront to all that the IETF stands for and a slap in the face to all the people
who worked so hard to design and deploy the latest version of the Internet
Protocol.  While we can collectively be ashamed and disappointed that this is
the situation, that doesn't necessarily make the service any less useful.


# Security Considerations

Continuity of operations is always a consideration when taking a dependency on
an external service.

Consistent use of git reduces the exposure to a system failure because the
primary repository is replicated in multiple locations.  This extends to web
pages that are hosted because the content of the page is saved in the main
repository.

However, other information maintained on Github is more vulnerable to loss.
This includes issues and discussion on those issues, discussion and reviews of
commits and pull requests, and any content hosted on the wiki.


# IANA Considerations

This document has no IANA actions.


--- back

# Acknowledgments

Mark Nottingham has done a lot to pioneer the use of github at the IETF.
