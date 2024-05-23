---
RFC: 1
Title: Using RFCs
Start: 5/15/2024
PR: 0
---

# Using RFCs

# Summary
This is a proposal to use RFCs in engineering. The "Request for Comments" system is used by several successful open source groups, and provides a framework for managing complex change and its documentation. Not everything needs an RFC, but since this can slow a company down, the proposal itself deserves an RFC to explain the rationale and reasoning.

# Motivation
Larger changes, while still reversible, require some amount of documentation as to why the decisions were made and the technical climate at the time the idea was proposed. Historically, these live in wikis or alternative documentation systems. These locations are either difficult to search, too far removed from the code, or are rarely seen as a source of truth.

This solution proposes a documentation system that lives in code, uses plain text for authoring, and takes advantage of existing git collaboration tools in order to edit, maintain, and build consensus on code ideas that impact all of engineering. It is based on the RFC process as designed by the <a href="https://www.ietf.org/process/rfcs/" target="_blank">IETF</a> [IETF](https://www.ietf.org/process/rfcs/{:target="_blank"}) and later adapted for open source projects. For the feedback and comment part this RFC will also be added to Confluence.

# Guide Implementation
To make sure you've hit on all major parts of an RFC, this RFC can serve as a reference model.

## Creating a new RFC
Creating a new RFC should be something you start as soon as it feels like the work is substantial and worth getting additional opinions on. You can start an RFC by creating a branch in this repository and copying the template file to a new file in the `text/` directory: `cp 0000-template.md text/0000-my_feature_name.md`, replacing `my_feature_name` with a shortened name for your feature or proposal. You'll be given a simple markdown document, for which you can edit the sections and start your proposal. 

## Confluence integration
This repo uses a github action workflow to automatically publish your RFC file to Confluence. Once you commit the changes to your local branch, a confluence page will be created with you RFC and the process could be started.

## Getting Feedback
The beauty of having the Confluence integratios is that you can have your RFC in your own local branch, at an accessible URL, which you can share to other individuals to get feedback. While we won't be prescriptive on who you should be reaching out to at this stage, testing your ideas and assumptions with several senior engineers can help work out any large issues. If you don't have great solutions yet, that's okay! Just mark the areas as still open and needing input. 

> **Open Question:** What is going to be the suggested communication process? For example: the creator should review the RFC with its peers before submitting a Pull request. Then submit it to a broader audience.

> **Open Question:** How RFC would be shared when created? Are we going to have a community or something that will receive all RFCs?Or the communication would be organic?

## The Pull Request
When you feel you're ready to get more feedback beyond your immediate peers, it's time to make a pull request. Most git tools have a way to submit a pull request to the upstream repository. [For example, here's GitHub's instructions](https://help.github.com/articles/creating-a-pull-request/). With a formal pull request, folks can comment on the pull request, suggest changes, and have discussions about the issue. More importantly, all of these discussions are captured and will live on in the pull request's history.

## Manage Feedback
As more eyes look at your RFC, they'll have their own valuable thoughts and opinions to share. As the creator of the RFC, it's generally good to address feedback and if necessary, make changes to the RFC. If you have a meeting in which the RFC is discussed, be sure to capture the notes and share them in the RFC's pull request as a comment. After some amount of time, the folks closest to the domain at the company will ask that all final comments are submitted.

## Final Feedback
To avoid discussion going in circles forever, an owner in the domain related to your RFC will ask for "final comments". At that point, the discussion will wrap up, and the group accountable for the domain related to your RFC will determine if this RFC proposal needs to be widely distributed. If distribution of the RFC is decided, the pull request will be accepted and the RFC given a numeric ID. If a RFC was not chosen to be distributed, that request and the RFC document continue to exist in your collaborative repository's ticket system and in WEX IT RFC Confluence Space, capturing the rationale and explanation.

> **Open Question:** Who can declare that an RFC is entering its Final Feedback phase?

> **Open Question:** What is the decision process going to be for resolving an RFC? It could be a meeting or an up/down vote by N individuals in the company.

## Adoption
When an RFC is chosen for distribution, it will be given a numeric ID corresponding with the next sequence in the `/text` directory (This is why your file was `0000-my_feature_name` originally). While this does not guarantee the opinion is widely adopted, it does ensure that it has the support of the individuals accountable for the domain relevant to the RFC.

If an RFC is not chosen for distribution, clear explanations will be provided by the domain owner and the pull request closed. This does not prevent the implementation of the idea, but the decision on an RFC carries significant weight. Remember, RFCs exist to inform and share information and intent. Also, it should be included in WEX IT RFC Confluence Space under the archived session.

# Reference Implementation
`0000-template.md` contains the minimum template needed for an effective RFC process. An RFC pull request document must meet the folowing criteria:
* Adds to `text/` with a filename `0000-my_feature_name.md` where `my_feature_name` maps to the feature name in the header of the RFC
* The RFC pull request contains a single file change that is the `0000-my_feature_name.md` file
* The RFC file contains the following sections: Summary, Motivation, Guide, Reference Implementation, Drawbacks, Alternatives

> **Open Question:** Should we include a Diagram session?

# Drawbacks
**Time:** A common cited problem for an RFC process is the time investment asked of every participating engineer. This is in error, as the time required to create an RFC is ultimately spent in several other ways stemming from a lack of consensus or documentation. A proposal for an RFC has the highest ROI at the beginning of the process, not the end. In situations where there is already substantial buy-in from domain owners, the RFC is a lightweight process of recording what was already agreed upon. In situations where there is disagreement, then this time spent in the RFC process becomes time well spent.

**Owners:** Ownership is something difficult for engineering organizations to talk about. It requires the engineering organization to agree outright that one or more individuals are operating in the best interest of a domain and will invest the time ensuring their domain remains well maintained. However, these owners already exist; they are the folks engineers turn to with questions. To offset the obligation of being an owner, ownership can be added to an individuals engineering expectations and factored into any leverage / impact criteria for their role.

> **Open Question:** Who is going to be the RFC Owner?

# Rationale / Alternatives
## Decision Bodies
RFCs are a better solution than forming an Architecture Council. The move to create an Architecture Council forms when there is no longer a way to create consensus around a topic. Unfortunately, AC meetings are often reduced to debating semantics and rarely making decisions regarding proposed changes to the domain. Another common problem with ACs is they often lack a holistic view of the domains in engineering. Without the right individuals representing the needs of the domain, the best decisions cannot be made. RFCs avoid this process. Each RFC naturally drives towards a decision (and a decision is required on every RFC). Every RFC can be handled asynchronously, avoiding the challenges associated with running a regular meeting with senior engineers.

RFCs are a more comprehensive solution than [Architecture Decision Records (ADRs)](https://www.thoughtworks.com/radar/techniques/lightweight-architecture-decision-records) and [whydocs](https://web.archive.org/web/20161119073912/https://medium.com/@jakob/a-better-framework-for-status-5c3dde887aa5). While ADRs and whydocs can effectively capture decisions being made during the development phase of software, they fail to capture ideas and intent. Why we **don't** do things is equally important to why we **do**, necessitating a more complete process.

## Documentation Systems
RFCs are superior to wikis. While wikis often have better search facilities, wiki pages do not easily foster the discussion needed around major engineering topics. Wikis lie outside of an engineer's normal workflow and tools, making them less visible to the engineering organization. RFCs are a naturally better fit for the engineering workflow, leveraging GitHub/GitLab/BitBucket/etc and their native review and discussion tools.

RFCs are a better alternative than document cloud options. While document clouds have better discussion tools than wikis, the ability to locate documents is restricted to the search facilities and sharing permissions available in the document cloud. For example, items shared with a limited subset of engineers are unlikely to receive holistic review. Further, when the document author leaves the company, the decisions risk being lost unless the owner is migrated. RFCs avoid this by living as code in a git repository, owned by the engineering organization as a whole.

# Unresolved Questions
Unresolved Questions are marked inline in the following format:

> **Open Question:** topic

These questions remain open and require either textual amendment to define the operating rules of your unique RFC process, or a supplemental RFC proposing adaptations that build upon this idea.
