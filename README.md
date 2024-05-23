# RFCs
```
These standards (or lack of them) are stated explicitly for two reasons.
First, there is a tendency to view a written statement as ipso facto
authoritative, and we hope to promote the exchange and discussion of
considerably less than authoritative ideas.  Second, there is a natural
hesitancy to publish something unpolished, and we hope to ease this
inhibition.
  -- Stephen Crocker RFC3 (https://tools.ietf.org/html/rfc3)
```

RFCs are an effective way for an engineering organization to manage both historical and planned changes. With curation, your RFC archive tells the story of your company's technology and thought process. We believe in an open and honest dialog between all engineers. Because of this, we've embraced the Request for Comments system.

1. Any person at the company can create a Request for Comment and have it included in this series
2. These RFCs should always choose "timely" over "perfect"
3. These are not authoritative ideas (what's authoritative is what's in the code)

Since the inception of the RFC process modern tools (hi git!) have made it possible to build a rich RFC process with minimal effort. Github repositories all have code commenting and review tools, capable of capturing the discussion surrounding RFCs, and which RFCs are being strongly championed by the company.

Many software changes, including bug fixes and documentation improvements can be implemented and reviewed via the normal git pull request workflow without ever touching this process. However, we do ask that bigger requests and ideas follow a bit of formality, especially when you are thinking about changes that impact other engineers elsewhere in the company. By creating an RFC, you're guaranteed that impacted folks have an adequate heads-up on the changes.

Please refer to [RFC1](https://github.com/tiagoferreiraWex/rfc/blob/tiagoferreiraWex-RFC0001/RFCs/Informational/0001-using_rfcs.md) "Using RFCs" for a detailed explanation of why RFCs are important and how to contribute your own RFC to this series.

# The Process
* Branch this repository
* Copy the template file: `cp RFCs/0000-template.md RFCs/[Category]/0000-my_feature.md` `[Category]` being the chosen category for your RFC
* Fill in the RFC. Put thought into the sections, but remember that **timely is more important than perfect**
* Commit the changes to have your RFC created automatically to the [RFC Confluence Space](https://wexinc.atlassian.net/wiki/spaces/ITRFC/overview?homepageId=154384499250)
* Help drive consensus on the RFC. Work to understand concerns. Don't forget to collect the feedback from meetings and post them as comments in the Confluence page for the RFC
* Be willing to update the RFC as yours (and the company's) understanding evolves
* Assist in wrapping up discussions when a final call for comments is made

# What An Approved RFC Means
RFC approval means that the RFC will be assigned an ID and added to the series. RFCs may not be added to the series for reasons such as:
* There is no clear consensus, and we are concerned the publication would be seen as authoritative
* You have informed the domain owner that you do not wish for the RFC to be published
* The RFC is not complete, making consensus difficult

If the RFC is not approved for publication, the domain owner responsible for editing RFCs will provide clear and detailed feedback regarding why the RFC wasn't published. Your RFC will continue to exist in the code review history and available in searches.

A published RFC ensures that other teams are made aware of the document.

Modifications to "active" RFCs can be done in follow-up pull requests. We strive to write each RFC that refers to architecture in a manner that it will reflect the final design; but the nature of the process means that we cannot expect every merged RFC to actually reflect what the end result will be at the time of release.

In general, once published, RFCs should not be substantially changed. Only very minor changes should be submitted as amendments. More substantial changes should be new RFCs, with a link added to the original RFC.

# Acknowledgments / License
This work was inspired by the [Rust RFC Process](https://github.com/rust-lang/rfcs) and IETF [RFC3](https://tools.ietf.org/html/rfc3) "Documentation Conventions".

This repository text is available under both the Apache-2.0 and MIT license.

Apache License, Version 2.0, (LICENSE-APACHE or http://www.apache.org/licenses/LICENSE-2.0)
MIT license (LICENSE-MIT or http://opensource.org/licenses/MIT)
