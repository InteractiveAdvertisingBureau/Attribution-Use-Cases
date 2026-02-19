![](https://drive.google.com/uc?id=1MStOYYaZDqrvuOwlmecX0iayL0Jt_eAN)

# Attribution Use Cases Version 1.0


## About Attribution Use Cases

In browsers where third party cookies are not available there is a need to compute and measure conversions. A new set of standards are emerging that aim to bridge the gap between third party cookies and attribution measurement. 

In this document we describe a set of key advertising use cases primarily focused on attribution and conversion measurement. The goal is to document a set of key advertising use cases to help browser standard developers design and implement their solutions. 

This document focuses on key use cases primarily around flexibility needed for reporting and reconciliation between multiple parties, complex and custom attribution models, flagging invalid traffic, and novel potential new features such as app-to-web/web-to-app conversions.

This document is largely based on [TechLab’s Privacy Sandbox Fit-Gap Analysis](https://iabtechlab.com/wp-content/uploads/2024/06/Privacy-Sandbox-Fit-Gap-Analysis-FINAL.pdf) and [Digital Advertising Industry Ad Systems Requirements](https://iabtechlab.com/wp-content/uploads/2024/10/Digital-Advertising-Industry-Ad-System-Requirements-Version-1.0.pdf).

This document is developed by [IAB Tech Lab’s Private Ad Systems Task Force](https://iabtechlab.com/working-groups/privacy-sandbox-task-force/).

### License

The Digital Advertising Industry Requirements document is licensed under a Creative Commons Attribution 3.0 License. To view a copy of this license, visit creativecommons.org/licenses/by/3.0/ or write to Creative Commons, 171 Second Street, Suite 300, San Francisco, CA 94105, USA.

### IAB Tech Lab Leads

Miguel Morales, Director Addressability & Privacy Enhancing Technologies (PETs)
Shailley Singh, EVP Product & COO, IAB Tech Lab


### About IAB Tech Lab

The IAB Technology Laboratory is a nonprofit research and development consortium charged with producing and helping companies implement global industry technical standards and solutions. The goal of the Tech Lab is to reduce friction associated with the digital advertising and marketing supply chain while contributing to the safe growth of an industry.

The IAB Tech Lab spearheads the development of technical standards, creates and maintains a code library to assist in rapid, cost-effective implementation of IAB standards, and establishes a test platform for companies to evaluate the compatibility of their technology solutions with IAB standards, which for 18 years have been the foundation for interoperability and profitable growth in the digital advertising supply chain. Further details about the IAB Technology Lab can be found at [https://iabtechlab.com](https://iabtechlab.com).

### Disclaimer

THE STANDARDS, THE SPECIFICATIONS, THE MEASUREMENT GUIDELINES, AND ANY OTHER MATERIALS OR SERVICES PROVIDED TO OR USED BY YOU HEREUNDER (THE “PRODUCTS AND SERVICES”) ARE PROVIDED “AS IS” AND “AS AVAILABLE,” AND IAB TECHNOLOGY LABORATORY, INC. (“TECH LAB”) MAKES NO WARRANTY WITH RESPECT TO THE SAME AND HEREBY DISCLAIMS ANY AND ALL EXPRESS, IMPLIED, OR STATUTORY WARRANTIES, INCLUDING, WITHOUT LIMITATION, ANY WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, AVAILABILITY, ERROR-FREE OR UNINTERRUPTED OPERATION, AND ANY WARRANTIES ARISING FROM A COURSE OF DEALING, COURSE OF PERFORMANCE, OR USAGE OF TRADE. TO THE EXTENT THAT TECH LAB MAY NOT AS A MATTER OF APPLICABLE LAW DISCLAIM ANY IMPLIED WARRANTY, THE SCOPE AND DURATION OF SUCH WARRANTY WILL BE THE MINIMUM PERMITTED UNDER SUCH LAW. THE PRODUCTS AND SERVICES DO NOT CONSTITUTE BUSINESS OR LEGAL ADVICE. TECH LAB DOES NOT WARRANT THAT THE PRODUCTS AND SERVICES PROVIDED TO OR USED BY YOU HEREUNDER SHALL CAUSE YOU AND/OR YOUR PRODUCTS OR SERVICES TO BE IN COMPLIANCE WITH ANY APPLICABLE LAWS, REGULATIONS, OR SELF-REGULATORY FRAMEWORKS, AND YOU ARE SOLELY RESPONSIBLE FOR COMPLIANCE WITH THE SAME, INCLUDING, BUT NOT LIMITED TO, DATA PROTECTION LAWS, SUCH AS THE PERSONAL INFORMATION PROTECTION AND ELECTRONIC DOCUMENTS ACT (CANADA), THE DATA PROTECTION DIRECTIVE (EU), THE E-PRIVACY DIRECTIVE (EU), THE GENERAL DATA PROTECTION REGULATION (EU), AND THE E-PRIVACY REGULATION (EU) AS AND WHEN THEY BECOME EFFECTIVE.

## Table of Contents

- [About Attribution Use Cases](https://github.com/InteractiveAdvertisingBureau/Attribution-Use-Cases/blob/main/Attribution%20Use%20Cases%20v1.md#about-attribution-use-cases)
  - [License](https://github.com/InteractiveAdvertisingBureau/Attribution-Use-Cases/blob/main/Attribution%20Use%20Cases%20v1.md#license)
  - [IAB Tech Lab Leads](https://github.com/InteractiveAdvertisingBureau/Attribution-Use-Cases/blob/main/Attribution%20Use%20Cases%20v1.md#iab-tech-lab-leads)
  - [About IAB Tech Lab](https://github.com/InteractiveAdvertisingBureau/Attribution-Use-Cases/blob/main/Attribution%20Use%20Cases%20v1.md#about-iab-tech-lab)
  - [Disclaimer](https://github.com/InteractiveAdvertisingBureau/Attribution-Use-Cases/blob/main/Attribution%20Use%20Cases%20v1.md#disclaimer)
- [Table of Contents](https://github.com/InteractiveAdvertisingBureau/Attribution-Use-Cases/blob/main/Attribution%20Use%20Cases%20v1.md#table-of-contents)
- [Overview](https://github.com/InteractiveAdvertisingBureau/Attribution-Use-Cases/blob/main/Attribution%20Use%20Cases%20v1.md#overview-1)
  - [Reporting Dimensions](https://github.com/InteractiveAdvertisingBureau/Attribution-Use-Cases/blob/main/Attribution%20Use%20Cases%20v1.md#reporting-dimensions)
  - [Event-Level Processing](https://github.com/InteractiveAdvertisingBureau/Attribution-Use-Cases/blob/main/Attribution%20Use%20Cases%20v1.md#event-level-processing)
  - [Complex Attribution Models](https://github.com/InteractiveAdvertisingBureau/Attribution-Use-Cases/blob/main/Attribution%20Use%20Cases%20v1.md#complex-attribution-models)
    - [Multi-touch Attribution](https://github.com/InteractiveAdvertisingBureau/Attribution-Use-Cases/blob/main/Attribution%20Use%20Cases%20v1.md#multi-touch-attribution)
    - [Measure Multiple Conversions from Multiple Ads](https://github.com/InteractiveAdvertisingBureau/Attribution-Use-Cases/blob/main/Attribution%20Use%20Cases%20v1.md#measure-multiple-conversions-from-multiple-ads)
  - [Measure IVT Conversions](https://github.com/InteractiveAdvertisingBureau/Attribution-Use-Cases/blob/main/Attribution%20Use%20Cases%20v1.md#measure-ivt-conversions)
  - [App-to-Web / Web-to-App Attributions](https://github.com/InteractiveAdvertisingBureau/Attribution-Use-Cases/blob/main/Attribution%20Use%20Cases%20v1.md#app-to-web--web-to-app-attributions)


## Overview

Below we explore some important use cases deemed necessary by industry members. These features are important to make any attribution system useful and support the industry’s requirements.

The following use cases would fall into one or more of these pillars:

- Flexible Extensive Reporting Dimensions
- Flexible Custom Attribution Models
- IVT/Fraud Detection
- Novel Features

### Reporting Dimensions

As an advertiser, be able to label a conversion with different reporting dimensions to merge with impression reports.

These dimensions can be rolled up and aggregated and are not expected to be event level. Timestamp for example may be truncated based on the requested report.

Note that these dimensions are typically labeled on the impression side via macros.

| Dimension |
| -------------- |
| Timestamp |
| Source |
| Seat ID |
| Deal ID |
| Advertiser ID |
| Campaign ID |
| Advertisement ID |
| Creative ID |
| Line Item ID |
| Exchange ID |
| Publisher ID |
| Domain |
| Page URL |
| App Name |
| Device Type |
| Make |
| Model |
| OS |
| OS Version |
| City |
| Region |
| Country |
| Postal Code |


The table above is just an example on the types of dimensions an advertiser would want to generate reports for. This list is not meant to be exhaustive and the attribution system should allow the advertiser to label an impression/conversion with as many reporting dimensions as they would like. Within the limits of storage, network, and memory of the browser.

Advertisers need to run multiple reports and slice and dice their data as needed by multiple reporting dimensions. It is not viable for an advertiser to define a single set of reporting dimensions they want a report for ahead of time. Advertisers need to be able to generate reports for themselves and their clients as needed.

The ability to receive the current attribution report should not be impaired by an error in attempting to get the previous report.

The report requester will utilize key dimensions (e.g. campaign id, creative id, etc) to resolve joining table information such as campaign dates, creative dimensions, etc.

### Event-Level Processing

Ability to combine exposure and action event logs with conversion event logs.

Advertisers should be able to evaluate a set of exposure and conversion events to implement their own custom and complex attribution models, some which are outlined below.

Event logs can be shipped off to a TEE or similar Data Clean Room environment. The exposure and conversion events should be joinable either via a reference id (for example an advertisement id, ip, etc). The power of being able to ship events with a joinable identifier is that these events can then be joined with publisher (or other party) provided events for reconciliation, dispute resolution, and debugging.

Alternatively, the event logs can be processed locally within the user agent within a secure worklet environment in which aggregatable signals can be generated during processing (similar to Shared Storage).

### Complex Attribution Models

As outlined above, it is important for advertisers to be able to define and program their own attribution models. For many agencies these models can vary campaign by campaign. It is not feasible for a browser to implement these complex models and advertisers don’t want to wait for browsers to update their systems for new models.

Below is an example of some popular more complex attribution models. However, there are many more and that is why attribution systems need to:

#### Multi-touch Attribution

As a Brand I want to know the relative contribution of prior ad exposures across publishers’ ad Inventory.

The ability to attribute conversions to multiple publishers and sites and determining the percentage of the attribution should be distributed to each publisher.

Ability to define custom attribution models which can take multiple publishers into consideration for attribution computation and reporting.

The core use case is for advertisers to define their own complex and custom attribution models.

#### Measure Multiple Conversions from Multiple Ads

As an Advertiser I want to measure attribution when I advertise multiple brands that convert on the same domain.

As an Advertiser, I want to measure attributed measurement independent of, and without influence from, other advertisers or brands converting on the same eTLD+1 domain.


An Advertiser would not want their measurement fidelity impacted by other Advertisers or brands. This use case would include scenarios of multiple brands, product lines, or cohorts of users advertising on a common ecommerce site as well as a multi-brand company converting multiple brands they own on their own sites.

Simple example: a user may see 3 different brands in various places (in the attribution time window the DSP is setting), that all lead to the same eTLD+1 domain (e.g Amazon). There should be an ability to count 3 conversions ideally, rather than just 1.

- Limits to a domain can be limiting for larger brands that have many sub-brands. E.g. adidas has distinct sub brands with different cohorts (fashion, high fashion, etc)
- About understanding quotas and rate-limits. Because of privacy limits there will be some sort of partitioning. There should be a way for brands to participate in this system and domains is not the right way to partition it. A way for brands to establish their own partitions (e.g. similar to have a group of domains can be owned by a single publisher)
- A solution to 100, 1K, 1M advertisers to the same domain and maintains the same level of attributed measurement coverage and accuracy - and is unaffected by the number of external advertisers or owned sub-brand/product line campaigns converting on the same destination. It is reasonable for privacy protection for an advertiser to have to make tradeoffs within their control on the granularity and number of campaigns deployed. However it is not reasonable for the advertiser’s attributed measurement to be affected by the number of external advertisers or the number of their own sub-brands or product lines converting on the same domain.

### Measure IVT Conversions

As an advertiser, I want to know if a certain conversion was activated from a data center, headless browser, bot, etc.

It is important to distinguish that an impression may have occurred legitimately but the conversion was triggered by [IVT](https://www.iab.com/guidelines/mrc-invalid-traffic-ivt-detection-and-filtration-guidelines-addendum/).

Ability for flexibility in detecting and updating detection models and not having to wait to react to new threat models or information.

Ability to examine historical data to flag invalid traffic based on previous observations.

Critically determine if activity is being driven in a data center or synthetic browser.

Determine if a conversion was driven by an agent the user authorized.

Signals that indicate that conversions (and associated exposure) come from human traffic.


This feature could be provided by related standards such as PRIVACY-PASS or Private State Tokens but there needs to be clear guidance on how advertisers can determine validity of conversion signals.

### App-to-Web / Web-to-App Attributions

Advertisers want to be able to display ads on a website and determine if a subsequent action (e.g. purchase) on a native application was driven by that specific ad’s impression or click.

Advertisers want to be able to display ads on a native application and determine if a subsequent action (e.g. purchase) on a website was driven by that specific ad’s impression or click.

