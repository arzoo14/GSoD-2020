### Introduction

As GSoD 2020 has come to an end, this is my project report (final work product) wrapping up all the work done during this journey.

### What is Performance Co-Pilot?

Performance Co-Pilot (PCP) provides a framework and services to support system-level performance monitoring and management. It presents a unifying abstraction for all of the performance data in a system, and many tools for interrogating, retrieving and processing that data.

PCP is a feature-rich, mature, extensible, cross-platform toolkit supporting both live and retrospective analysis. The distributed PCP architecture makes it especially useful for those seeking centralized monitoring of distributed processing.

### Project's Abstract

A community website plays an essential role in an open-source organization because it spreads the idea of offerings that the community provides, their precious contributions, their skills, their documentations, their tutorials, etc. So, my project will aim to increase the usability and easiness for all the open-source contributors by transferring and updating the book project areas content, i.e., docbook content, REST API documentation and pbench markdown content to reStructuredText format such that it can be hosted on the modern, community readthedocs.io site. This project will also benefit the community contributors by allowing them to change and extend this content more easily. As well as, as a stretch goal, the diagrams in the documentation will be improved to give them a more professional look.

### GSoD 2020

As a part of GSoD 2020, my project had following deliverables:
 
  1. Converting docbook content to reStructuredText format and hosting it on readthedocs site.
  2. Converting REST API documentation from manpage to developer-friendly format, i.e., reStructuredText format and hosting it on readthedocs site.
  3. Converting pbench MarkDown content to reStructuredText format and hosting it on readthedocs site.
  4. Stretch goals would be to improve the diagrams present in the documentation.
  5. After the first deliverable, an additional Stretch Goal is added - Addition of **pmseries(1)** chapter in the PCP User's and Administrator's Guide book.
  
As a part of GSoD 2020, I completed all the deliverables on time. Details of my work are as follows:

#### Deliverable 1

During this phase, I kick-started with setting up the basic sphinx configuration for the PCP books documentation. After that, I started with the conversion of the PCP User's and Administrator's Guide (UAG) and Programmer's Guide (PG) books from docbook to reStructured Text (rst) format. On completion of both the books, I cross-referenced the headings to each other and hyperlinked the tags. In the end, after the removal of all the errors and the review from the mentors, they were hosted on modern, community readthedocs site.

So, during Phase 1, I completed the following deliverables: 
 
  * Converted PCP UAG book to rst format.  
  * Converted PCP PG book to rst format.  
  * Hosted both of them on readthedocs site.  
  
