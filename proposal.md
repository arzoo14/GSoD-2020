# GSoD 2020 Proposal (Performance Co-Pilot)

### Table of Contents  
[Proposal](#proposal)
[Timeline](#timeline)


**CONTACT INFORMATION**  
Name: Arzoo  
Github handle: arzoo14  
Email: arzoopprajapati11@gmail.com  
Phone: +91-9971718061  
Location: Noida, Uttar Pradesh, India (UTC+05:30)

**TITLE**  
Convert book project areas content to readthedocs and reStructuredText format along with the stretch goal of diagrams' improvement.

**ABSTRACT**  
A community website plays an essential role in an open-source organization because it spreads the idea of offerings that the community provides, their precious contributions, their skills, their documentations, their tutorials, etc. So, my project will aim to increase the usability and easiness for all the open-source contributors by transferring and updating the book project areas content, i.e., docbook content, REST API documentation and pbench markdown content to reStructuredText format such that it can be hosted on the modern, community readthedocs.io site. This project will also benefit the community contributors by allowing them to change and extend this content more easily. As well as, as a stretch goal, the diagrams in the documentation will be improved to give them a more professional look.

## PROPOSAL

**1.  OVERVIEW**  
The Performance Co-Pilot documentation currently exists in several different formats. These include PCP books in docbook format, REST API in manpage format, and pbench guides in markdown format. So, the organization’s current maintainer group identified that they need a solution that is as maintenance-free as possible, and that allows the developer community to be entirely focused on maintaining its content in a streamlined and easy way.  

So, according to the current needs of the organization, I will implement the following goals during this Google Season of Docs:  
1. Converting docbook content to reStructuredText format and hosting it on readthedocs site.
2. Converting REST API documentation from manpage to developer-friendly format, i.e., reStructuredText format and hosting it on readthedocs site.
3. Converting pbench MarkDown content to reStructuredText format and hosting it on readthedocs site.
4. Stretch goals would be to improve the diagrams present in the documentation.

**2. IMPLEMENTATION**  
Currently, the Performance Co-Pilot documentation is not present in a specific format. Whenever the content of the documentation needs to be changed, it needs to be changed by a restricted set of users. It is not that easy for the active community members to change and extend the documentation’s content.  

I will let the organization overcome these limitations during this GSoD with the help of reStructuredText format, Read the Docs (RTD), and Sphinx.  

Read the Docs (RTD) simplifies software documentation by automating building, versioning, and hosting our docs for us. It is a hosting platform for Sphinx-generated documentation. It takes the power of Sphinx and adds version control, full-text search, and other useful features. It pulls down code and doc files from Git, Mercurial, or Subversion, then builds and hosts our documentation. We’ll use GitHub in our project as it’s the most commonly used system for accessing code.  

To get started, we’ll create a Read the Docs account, and link the GitHub account. Then we’ll select the GitHub repository we’d like to build documentation for, at which point the magic happens.  

Read the Docs will:  
* Clone our repository.
* Build HTML, PDF, and ePub versions of our documentation from our master branch.
* Index our documentation to allow full-text-search.
* Create Version objects from each tag and branch in our repository, allowing us to host those as well optionally.
* Activate a webhook on our repository, so when we push code to any branch, our documentation is rebuilt.  
 
Sphinx is an authoritative documentation generator that has many great features for writing technical documentation, including:  
* Generate web pages, printable PDFs, documents for e-readers (ePub), and more all from the same sources.
* We can use reStructuredText to write documentation.
* An extensive system of cross-referencing code and documentation.
* Syntax highlighted code samples.
* A vibrant ecosystem of first and third-party extensions.  

I will start with converting the two PCP books which are present in docbook format to rst format, following the conversion of REST API documentation from man page format to rst format, then conversion of pbench markdown content to rst format and in the end, hosting all of these on the readthedocs site. The stretch goals would be to improve the diagrams in the documentation.

**I. Conversion to reStructuredText format**  
The first step will be to convert the documentation content into reStructuredText format. Each chapter will have a separate rst file, which will contain the content of that chapter only. For example, Performance Co-Pilot User's and Administrator's Guide book include eight chapters. It means there will be eight different rst files corresponding to those eight chapters. The name of the rst file will be the same as the chapter name to avoid any confusion in the future. A list of figures, tables, and lists of examples will be there in three different rst files. The rst content will be thoroughly hyperlinked in the same way it is currently present. The same thing will be used for the REST API documentation and pbench content.   
All the necessary things, such as bold, italic, underline, bullet points, tables, font size, code-style, image size, alignment, etc., will be taken care of while converting the contents into rst format.  

**II. Integration of rst with Sphinx**  
```  
Note: 
The name of the project will be named only after the discussion with the mentors and community members. Also, whether there will be a single website for 
hosting all the three topics or three different websites corresponding to the three topics will be according to mentors' and community members' consent.    
In this proposal, I am using ‘Performance Co-Pilot Documentation’ as the name of the project.    
```

ReadtheDocs uses Sphinx and reStructuredText (rst) as defaults. As Sphinx is pre-installed in my system, I will start with creating a directory inside the project (named as Performance Co-Pilot Documentation) to hold the docs:  
```
$ cd /path/to/project  
$ mkdir docs  
```

After that, running `sphinx-quickstart` in there:  
```
$ cd docs  
$ sphinx-quickstart  
```
 
This quick start will walk through creating the necessary configuration; in most cases, we can just accept the defaults (but when required, we can make the essential changes in the configuration file). When it’s done, we’ll have an `index.rst`, a `conf.py`, and some other files.  
In index.rst, I will add all the necessary details about the Performance Co-Pilot and will create headings for both the books, REST API documentation, and pbench guides. When the user will click any of the headings, it will open up all the documentation materials under that heading.  
 
```
NOTE:  
The design of the index page will be according to the mentors' and community members' consent and will be changed according to the needs and requirements.  
```
 
The index.rst will be built into index.html in our documentation output directory (typically `_build/html/index.html`). Once we have Sphinx documentation in a public repository, we can start using Read the Docs by importing our docs.  

The conf.py file will be as follows: 
 
```
# -- Project information
project = 'Performance Co-Pilot Documentation'
copyright = '2020, Arzoo'
author = 'Arzoo'
master_doc = 'index'

# -- General configuration
extensions = [ ]
templates_path = ['_templates']

# List of patterns, relative to the source directory, that match files and directories to ignore when looking for source files.
# This pattern also affects html_static_path and html_extra_path.
exclude_patterns = ['_build', 'Thumbs.db', '.DS_Store']


# -- Options for HTML output 
html_theme_options = {
    'canonical_url': '',
    'analytics_id': 'UA-XXXXXXX-1', 
    'logo_only': False,
    'display_version': True,
    'prev_next_buttons_location': 'bottom',
    'style_external_links': False,
    'style_nav_header_background': 'dark blue',
    # Toc options
    'collapse_navigation': True,
    'sticky_navigation': True,
    'navigation_depth': -1,
    'includehidden': False,
    'titles_only': False
}

# The theme to use for HTML and HTML Help pages.
html_theme = 'sphinx_rtd_theme'

# Add any paths that contain custom static files (such as style sheets) here, relative to this directory.
html_static_path = ['_static']

# Custom sidebar templates must be a dictionary that maps document names to template names.
html_sidebars = {
    '**': [
        'about.html',
        'navigation.html',
        'relations.html',  
        'searchbox.html',
        'donate.html',
    ]
}  
```

When we’ll add any .rst file in our documentation, then corresponding to that file, three other files will be generated, one in doctrees folder with .doctree extension, second in Html folder with .html extension, and the third one in html/_sources folder with .rst.txt extension.  
 
I will also add the search functionality in the index page for searching any content from its name. I will use JavaScript to implement this search functionality.  
 
**3. HOSTING THE DOCUMENTATION**  
Hosting of documentation on the internet consists of two steps:  
1. Importing the documentation  
As a first step, I will connect the Read The Docs account with Github and import our documentation project to build.  
2. Building the documentation  
Within a few seconds of completing the import process, the code will automatically be fetched from our public repository, and the documentation will be built.  
 
**4. WEBHOOKS**  
The primary method that Read the Docs uses to detect changes to the documentation and versions is through the use of webhooks. Webhooks are configured with our repository provider, such as GitHub, and with each commit, merge, or other change to our repository, Read the Docs is notified. When we receive a webhook notification, we determine if the change is related to an active version for our project, and if it is, a build is triggered for that version.  
 
In this way, anyone (admins, mentors, community contributors) can change, extend or maintain the community documentation, and no particular restricted set of users will be needed to take care of what should be added to the documentation or what should be removed from the documentation.  
 
**5. THEMES**  
Themes, layouts, designs, and other HTML functionalities like search will be as per community needs and guidelines. In the community bonding period, I will discuss all these with the community members.  

``` 
Note:  
All the work will start from basic and will be there in a separate repository named Performance Co-Pilot Documentation.  
```
 
**6. STRETCH GOAL**  
As a stretch goal, I will improve the diagrams present in the documentation. Currently, the diagrams are mostly simple black-and-white drawings. I will introduce more color, shading, scaling, consistency, and a generally neater / more professional look to the images.  

To serve this purpose, I will use draw.io (or any other tool with the consent of the mentor).  

As a Proof of Concept, I have improved one of the diagrams present in the documentation with the help of draw.io.  

## PROOF OF CONCEPT  
 
I have converted a small part of the PCP book (docbook format) into the rst format and hosted it on the readthedocs site. Please find it here.  
 
Website - [https://pcp-books.readthedocs.io/en/latest/](https://pcp-books.readthedocs.io/en/latest/)  
Code - [ https://github.com/arzoo14/PCP_Books_Demo ]( https://github.com/arzoo14/PCP_Books_Demo ) 
 
I have also configured webhooks in the code repository with the help of which, the changes made in the code repository will get reflected in the website.  
 
Contributions to the Performance Co-Pilot Organization:  
 
**Merged [PR #53]** : Improvements in documentation  

## TIMELINE
 
### COMMUNITY BONDING PERIOD [ August 17 - September 13, 2020 ]  

I will spend this time familiarizing myself with the community, going through the documentation, and discussing many things with the mentors to make sure no bad decisions are made early in the process. I will discuss the themes, layouts, designs, other functionalities like search, navigation bar, etc. with the mentors and the community members during this period. The decision for the name of the project and whether there will be a single website for hosting all three topics or three different websites corresponding to the three topics will be discussed during the community bonding period.  

### DOC DEVELOPMENT PERIOD [ September 14 - November 30, 2020 ]  

 
FROM | TO | WEEK | DELIVERABLES 
:---: | :---: | :---: | --- 
September 14, 2020 | September 20, 2020 | 1 | Conversion of docbook content into rst format for the first four chapters of the Users and Administrators Guide book.   
September 21, 2020 | September 27, 2020 | 2 | Conversion of the docbook content into rst format for the next four chapters of the Users and Administrators Guide book.  
September 28, 2020 | October 4, 2020 | 3 | Conversion of the docbook content into rst format for all the four chapters of the Programmer's Guide book.  
October 5, 2020 | October 11, 2020 | 4 |  1. Hosting of both the PCP books on the readthedocs site. <br/>  2. Conversion of the REST API documentation from man page to rst format. The main landing page will be covered during this period.  <br/> 3. Blogging (of my GSoD project) for the last three weeks and the current week.  
October 12, 2020 | October 18, 2020 | 5 | Conversion of Scalable Time Series index into rst format. Scalable Time Series index covers the following: <br/> 1. GET /series/query <br/> 2. GET /series/values <br/> 3. GET /series/descs  <br/> 4. GET /series/labels <br/> 5. GET /series/metrics  <br/> 6. GET /series/sources <br/> 7. GET /series/instances  <br/> 8. GET /series/load  
October 19, 2020 | October 25, 2020 | 6 | Conversion of PMAPI Host Services index into rst format. PMAPI Host Services index covers the following: <br/> 1. GET /pmapi/context <br/> 2. GET /pmapi/metric <br/> 3. GET /pmapi/fetch  <br/> 4. GET /pmapi/children <br/> 5. GET /pmapi/indom <br/> 6. GET /pmapi/profile  <br/> 7. GET /pmapi/store  <br/> 8. GET /pmapi/derive <br/> 9. GET /pmapi/metrics <br/> **I will need two days off this week, i.e., October 23 and 24 because of the great Indian festival - Durga Puja.**  
October 26, 2020 | November 1, 2020 | 7 | 1. If anything is left in the last weeks, that will be covered first. <br/> 2. Hosting of REST API documentation on the readthedocs site. <br/> 3. Blogging (of my GSoD project) for the last two weeks and the current week.  
November 2, 2020 | November 8, 2020 | 8 | Conversion of the markdown content into rst format for the pbench guides.  
November 9, 2020 | November 15, 2020 | 9 | 1. Continued with the conversion of the markdown content into rst format for the pbench guides. <br/> 2. Hosting of the pbench guides on the readthedocs site. <br/> 3. Blogging (of my GSoD project) for the last week and the current week.  
November 16, 2020 | November 22, 2020 | 10 | 1. Implementation of the search functionality in the index page for searching any content from its name in the website(s). <br/> 2. Commencement of stretch goals.  
November 23, 2020 | November 30, 2020 | 11 | 1. Improvement of all the diagrams present in the documentation. <br/> 2. The final blogging (of my GSoD project) for the last and the current week. <br/> 3. Checking of whether the codebase is as per coding standards or not. If not, changing them to the standards.  
 
### PROJECT FINALIZATION PERIOD [ November 30 - December 5, 2020 ]  
 
* Pencil downtime. Working on the final submission and making sure that everything is okay.  
* Submission of the project reports, also known as final work products.  
* Submission of the evaluations of the success of the projects and the working experience with the mentors.  

## ADDITIONAL INFORMATION  
 
### EDUCATIONAL BACKGROUND  
I completed my senior secondary education from Nehru International Public School, Noida, Uttar Pradesh, India. Currently, I am a 5th-year undergraduate student pursuing my Dual Degree (B.Tech & M.Tech) in Computer Science and Engineering at the National Institute of Technology, Hamirpur, India.  
 
### HOBBIES  
Apart from coding, in the curricular field, I love learning about new technologies. I also have an interest in teaching, so I often help out my friends with the semester exams. Apart from this, I love reading non-fiction books and hanging out with my friends during weekends. I am a big fan of Anime, so watching them is one of my favorite hobbies. I like to play snooker and volleyball, which refreshes my mind and also enhances my overall personality. I am a proactive volunteer of GLUG (GNU/Linux User Group) of my college. Traveling is something that helps me in exploring different lifestyles.  
 
### WORKING HOURS  
I can devote my full time (45-50 hours per week) to the project.
 
### PERSONAL STATEMENT  
I believe I am a suitable candidate for this project and can lead to fruitful completion over the summer. I will be working on this full-time and will give weekly updates on the progress on the work.  
I have also studied technical writing courses during the application period to enhance my writing skills further.  
Working as a GSoD candidate on this project under the guidance of the accomplished Elixir mentors will be a great learning experience for me and will improve my technical writing abilities manifold. I am positive some constructive work will be done as a result.  
Not only clearing GSoD is my ultimate goal, but also I want to be in the good books of the organization. Moreover, I want to earn the membership of the Performance Co-Pilot community by continuously contributing even after the GSoD period.  
