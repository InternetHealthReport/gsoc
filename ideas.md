# List of ideas for projects

## Information for Students

Make sure you have read the IHR [contributor handbook](./ihr-contributor-handbook.md)

The below ideas were contributed by current IHR contributors. They are sometimes
vague or incomplete.
Questions related to these ideas should be asked on the related [GitHub
discussion thread](https://github.com/orgs/InternetHealthReport/discussions).

Becoming accepted as a Google Summer of Code student is quite competitive.
Accepted students typically have thoroughly researched the topic of their
proposed project and have been active in the discussions.
Simply copying and pasting an idea here will not work.
On the other hand, creating a completely new idea without first consulting
potential mentors also rarely works.

Also keep in mind that these are just proposals, we are open to new ideas you
might have!
Do you have an awesome idea you want to work on for IHR, but that is not among
the ideas below?
That's cool. We love that!
Please get in touch with a mentor early on and make sure your project is
realistic and within the scope of IHR.

If there is no specific contact given you can ask questions on github, slack, or
at admin@ihr.live.

## List of ideas

-----------------------------------
### IHR Status Page

**Brief explanation:** Things breaks easily, so we need a status page that tells
us which services are running as usual and which one are not. This page could
also provide a machine-readable JSON object so that we can automate email alerts
when something is not running as usual. It would also be nice to keep historical
availability data.

We provide datasets in different formats (e.g., RUST API, files on an FTP
server), which need to be monitored. Thus, there can be different liveness
checks, e.g., that an API responds (and also gives results), that a file exists,
etc.

The project should use, or build on top of, an existing monitoring solution,
should be maintainable, and extendable if we add new datasets in the future.

**Expected results:**
- Find a suitable monitoring tool that can be used as a base for this project
- Implement a status page for all API endpoints and results, websites (ihr, ihr-archive,
  iyp), and the IYP database
- Add a machine-readable format of the page
- Automatic email notification when something is down

**Github discussion:** https://github.com/orgs/InternetHealthReport/discussions/51

**Knowledge Prerequisite:**
- Overview of the IHR ecosystem, see Resources below
- Docker
- Web development experience

**Resources:**
- https://github.com/InternetHealthReport/
- [IHR API](https://www.ihr.live/en/api)
- [IHR Archive](https://archive.ihr.live/)
- [IYP website](https://iyp.iijlab.net/)
- [IYP
  database](https://iyp.iijlab.net/iyp/browser/?dbms=iyp-bolt.iijlab.net:443)

**Project size:** 90 hours

**Difficulty:** Easy

**Contact:** Dimitrios Giakatos (dimitrios@iij.ad.jp), Malte Tashiro
(malte@iij.ad.jp), Romain Fontugne (romain@iij.ad.jp)

-----------------------------------
### Migrate IHR API

**Brief explanation:** All results displayed on the Internet Health Report website 
are accessible via the IHR REST API. The current codebase is developed on an outdated 
version of [Django (2.2.27)](https://docs.djangoproject.com/en/2.2/), which is no 
longer supported, and we are not utilizing all of Django's features. Therefore, 
instead of just upgrading the Django version, we plan to migrate the codebase 
from the complex Django framework to a simpler framework, such as [FastAPI](https://fastapi.tiangolo.com/). 
Additionally, the current Django framework includes code for initializing/managing 
the database. This time, we want to implement Bash scripts for initializing/managing 
the database, which will result in better maintenance.

**Expected results:**
- Migrate all Django endpoints to FastAPI
- Convert the database code from Django to Bash scripts
- Dockerize the application (excluding the Bash scripts, which will be run as is)

**Github discussion:** https://github.com/orgs/InternetHealthReport/discussions/58

**Knowledge Prerequisite:**
- Django (to understand the current codebase)
- FastAPI
- SQL
- Docker

**Resources:**
- https://github.com/InternetHealthReport/ihr-django
- https://docs.djangoproject.com/en/2.2/
- https://fastapi.tiangolo.com/
- https://learnscripting.org/streamlining-database-operations-running-sql-queries-from-a-shell-script/

**Project size:** 175 hours

**Difficulty:** Medium

**Contact:** Romain Fontugne (romain@iij.ad.jp), Dimitrios Giakatos (dimitrios@iij.ad.jp)

-----------------------------------
### Improve the IHR Website Codebase

**Brief explanation:** The IHR website provides outputs from IHR research projects 
through a simple and user-friendly web interface. Its current codebase is large 
and contains many features. This time, instead of adding new features, we will 
focus on improving the existing ones. The goal of this project is to refactor 
certain components to enhance reusability.

**Expected results:**
- Refactor the codebase
- Improve reusability

**Github discussion:** https://github.com/orgs/InternetHealthReport/discussions/47

**Knowledge Prerequisite:**
- VueJS
- JavaScript
- CSS
- HTML

**Resources:**
- https://github.com/InternetHealthReport/ihr-website

**Project size:** 175 hours

**Difficulty:** Medium

**Contact:** Dimitrios Giakatos (dimitrios@iij.ad.jp)

-----------------------------------
### IYP Browser

**Brief explanation:** The Internet Yellow Pages (IYP) is a knowledge database 
that aggregates information about various Internet resources, such as ASNs, 
IP prefixes, and domain names. Currently, we use the Neo4J browser to query 
the graph, which returns results in four formats: an interactive graph, a table, 
a raw table, and a JSON object. To enhance the user experience, especially for 
those unfamiliar with Cypher, we have developed an LLM model and will provide an 
API to simplify the querying process. Our goal is to develop a new browser that 
allows users to input either a Cypher query (using the Neo4J API) or an English 
description (using our LLM API) of the results they wish to obtain from the 
database. Additionally, we aim to continue providing the default four output 
formats along with explanations generated by our LLM API.

**Expected results:**
- Design a user-friendly, maintainable browser that connects to both the Neo4J API and our LLM API (frontend only, no backend)
- Implement a graph visualizer similar to that of the Neo4J browser
- Implement a data table viewer similar to that of the Neo4J browser
- Allow users to input either a Cypher query or a natural language description
- Provide the LLM-generated explanation text (from our LLM API) alongside the graph visualizer and/or data table viewer

**Github discussion:** https://github.com/orgs/InternetHealthReport/discussions/50

**Knowledge Prerequisite:**
- Neo4J
- Javascript
- VueJS
- NVL (Neo4j Visualization Library)
- Quasar

**Resources:**
- https://github.com/InternetHealthReport/internet-yellow-pages
- http://iyp.iijlab.net/
- https://neo4j.com/docs/nvl/current/
- https://www.npmjs.com/package/@neo4j-nvl/base
- https://neo4j.com/docs/getting-started/graph-visualization/graph-visualization/

**Project size:** 175 hours or 350 hours

**Difficulty:** Medium

**Contact:** Dimitrios Giakatos (dimitrios@iij.ad.jp), Malte Tashiro
(malte@iij.ad.jp), Romain Fontugne (romain@iij.ad.jp)

-----------------------------------
### Traceroute visualization (continuation of GSoC'24)

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

**Github discussion:** https://github.com/orgs/InternetHealthReport/discussions/21

**Knowledge Prerequisite:**
- Good understanding of traceroute
- Javascript
- VueJS
- Visualization library (i.e. Plotly or D3.js)

**Resources:**
- https://github.com/InternetHealthReport/ihr-website
- https://atlas.ripe.net/
- https://labs.ripe.net/author/massimo_candela/tracemon-network-debugging-made-easy/

**Project size:** 350 hours

**Difficulty:** Hard

**Contact:** Romain Fontugne (romain@iij.ad.jp), Malte Tashiro
(malte@iij.ad.jp), Dimitrios Giakatos (dimitrios@iij.ad.jp)


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