Code - [PR #1060](https://github.com/performancecopilot/pcp/pull/1060), [PR #1076](https://github.com/performancecopilot/pcp/pull/1076)  
Final Deliverable - [PCP Books](https://pcp.readthedocs.io/en/latest/)

#### Deliverable 2

During this phase, I learnt a lot of new things. I have to convert REST API documentation from manpage to developer-friendly format, i.e., reStructuredText format in this phase. My mentor suggested me a new tool for API Documentation - **Swagger**. It was completely new to me. I was just full of questions like how to integrate Swagger with readthedocs, how to give multiple responses for a single API, how to write YAML and so on. My mentor [Andreas Gerstmayr](https://github.com/andreasgerstmayr) helped me in solving all the questions. With the help of [sphinxcontrib-redoc](https://sphinxcontrib-redoc.readthedocs.io/en/stable/#), I integrated Swagger with readthedocs and learnt YAML in no time. Finally, I wrote the REST API documentation in OpenAPI 3.0 (fka Swagger) and hosted them on readthedocs site.

So, during Phase 2, I completed the following deliverables: 
 
  * Converted REST API documentation from manpage to rst format. 
  * Hosted REST API Guide on readthedocs.
  
 Code - [PR #1117](https://github.com/performancecopilot/pcp/pull/1117), [PR #1119](https://github.com/performancecopilot/pcp/pull/1119), [PR #1139](https://github.com/performancecopilot/pcp/pull/1139)  
 Final Deliverable - [REST API Guide](https://pcp.readthedocs.io/en/latest/api/)
 
#### Deliverable 3

During this phase, I started with setting up the basic sphinx configuration for the Pbench guides. After that, I converted pbench guide from the MarkDown (md) format to rst format. In this phase, I learnt many new sphinx extensions. One of them being - sphinx-panels, which I used in this project to give dropdown card effect to the headings. 
 The code associated with this deliverable is still under review. The mentor has shown his satisfaction with the work and commented with 'Looks Good'. The readthedocs site needed the hosting of this documentation is already setup. Once, the PR will be merged, the documentation can be found [here](https://pbench.readthedocs.io/en/latest/). 
 
 So, during Phase 3, I completed the following deliverable: 
 
  * Converted Pbench guide from md to rst format. 
  
Code - [PR #1963](https://github.com/distributed-system-analysis/pbench/pull/1963)

#### Deliverable 4

Commencement of Stretch Goals. In this phase, I improved all the diagrams present in the PCP UAG and PG book with the help of [draw.io](https://www.draw.io/). Improvement in the diagrams incorporates the following:

 1. Shadow of the shapes.
 2. Color/font as per pcp.io website.
 3. Proper Scaling.
 4. Consistency (same font, same font size, same color palette, same size of the shapes) throughout the figures.
 5. Improvements in arrow heads.
 
 So, during Phase 4, I completed the following deliverables: 
 
  * Improved PCP UAG book diagrams.
  * Improved PCP PG book diagrams.
  
Code - [PR #1142](https://github.com/performancecopilot/pcp/pull/1142), [PR #1154](https://github.com/performancecopilot/pcp/pull/1154)  
Final Deliverable - Diagrams present in [PCP Books](https://pcp.readthedocs.io/en/latest/). One such reference is [here](https://pcp.readthedocs.io/en/latest/UAG/PcpDeploymentStrategies.html#figure-7-4-pcp-deployment-to-measure-client-server-quality-of-service).

#### Deliverable 5

After the deliverable 1, I added an another stretch goal in my timeline. The stretch goal was - Addition of **pmseries(1)** chapter in the PCP User's and Administrator's Guide book. So, I completed this stretch goal in the last week of my GSoD period. And after the completion of all the deliverables, I further improved the documentations by resolving the various bugs. 
 
 So, during Phase 5, I completed the following deliverables: 
 
  * Added the pmseries(1) chapter in the PCP UAG book.
  * Improved the documentation by:  
    * Removing typos and whitespaces.
    * Adding PCP icon to the docs.
    * wrapping the text of table cells.
    
Code - [PR #1147](https://github.com/performancecopilot/pcp/pull/1147), [PR #1161](https://github.com/performancecopilot/pcp/pull/1161), [PR #1162](https://github.com/performancecopilot/pcp/pull/1162)  
Final Deliverable - [pmseries(1)](https://pcp.readthedocs.io/en/latest/UAG/TimeSeriesQuerying.html)

### Post GSoD 2020

During the GSoD period, I discussed with my mentor regarding the one stand-alone documentation for Google Summer of Code (GSoC) and Google Season of Docs (GSoD) for the organization. It will contain everything related to a year - Proposal format, Ideas, Successful applicants proposal and their final works, Stats, Mentor Details, etc. Everything at a single 'Stop'. He has given consent for the same. So, after the GSoD period, I'll start with this.

 
### Additional Information and Resources

1. Mentoring Organization - [Performance Co-Pilot](https://pcp.io/)
2. Mentors - [Nathan Scott](https://github.com/natoscott), [Andreas Gerstmayr](https://github.com/andreasgerstmayr), [Peter Portante](https://github.com/portante)
3. [Project](https://developers.google.com/season-of-docs/docs/participants/project-pcp-arzoo14)
4. [Proposal](https://github.com/arzoo14/Google-Season-of-Docs-2020/blob/master/proposal.md)
5. Github Repositories - [PCP](https://github.com/performancecopilot/pcp), [Pbench](https://github.com/distributed-system-analysis/pbench)
6. [Merged PRs](https://github.com/performancecopilot/pcp/pulls?q=is%3Apr+author%3Aarzoo14+is%3Aclosed+is%3Amerged+), [Under Review PR](https://github.com/distributed-system-analysis/pbench/pull/1963)
7. [Final Work Product](https://pcp.readthedocs.io/en/latest/)

### EndNote

With this, the Google Season of Docs has come to an end. These three months have been very exciting, challenging and fun. During these three months, I learnt a lot of new things like Swagger, OpenAPI, Redoc, etc. Also, now rst format, md format and git are on my tips. I will definitely write some blogs on the Swagger-Sphinx collaboration. I have felt an immense improvement in my skills and would love to keep working with the Performance Co-Pilot organization and maybe even try for Google Season of Docs next year too. 

### Acknowledgements

I would like to express my sincere gratitude to my mentors - Nathan Scott and Andreas Gerstmayr for their constant support and guidance. They were always around and had solutions to any issue that I faced. I have learnt a lot from them and expect to learn a lot more in the future.

 I would also like to thank Peter Portante for his guidance on the pbench guides. I would continue with him on adding more content to the pbench guides. 
 
  I am grateful to Google and Performance Co-Pilot organization for giving me this golden opportunity.  
