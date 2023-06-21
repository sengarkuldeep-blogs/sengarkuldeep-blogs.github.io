---
layout: post
title: "Omnibus PR"
date: 2022-03-16
categories:
  - "code"
---
An Omnibus PR is like [Omnibus Bill](https://en.wikipedia.org/wiki/Omnibus_bill) that covers a number of diverse and unrelated changes. 

<!-- more -->

> A Code review a stage in software development lifecycle where developers consciously and systematically convene with fellow developers to look over the code and find out mistakes. 

Once the developer is finished with writing code, they send a request to other developers inviting them to review the code, i.e. to be a reviewer. A Reviewer looks at five main areas:
1. Code issues: Are there any obvious logic error in the code
2. Consistency with product requirement: Looking at the requirement, are all the cases fully implemented
3. Quality of code: Does the new code conforms to existing style guideline.
4. Quality of documentation: Does the new code incorporate accompanying documentation update
5. Quality of tests: Are the new automated tests sufficient? Do the existing tests need to rewritten to account for code change?


## A short history

Code review was first introduced in the 1976 when Michael Fagan wrote a series of journals for IBM and published a ground breaking paper, [Design and code inspections to reduce errors in program development](https://ieeexplore.ieee.org/document/5388086), The idea of formal and systematic code review caught on quickly. It generally consisted of bunch of people sitting together around the table poring over dot-matrix print-outs of computer code. 

# Why 

Here are some of the benefits that code review provides:
- Improved code quality: By detecting issues in the code early and ensuring consistent standard help in improving code quality. This further helps in building a robust software. 
- Support knowledge transfer: By looking at other developer's code it allows developers to learn more about varying feature of the software and also learn reliable techniques and best practices. 
- Better documentation: Code review helps the team create better documentation and keep it updated as well. 
- Facilitate easier QA: Having a consistent standard and code with less logical issues helps testers to better understand the code. This also helps to reduce the obvious errors in early stage and save time during testing process. 


## What is Omnibus PR
Omnibus PR is like an [Omnibus bill](https://en.wikipedia.org/wiki/Omnibus_bill) that has a diverse and unrelated changes. It can create following problems: 
1. Cognitive Load on reviewers: Cognitive load for revieweing a PR increases exponentially with the size of the PR. 
2. Omnibus factor: Derived from *Omnibus Bill* where the code related to the key feature is missed during a review as there are too many things to look at. 

### How to avoid

One simple way to avoid Omnibus PR is to have smaller ones. When you break down your work into smaller chunks and raise small and incremental changes it reduces the possibility of mixing to features in a single PR and thus causing Omibus PR. 
