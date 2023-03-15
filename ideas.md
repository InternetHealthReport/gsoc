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

If there is no specific contact given you can ask questions at admin@ihr.live.

## List of ideas

### Integration of Google transparency reports

**Brief explanation:** Google discloses traffic levels per countries 
(see https://transparencyreport.google.com/traffic/). 
The goal of this project is to show this data on IHR, so that user can estimate 
the impact of events observed on IHR to traffic changes to popular Internet services.

**Expected results:**
- Survey of Google transparency reports
- Implementation of a visualization widget for multiple datasets provided by Google
- Integration to IHR country reports
- (optional) Implementation of a backend anomaly detector to complement IHR alerting system

**Knowledge Prerequisite:** Javascript, python, VueJS 

**Resources:**
- https://github.com/InternetHealthReport/ihr-website
- https://transparencyreport.google.com/traffic/

**Project size:** 175 hours 

**Difficulty:** Easy/Medium

**Contact:** Anant Shah (anant.shah@edgecast.com), Romain Fontugne (romain@iij.ad.jp)

-----------------------------------
### Network dependency visualization

**Brief explanation:** IHR monitors the inter-dependence of networks (e.g. the 
university of Tokyo relies on Japan national academic ISP) and displays these
dependencies with very simple line charts that highlights changes over time.
Representing this data as a graph is more intuitive for network operators. 
Each node is an AS and dependencies are links. This graph can also be annotated
with other metrics reported by IHR, for example, latency.
Related to this project, we have an offline tool that shows network dependencies 
for a country, this is also something we'd like to implement on IHR website
(https://github.com/InternetHealthReport/country-as-hegemony-viz).

**Expected results:**
- Create a VueJS component that show the dependency graph
- Add mechanisms to display changes over time
- Annotate the graph with other metrics and external datasets

**Knowledge Prerequisite:** Javascript, VueJS, and visualization library (i.e. Plotly or D3.js)

**Resources:**
- https://github.com/InternetHealthReport/ihr-website
- https://www.iijlab.net/en/members/romain/pdf/romain_pam2018.pdf
- https://github.com/InternetHealthReport/country-as-hegemony-viz

**Project size:** 175 hours 

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

**Resources:**
- https://github.com/InternetHealthReport/ihr-website
- https://ihr.iijlab.net/ihr/en-us/global_report

**Project size:** 350 hours

**Difficulty:** Medium / Hard

**Contact:** Emile Aben (emile.aben@ripe.net), Romain Fontugne (romain@iij.ad.jp)


-----------------------------------
### User management and notifications (continuation of GSoC'22)

**Brief explanation:** As part of GSoC'22, a basic user management has been
implemented in IHR front and backend. The users should be able to
input a list of networks and country they are interested in so that IHR can send
them personalized alerts when disruptions or important routing changes
happen. This code requires some more polishing/testing to be deployed on the IHR website. 
It also lacks a way to send notification to the users. We'd like to give different 
options to communicate with the users (email, slack, discord, etc...).

**Expected results:**
- Testing/improving existing code
    - https://github.com/InternetHealthReport/ihr-website/tree/user-mngt
    - https://github.com/InternetHealthReport/ihr-django
- Add ways to choose a communication channel (email, slack, etc...)
- Send notification (email, slack, etc...)

**Knowledge Prerequisite:** python, django, javascript, VueJS

**Resources:**
- https://github.com/InternetHealthReport/ihr-website
- https://github.com/InternetHealthReport/ihr-django

**Project size:** 175 hours

**Difficulty:** Easy/Medium

**Contact:** Romain Fontugne (romain@iij.ad.jp)

-----------------------------------
### Search page for the Internet Yellow Pages

**Brief explanation:** The Internet Yellow Pages 
(IYP: https://github.com/InternetHealthReport/internet-yellow-pages) is a
knowledge graph for network resources. The goal of this GSoC project is to 
create a web page for searching information in this knowledge graph. 
For example, the user enters a network's ASN, then the page query IYP for that 
network and display all related information.

**Expected results:**
- Add basic functions to query IYP (neo4j) from IHR website code
- Templates to show information related to a ASN, IP address, IP prefix, domain 
name, country, IXP. 
- (optional) Simple widget to show on IHR network and country pages

**Knowledge Prerequisite:** javascript, VueJS, Neo4j/Cypher

**Resources:**
- https://github.com/InternetHealthReport/ihr-website
- https://github.com/InternetHealthReport/internet-yellow-pages

**Project size:** 175 hours to 350 hours (depending on the number of templates)

**Difficulty:** Medium

**Contact:** Romain Fontugne (romain@iij.ad.jp),  Emile Aben (emile.aben@ripe.net) 

-----------------------------------
### IHR exploratory dashboard (continuation of GSoC'22)

**Brief explanation:** To show the impact of events on Internet performances we usually 
have to monitor multiple metrics at different periods of time. For example, to measure
the impact of national lockdowns during the outbreak of COVID19 we designed this dashboard:
https://ihr.iijlab.net/ihr/en-us/covid19?country=France
The goal of this project is to create a more flexible dashboard that allow a user to explore
IHR dataset and monitor any event. For this the implemented dashboard would let the user 
select a set of source and destination networks (or cities), time periods, and a metric (e.g. RTT).
Then it would plot the corresponding data. Depending on the contributor's ability a lot of
features can be added to this dashboard. For example, an assistant to select a set of 
important networks from a selected country, or global statistics about plotted data.

The main framework behind this dashboard has been implemented during GSoC'22 
(see https://github.com/InternetHealthReport/ihr-website/tree/exploratory-dashboard), 
but it needs UI and features improvements to be integrated to IHR website.

**Expected results:**
- Flexible user input form
- Plots based on user's input
- Permanent links for sharing plots on social media
- (optional) Networks selection assistant
- (optional) Add statistics about plotted data

**Knowledge Prerequisite:** javascript, VueJS

**Resources:**
- https://github.com/InternetHealthReport/ihr-website (see the explratory-dashboard branch)
- https://ihr.iijlab.net/ihr/en-us/covid19

**Project size:** 175 hours for the basic implementation (350 hours for full-featured dashboard)

**Difficulty:** Medium

**Contact:** Romain Fontugne (romain@iij.ad.jp)

-----------------------------------
### Dockerize all IHR components

**Brief explanation:** The IHR backend is based on a lot of different analysis
modules, anomaly detectors, and scripts that produce data for our main database.
The goal of this project is to create docker images for all these components so
that each component can be easily move on our servers.

**Expected results:**
- A docker image for each IHR analysis module
- Documentation on how to use the containers

**Knowledge Prerequisite:** docker, python

**Resources:**
- https://github.com/InternetHealthReport/

**Contact:**  romain@iij.ad.jp


-----------------------------------

## Proposal template
### Project
If appropriate, screenshot or another image

**Brief explanation:**

**Expected results:**

**Knowledge Prerequisite:**

**Resources:**
- https://github.com/InternetHealthReport/

**Contact:**  (your name and email address for contact)

*Content based on [https://community.kde.org/GSoC](https://community.kde.org/GSoC) and available under [Creative Commons License SA 4.0](https://community.kde.org/KDE_Community_Wiki:Copyrights)*
