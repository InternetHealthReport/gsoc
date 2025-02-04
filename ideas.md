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
us which service are running as usual and which one are not. This page could
also provide a machine-readable JSON object so that we can automate email alerts
when something is not running as usual.

**Expected results:**
- Find a suitable monitoring tool that can be used as a base for this project
- Implement a status page for all API endpoints and results, websites (ihr, ihr-archive,
  iyp), and the IYP database
- Add a machine-readable format of the page
- Automatic email notification when something is down

**Github discussion:** https://github.com/orgs/InternetHealthReport/discussions/51

**Knowledge Prerequisite:**
- Overview of the IHR ecosystem
- Docker
- Some web development experience

**Resources:**
- https://github.com/InternetHealthReport/

**Project size:** 90 hours

**Difficulty:** Easy

**Contact:** Dimitrios Giakatos (dimitrios@iij.ad.jp), Malte Tashiro
(malte@iij.ad.jp), Romain Fontugne (romain@iij.ad.jp)

-----------------------------------
### Migrate IHR API

**Brief explanation:**

**Expected results:**

**Github discussion:** https://github.com/orgs/InternetHealthReport/discussions/

**Knowledge Prerequisite:**

**Resources:**
- https://github.com/InternetHealthReport/

**Project size:** 175 hours

**Difficulty:** Medium

**Contact:** Romain Fontugne (romain@iij.ad.jp), Dimitrios Giakatos (dimitrios@iij.ad.jp)

-----------------------------------
### Improve the IHR Website Codebase

**Brief explanation:**

**Expected results:**

**Github discussion:** https://github.com/orgs/InternetHealthReport/discussions/47

**Knowledge Prerequisite:**

**Resources:**
- https://github.com/InternetHealthReport/

**Project size:** 175 hours

**Difficulty:** Medium

**Contact:** Dimitrios Giakatos (dimitrios@iij.ad.jp)

-----------------------------------
### IYP Browser

**Brief explanation:**

**Expected results:**

**Github discussion:** https://github.com/orgs/InternetHealthReport/discussions/50

**Knowledge Prerequisite:**

**Resources:**
- https://github.com/InternetHealthReport/

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

**Knowledge Prerequisite:** Good understanding of traceroute, Javascript, VueJS, and visualization library (i.e. Plotly or D3.js)

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
