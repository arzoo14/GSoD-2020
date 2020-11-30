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
  5. After the first deliverable, an additional Stretch Goal is added - Addtion of **pmseries(1)** chapter in the PCP User's and Administrator's Guide book.
  
As a part of GSoD 2020, I completed all the deliverables on time. Details of my work are as follows:

#### Deliverable 1

During this phase, I kickstarted with setting up the basic sphinx configuration for the PCP books documentation. After that, I started with the conversion of the PCP User's and Administrator's Guide (UAG) and Programmer's Guide (PG) books from docbook to reStructured Text (rst) format. On completion of both the books, I cross-referenced the headings to each other and hyperlinked the tags. In the end, after the removal of all the errors and the review from the mentors, they were hosted on modern, community readthedocs site.

So, during Phase 1, I completed the following deliverables:  

  a. Converted PCP UAG book to rst format.  
  b. Converted PCP PG book to rst format.  
  c. Hosted both of them on readthedocs site.  


