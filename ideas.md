# List of ideas for projects

## Information for Students

These ideas were contributed by current IHR contributors. They are sometimes vague or incomplete. 
If you wish to submit a proposal based on these ideas, you are urged to contact the related person 
and find out more about the particular suggestion you're looking at.

Becoming accepted as a Google Summer of Code student is quite competitive. 
Accepted students typically have thoroughly researched the topic of their proposed project and have been in frequent contact with potential mentors. 
Simply copying and pasting an idea here will not work. 
On the other hand, creating a completely new idea without first consulting potential mentors rarely works.

That said, these are just proposals, we are open to new ideas you might have!
Do you have an awesome idea you want to work on with IHR but that is not among the ideas below? 
That's cool. We love that! 
But please get in touch with a mentor early on and make sure your project is realistic and within the scope of IHR.

If there is no specific contact given you can ask questions at ihr-admin@iij-ii.co.jp.

## List of ideas

### Visualization widgets for M-Lab data

**Brief explanation:** IHR website provides plots of Internet latency and routing
(network dependency) for networks (AS) and countries. The goal of the project
is to add new plots showing speed test data collected by the Measurement-Lab (M-Lab),
so that users can monitor how disconnections and routing events impact throughput.
M-Lab provides an API (https://github.com/m-lab/stats-pipeline) to get aggregations
of their data.

**Expected results:**
- Map M-Lab's aggregations to IHR's ASN and countries 
- Create a VueJS component for each M-Lab metric (e.g. Throughtput, packet loss)
- Integration with IHR website
- (optional) Experienced contributor could add searching/comparing features

**Knowledge Prerequisite:** Javascript, VueJS, plotly.js

**Project size:** 175 hours

**Difficulty:** Easy/Medium

**Contact:** Anant Shah (anant.shah@edgecast.com), Romain Fontugne (romain@iij.ad.jp)

-----------------------------------
### Integration of transparency reports

**Brief explanation:** Certain services such as Google and Cloudflare disclose
traffic levels per countries (see https://transparencyreport.google.com/traffic/
and https://radar.cloudflare.com/ ). The goal of this project is to import this
data in IHR, so that user can estimate the impact of events observed on IHR to
traffic changes to popular Internet services.

**Expected results:**
- Survey of transparency reports
- Implementation of a visualization widget for multiple datasets
- Implementation of a simple anomaly detector to highlight important changes
- Integration to IHR country reports
- (optional) Implementation of a backend anomaly detector to complement IHR alerting system

**Knowledge Prerequisite:** Javascript, python, VueJS 

**Project size:** 175 hours or 350 hours

**Difficulty:** Medium

**Contact:** Anant Shah (anant.shah@edgecast.com), Romain Fontugne (romain@iij.ad.jp)

-----------------------------------
### Network dependency visualization
If appropriate, screenshot or another image

**Brief explanation:** IHR monitors the inter-dependence of networks (e.g. the 
university of Tokyo relies on Japan national academic ISP) and displays these
dependencies with very simple line charts that highlights changes over time.
Representing this data as a graph is more intuitive for network operators. 
Each node is an AS and dependencies are links. This graph can also be annotated
with other metrics reported by IHR, for example, latency.

**Expected results:**
- Create a VueJS component that show the dependency graph
- Add mechanisms to display changes over time
- Annotate the graph with other metrics and external datasets

**Knowledge Prerequisite:** Javascript, VueJS, and visualization library (i.e. Plotly or D3.js)

**Project size:** 175 hours or 350 hours

**Difficulty:** Medium

**Contact:** Romain Fontugne (romain@iij.ad.jp)


-----------------------------------
### Alarms correlation and aggregated reports

**Brief explanation:** IHR implements simple anomaly detectors to identify changes 
in monitored metrics. This results in a lot of alarms displayed as tables in IHR
global reports. The most important events usually generates numerous alarms
across multiple datasets. The goal of this project is to group topologically or 
geographically related alarms that happen at the same time and provide 
multi-dimensional reports.

**Expected results:**
- This can be either implemented as an online or offline tool
- For an online implementation we expect:
    - A JS module to analyze and aggregate alarms
    - A VueJS component to display aggregated alarms
    - Integration with IHR's global report
- For an offline implementation we expect:
    - More comprehensive anlysis of IHR alarms with the possibility to add alarms 
    from other tools (e.g. BGPAlerter)
    - Allow user to provide feedback about the importance of reported alarms
    - Simple machine learning to personnalized this alerting system

**Knowledge Prerequisite:** Javascript/Python, visualization library, networking basics 

**Project size:** 350 hours

**Difficulty:** Medium / Hard

**Contact:** Emile Aben (emile.aben@ripe.net), Romain Fontugne (romain@iij.ad.jp)


-----------------------------------
###  Reusable visualizations for Internet open datasets 

**Brief explanation:** Develop reusable building blocks for visual exploration 
of Internet data. The goal of this project is to provide open source code 
to browse open data sets (e.g. IHR, RIS/Routeviews and RIPE Atlas) that  
researchers and network operators could easily adapt when investigating events
or sharing results.

**Expected results:**
- Development of basic libraries to handle Internet data (BGP, traceroutes) in Observable
- Simple examples with open data sets
- Documentation

**Knowledge Prerequisite:** Javascript, d3, ObservableHQ 

**Project size:** 175 hours or 350 hours

**Difficulty:** Medium

**Contact:** Emile Aben (emile.aben@ripe.net) 


-----------------------------------
### User management and notifications

**Brief explanation:** IHR database already have tables to manage users, but 
the website lacks a proper user management system. The users should be able to
input a list of networks and country they are interested in so that IHR can send
them by email personalized alerts when disruptions or important routing changes
happen.

**Expected results:**
- Implement user registration process (front and backend)
- A view on IHR website for letting a user select resources and a level of verbosity
- Backend email alerting system

**Knowledge Prerequisite:** python, django, javascript, VueJS

**Project size:** 175 hours

**Difficulty:** Easy/Medium

**Contact:** Romain Fontugne (romain@iij.ad.jp)

-----------------------------------
### Integration of Internet Yellow Pages data

**Brief explanation:** The Internet Yellow Pages (http://iyp.iijlab.net) is an IHR
project that aims to maintaining a knowledge graph for network resources. The goal
of this GSoC project is to import and display IYP data for networks, IP prefixes, and 
countries monitored by IHR.

**Expected results:**
- Generic SPARQL queries for extracting relevant information about a network resources
- Widgets on IHR website for displaying data related to a selected resource
- (optional) Simple interface to browse IYP knowlege graph

**Knowledge Prerequisite:** javascript, VueJS, SPARQL

**Project size:** 175 hours

**Difficulty:** Easy

**Contact:** Romain Fontugne (romain@iij.ad.jp),  Emile Aben (emile.aben@ripe.net) 

-----------------------------------

## Proposal template
### Project
If appropriate, screenshot or another image

**Brief explanation:**

**Expected results:**

**Knowledge Prerequisite:**

**Contact:**  (your name and email address for contact)

*Content based on [https://community.kde.org/GSoC](https://community.kde.org/GSoC) and available under [Creative Commons License SA 4.0](https://community.kde.org/KDE_Community_Wiki:Copyrights)*
