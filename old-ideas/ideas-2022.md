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

If there is no specific contact given you can ask questions at gsoc@ihr.live.

## List of ideas

### Visualization widgets for M-Lab data

**Brief explanation:** IHR website provides plots of Internet latency and routing
(network dependency) for networks (AS) and countries. The goal of the project
is to add new plots showing speed test data collected by the Measurement-Lab (M-Lab: https://www.measurementlab.net/),
so that users can monitor how disconnections and routing events impact throughput.
M-Lab provides an API (https://github.com/m-lab/stats-pipeline) to get aggregations
of their data.

**Expected results:**
- Map M-Lab's aggregations to IHR's ASN and countries 
- Create a VueJS component for each M-Lab metric (e.g. Throughtput, packet loss)
- Integration with IHR website
- (optional) Experienced contributor could add searching/comparing features

**Knowledge Prerequisite:** Javascript, VueJS, plotly.js

**Resources:**
- https://github.com/InternetHealthReport/ihr-website
- https://github.com/m-lab/stats-pipeline
- https://speed.measurementlab.net
- https://www.measurementlab.net/

**Project size:** 175 hours

**Difficulty:** Easy/Medium

**Mentors:** Anant Shah<sup>1</sup>, Romain Fontugne<sup>2</sup>

**Contact:** <sup>1</sup> anant.shah@edgecast.com, <sup>2</sup> gsoc@ihr.live

-----------------------------------
### Integration of transparency reports

**Brief explanation:** Certain services such as Google and Cloudflare disclose
traffic levels per countries (see https://transparencyreport.google.com/traffic/
and https://radar.cloudflare.com/ ). The goal of this project is to show this
data on IHR, so that user can estimate the impact of events observed on IHR to
traffic changes to popular Internet services.

**Expected results:**
- Survey of transparency reports
- Implementation of a visualization widget for multiple datasets
- Integration to IHR country reports
- (optional) Implementation of a backend anomaly detector to complement IHR alerting system

**Knowledge Prerequisite:** Javascript, python, VueJS 

**Resources:**
- https://github.com/InternetHealthReport/ihr-website
- https://transparencyreport.google.com/traffic/
- https://radar.cloudflare.com/ 

**Project size:** 175 hours or 350 hours

**Difficulty:** Medium

**Mentors:** Anant Shah<sup>1</sup>, Romain Fontugne<sup>2</sup>

**Contact:** <sup>1</sup> anant.shah@edgecast.com, <sup>2</sup> gsoc@ihr.live

-----------------------------------
### Network dependency visualization
If appropriate, screenshot or another image

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

**Project size:** 175 hours or 350 hours

**Difficulty:** Medium

**Mentors:** Romain Fontugne<sup>1</sup>

**Contact:** <sup>1</sup> gsoc@ihr.live


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

**Mentors:** Emile Aben<sup>1</sup>, Romain Fontugne<sup>2</sup>

**Contact:** <sup>1</sup> emile.aben@ripe.net, <sup>2</sup> gsoc@ihr.live


-----------------------------------
###  Reusable visualizations for Internet open datasets 

**Brief explanation:** Develop reusable building blocks for visual exploration 
of Internet data. The goal of this project is to provide open source code 
to browse open data sets (e.g. IHR, RIS/Routeviews and RIPE Atlas) that
researchers and network operators could easily adapt when investigating outages
or documenting networking events.

**Expected results:**
- Development of basic libraries to handle Internet data (BGP, traceroutes) in Observable
- Examples for monitoring popular open data sets such as RIPE Atlas, M-Lab
- Examples for a few selected past events (e.g. network outage, route leak, BGP hijack)
- Documentation

**Knowledge Prerequisite:** Javascript, d3, ObservableHQ 

**Resources:**
- https://observablehq.com/@emileaben/
- https://www.ripe.net/analyse/internet-measurements/routing-information-service-ris
- https://atlas.ripe.net/
- http://www.routeviews.org/routeviews/
- https://www.measurementlab.net/

**Project size:** 175 hours or 350 hours

**Difficulty:** Medium

**Mentors:** Emile Aben<sup>1</sup>

**Contact:** <sup>1</sup> emile.aben@ripe.net


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

**Resources:**
- https://github.com/InternetHealthReport/ihr-website
- https://github.com/InternetHealthReport/ihr-django

**Project size:** 175 hours

**Difficulty:** Easy/Medium

**Mentors:** Romain Fontugne<sup>1</sup>

**Contact:** <sup>1</sup> gsoc@ihr.live

-----------------------------------
### Integration of Internet Yellow Pages data

**Brief explanation:** The Internet Yellow Pages (IYP: http://iyp.iijlab.net) is an IHR
project that aims to maintaining a knowledge graph for network resources. The goal
of this GSoC project is to import and display IYP data for networks, IP prefixes, and 
countries monitored by IHR.

**Expected results:**
- Matching IHR monitored resources to IYP items
- Generic SPARQL queries for extracting relevant information about monitored resources
- Widgets on IHR website for displaying data related to a selected resource
- (optional) Simple interface to explore IYP knowlege graph

**Knowledge Prerequisite:** javascript, VueJS, SPARQL

**Resources:**
- https://github.com/InternetHealthReport/ihr-website
- http://iyp.iijlab.net/wiki/Main_Page
- https://www.mediawiki.org/wiki/Wikibase

**Project size:** 175 hours (350 hours if planning to add the browsing interface)

**Difficulty:** Easy/Medium

**Mentors:** Romain Fontugne<sup>1</sup>, Emile Aben<sup>2</sup>

**Contact:** <sup>1</sup> gsoc@ihr.live, <sup>2</sup> emile.aben@ripe.net

-----------------------------------
### Lightweight NDT speed test

**Brief explanation:** NDT (Network Diagnostic Tool) measurement tool that reports upload
and download speeds and latency metrics. This is one of the main tool used by the Measurement
Lab. The goal of this project is to improve NDT7 (https://github.com/m-lab/ndt7-js/)
to perform lightweight speed test using, for example, the technique proposed in https://www.usenix.org/system/files/nsdi21-yang-xinlei.pdf. 

**Expected results:**
- Make NDT more practical to measure high-speed links
- Tests more efficient for large infrastructures and devices with limited resources
- Measure time/bandwidth saving using lightweight tests for MLab

**Knowledge Prerequisite:** javascript

**Resources:**
- https://www.measurementlab.net/
- https://github.com/m-lab/ndt7-js/
- https://www.usenix.org/system/files/nsdi21-yang-xinlei.pdf

**Project size:** 350 hours

**Difficulty:** Medium/Hard

**Mentors:** Romain Fontugne<sup>1</sup>, Emile Aben<sup>2</sup>

**Contact:** <sup>1</sup> gsoc@ihr.live, <sup>2</sup> emile.aben@ripe.net

-----------------------------------
### Port link monitoring code to python3 and Kafka

**Brief explanation:** We have stopped our link monitoring code (https://github.com/InternetHealthReport/tartiflette)
because this code need to be updated to our current backend. That means porting the code
to python3 and fetching traceroute data from Kafka. This code is based on this research
paper: https://www.iijlab.net/en/members/romain/pdf/romain_imc2017.pdf

**Expected results:**
- Code ported to python3
- Data fetching from Kafka
- Unit tests / Documentation

**Knowledge Prerequisite:** python, Kafka

**Resources:**
- https://github.com/InternetHealthReport/tartiflette
- https://www.iijlab.net/en/members/romain/pdf/romain_imc2017.pdf

**Project size:** 175 hours

**Difficulty:** Medium

**Mentors:** Romain Fontugne<sup>1</sup>

**Contact:** <sup>1</sup> gsoc@ihr.live

-----------------------------------
### IHR exploratory dashboard

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

**Expected results:**
- Flexible user input form
- Plots based on user's input
- Permanent links for sharing plots on social media
- (optional) Networks selection assistant
- (optional) Add statistics about plotted data

**Knowledge Prerequisite:** javascript, VueJS

**Resources:**
- https://github.com/InternetHealthReport/ihr-website
- https://ihr.iijlab.net/ihr/en-us/covid19

**Project size:** 175 hours for the basic implementation (350 hours for full-featured dashboard)

**Difficulty:** Medium

**Mentors:** Romain Fontugne<sup>1</sup>

**Contact:** <sup>1</sup> gsoc@ihr.live

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
