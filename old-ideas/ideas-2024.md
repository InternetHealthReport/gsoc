# List of ideas for projects

## Information for Students

Make sure you have read the IHR [contributor handbook](./ihr-contributor-handbook.md)

The below ideas were contributed by current IHR contributors. They are sometimes vague or incomplete. 
If you wish to submit a proposal based on these ideas, feel free to ask question 
on related [github discussion thread](https://github.com/orgs/InternetHealthReport/discussions)
or contact the related person and find out more about these ideas.

Becoming accepted as a Google Summer of Code student is quite competitive. 
Accepted students typically have thoroughly researched the topic of their proposed project and have been in frequent contact with potential mentors. 
Simply copying and pasting an idea here will not work. 
On the other hand, creating a completely new idea without first consulting potential mentors rarely works.

Also keep in mind that these are just proposals, we are open to new ideas you might have!
Do you have an awesome idea you want to work on for IHR but that is not among the ideas below? 
That's cool. We love that! 
Please get in touch with a mentor early on and make sure your project is realistic and within the scope of IHR.

If there is no specific contact given you can ask questions on github, slack, or at admin@ihr.live.

## List of ideas

-----------------------------------
### Real-time BGP monitor

**Brief explanation:**
Network operators need to monitor the global reachability of their IP prefixes 
every time they update their routing policies, RPKI, or BGP announcements.
The goal of this project is to provide a monitoring dashboard on the IHR website 
to easily monitor how a prefix propagates on the Internet. This tool should get
a prefix (or list of prefixes or an ASN) from a user, optionnally the user can
select a list of RIS collectors and the maximum number of hops from the monitored
prefix to display. Then the user push a 'play' button. The tool connects to 
RIS Live with the corresponding parameters and displays the AS paths received.
It could be similar to [BGPlay](https://stat.ripe.net/widget/bgplay) but we'd like to  
show only nodes that are near the monitored prefix so the graphs are more readable.
A path should be replaced if a new path is advertised by the same peer.
We also would like to show line charts to reflect the changes over time.

**Expected results:**
- Simple UI for getting the parameters from the user (prefix, collectors, number of hops)
- Display RIS Live data in a graph with some annotations (e.g. ASN, BGP communities)
- Integration to IHR website
- (optional) show additional information about ASes using IYP 
- (optional) near realtime RPKI status using for example https://rpki.gin.ntt.net/api/export.json

**Github discussion:** https://github.com/orgs/InternetHealthReport/discussions/34

**Knowledge Prerequisite:** Basics of BGP, Javascript, VueJS, D3JS or other plotting library

**Resources:**
- https://ris-live.ripe.net/
- https://stat.ripe.net/widget/bgplay

**Project size:** 175 hours 

**Difficulty:** Medium

**Contact:** Romain Fontugne (romain@iij.ad.jp), Emile Aben (emile.aben@ripe.net), Dimitrios Giakatos (dimitrios@iij.ad.jp)

-----------------------------------
### IYP automatic deployment

**Brief explanation:** For the Internet Yellow Pages we compute every week a new 
database that we want to make publicly available as soon as possible. The goal 
of this project is to design and implement this automated deployment. This 
requires multiple tests that will ensure the integrity of the new database, 
automatically store the new database on a public repository, and hot swap databases.
Optionally we could keep older databases online, for example all databases for the 
past month.

**Expected results:**
- Design an easy to maintain automated pipeline that would be easy to maintain
- Implement unit tests for each of the IYP dataset
- Implement automatic deployment and hot swap of IYP databases
- (optional) Maintain multiple instances of the database

**Github discussion:** https://github.com/orgs/InternetHealthReport/discussions/35

**Knowledge Prerequisite:** Neo4j, python, docker

**Resources:**
- https://github.com/InternetHealthReport/internet-yellow-pages
- http://iyp.iijlab.net/

**Project size:** 175 hours 

**Difficulty:** Easy/Medium

**Contact:** Romain Fontugne (romain@iij.ad.jp), Malte Tashiro (malte@iij.ad.jp)

-----------------------------------
### Network topology overview

**Brief explanation:** IHR monitors the inter-dependence of networks (e.g. the 
university of Tokyo relies on Japan's academic ISP) and displays these
dependencies with very simple line charts that highlights changes over time.
Representing this data as a graph is more intuitive for network operators.
So the goal of this project is to show the connectivity of a network (aka AS) in
a simple graph.
Using data from the Internet Yellow Pages we can depict a very detailed view of
an AS, by finding all prefixes originated by the AS, fetching AS dependencies for
all these prefixes, grouping these prefixes based on their dependencies, and 
finally displaying an AS graph that shows how these prefixes are connected to the
Internet. Additional information for each AS/prefix can be displayed by querying
IYP.
Related to this project, we have an offline tool that shows network dependencies 
for a country, this is also something we'd like to implement on IHR website
(https://github.com/InternetHealthReport/country-as-hegemony-viz).

**Expected results:**
- Create a VueJS component that show the dependency graph
- Integrate this component in IHR network report
- (optional) Create similar views for a country or a single prefix

**Github discussion:** https://github.com/orgs/InternetHealthReport/discussions/36

**Knowledge Prerequisite:** Basics of BGP, Javascript, VueJS, and visualization library (i.e. Plotly or D3.js)

**Resources:**
- https://github.com/InternetHealthReport/ihr-website
- https://www.iijlab.net/en/members/romain/pdf/romain_pam2018.pdf
- https://github.com/InternetHealthReport/country-as-hegemony-viz

**Project size:** 175 hours or 350 hours

**Difficulty:** Medium

**Contact:** Romain Fontugne (romain@iij.ad.jp), Malte Tashiro (malte@iij.ad.jp), Dimitrios Giakatos (dimitrios@iij.ad.jp)

-----------------------------------
### Traceroute visualization

**Brief explanation:** Operators would like to have a better way to visualize 
latency increases in upstream networks. We have a lot of traceroute data from 
RIPE Atlas but we miss a good visualization to show traceroute details.
The goal of this project is to design and implement a page on IHR to visualize
traceroute results from RIPE Atlas.
There is some good tools to get inspired from ([tracemon](https://labs.ripe.net/author/massimo_candela/tracemon-network-debugging-made-easy/) and [thousand eyes path visualization](https://docs.thousandeyes.com/product-documentation/internet-and-wan-monitoring/viewing-data/getting-started-with-path-visualization),
having our own would be great so we can integrate it with other tools (e.g. IYP, AS Hegemony).

**Expected results:**
- Create a VueJS component that fetch traceroute results from RIPE Atlas
- Display the results in intuitive graphs, showing the IP paths and corresponding RTT values
- Integrate with IYP data 
- 
**Github discussion:** https://github.com/orgs/InternetHealthReport/discussions/21

**Knowledge Prerequisite:** Good understanding of traceroute, Javascript, VueJS, and visualization library (i.e. Plotly or D3.js)

**Resources:**
- https://github.com/InternetHealthReport/ihr-website
- https://atlas.ripe.net/
- https://labs.ripe.net/author/massimo_candela/tracemon-network-debugging-made-easy/

**Project size:** 175 hours or 350 hours

**Difficulty:** Medium to Hard

**Contact:** Romain Fontugne (romain@iij.ad.jp), Malte Tashiro (malte@iij.ad.jp)

-----------------------------------
### Dockerize all IHR components (continuation of GSoC'23)
 
**Brief explanation:** The IHR backend is based on a lot of different analysis
modules, anomaly detectors, and scripts that produce data for our main database.
The goal of this project is to create docker images for all these components so
that each component can be easily move on our servers.

**Expected results:**
- A docker image for each IHR analysis module
- Documentation on how to use the containers
- Orchestration and monitoring

**Knowledge Prerequisite:** docker, python

**Project size:** 175 hours 

**Resources:**
- https://github.com/InternetHealthReport/

**Contact:** Romain Fontugne (romain@iij.ad.jp), Anant Shah (ashah@edg.io)


-----------------------------------

## Proposal template
-----------------------------------
### Project
If appropriate, screenshot or another image

**Brief explanation:**

**Expected results:**

**Github discussion:** https://github.com/orgs/InternetHealthReport/discussions/

**Knowledge Prerequisite:**

**Resources:**
- https://github.com/InternetHealthReport/

**Project size:** 175 hours or 350 hours 

**Difficulty:** Easy / Medium / Hard

**Contact:**  (your name and email address for contact)


*Content based on [https://community.kde.org/GSoC](https://community.kde.org/GSoC) and available under [Creative Commons License SA 4.0](https://community.kde.org/KDE_Community_Wiki:Copyrights)*
