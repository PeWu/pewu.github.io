---
layout: post
title: Structured data on genealogy websites
tag:
- genealogy
- gedcom
- linked-data
- semanticweb
- structured-data
imagecredit_id: "@killerfvith"
imagecredit_name: "Alex wong"
comments: true
---

![]({{ site.baseurl }}/images/alex-wong-l5Tzv1alcps-unsplash.jpg)

_Originally posted on [Medium](https://medium.com/@pwiech/structured-data-on-genealogy-websites-153894c801c3?source=friends_link&sk=f151cd07ef16dc4e5708ecb894ba1947)_

<!-- excerpt-start -->

In my previous post, I listed several problems with publishing and using genealogy data on the Web. In short, the issues are:
- it should be easier to copy data from Web resources to a researcher’s database
- data on the Web may be ambiguous
- good links to sources should be provided where possible
- software could exist to help with the above

Before we can try to figure out what solutions are viable, let’s see what the current state of genealogy websites is. What I wanted to do is to take some websites that contain information interesting for genealogists and assess them in terms of how easy it is to collect data from them in an automatic and unambiguous way and also be able to link back to the site as the source of information.

<!-- excerpt-end -->

Tim Berners Lee proposed a way of assessing Web data sources in terms of machine-readable access. It is called _[5-star Linked Data](https://www.w3.org/DesignIssues/LinkedData.html)_ and the criteria are described as follows:

> ★ Available on the web (whatever format) but with an open licence, to be Open Data
>
> ★★ Available as machine-readable structured data (e.g. excel instead of image scan of a table)
>
> ★★★ as (2) plus non-proprietary format (e.g. CSV instead of excel)
>
> ★★★★ All the above plus, Use open standards from W3C (RDF and SPARQL) to identify things, so that people can point at your stuff
>
> ★★★★★ All the above, plus: Link your data to other people’s data to provide context

I started assigning these stars to genealogy websites but it soon turned out that I’ll be making my own rating system.

Firstly, I definitely don’t expect all sites to expose data as _Open Data_. There are paid genealogy sites and private sites and this is fine. It is clear that some data actually should be made private, especially when talking about living individuals. However, a paid site or a private one can still be machine-readable and citeable. For example, FamilySearch exposes its data in GedcomX format and is a paid site. Also, WikiTree exposes structured data even for living individuals for those that have appropriate access.

The “excel instead of image scan of a table” star is also not very relevant to genealogy data. Actually, some sources are exactly that — scans and photos of original materials, and this is what we expect them to be. We don’t want them being _replaced_ by transcribed data, we want them _extended_ by transcribed data. Instead, I would argue that we should distinguish structured data from data that needs to be parsed out from HTML contents.

Having a non-proprietary data format is also not a big issue, especially that I haven’t seen genealogy data published in Excel files.

The fourth and fifth stars are actually relevant. Using standard data formats is a big plus. Linking to other data even more so.

---

Let me phrase my own “star” system:

★☆☆☆☆ **Data is referenceable by a unique URL**

It should be possible to reference each item of data individually. In particular, a single record, a single person, a single grave, a single family should be referenceable. In contrast, some sites only provide ways to reference lists or groups of items.

☆★☆☆☆ **Data is machine-readable**

It should be possible to create simple rules that extract data from the site. This means that fields are separated (e.g. first and last name) and are consistently named. In contrast, most sites require HTML scraping with complex rules for dealing with names and dates.

☆☆★☆☆ **Data is in a well-known format**

Instead of having each website publish data in its own format, it is much better to have only a few formats that everyone uses. It seems that the most popular now is using [Microdata annotations with schema.org semantics](https://schema.org/docs/gs.html) but [GedcomX](http://www.gedcomx.org/) and [DBpedia’s ontologies](https://www.dbpedia.org/resources/ontology/) are also a good choice.

☆☆☆★☆ **Data contains links to other entities**

For example, an entry for a person links to entries for the person’s parents.

☆☆☆☆★ **Data contains links to entities on other websites**

Not only links inside the same site but also links to other websites. Example — DBpedia linking to WikiTree

---

Here are some websites I looked at:

### ★★★★★ DBpedia

[Example link](https://dbpedia.org/page/J._R._R._Tolkien)

RDF and all kinds of serializations of the RDF data model

This is the only website that has all the stars.

### ★★★★☆ Billion Graves

[Example link](https://billiongraves.com/grave/ANTONIA-WI%C4%98CH/11529550)

Microdata + schema.org

### ★★★★☆ FamilySearch

[Example link](https://www.familysearch.org/ark:/61903/1:1:K4R2-GQ9)

GedcomX

Getting a GedcomX response requires a special HTTP request header:

`accept: application/x-gedcomx-v1+json`

### ★★★★☆ Find a Grave

[Example link](https://www.findagrave.com/memorial/169370527/alex-a.-wiech)

Microdata + schema.org

### ★★★★☆ Geni

[Example link](https://www.geni.com/people/Stanis%C5%82aw-Wo%C5%BAniak/6000000060119178969)

Microdata + schema.org

### ★★☆★★ WeRelate

[Example link](https://www.werelate.org/wiki/Person:Samuel_Horsfall_%281%29)

Custom data format

Links to external websites are stored as source citations.

### ★★★★☆ WikiTree

[Example link](https://www.wikitree.com/wiki/Clemens-1)

Microdata + schema.org

Links to other sites are embedded in a free-text field.

### ★★★☆☆ Graves in Belarus

[Example link](http://www.graves.by/pins/d3173b1b4513f397.html)

Open Graph

### ★★☆☆☆ MyHeritage record

[Example link](https://www.myheritage.com/research/collection-10171/rejestr-urodze%C5%84-w-piotrkowie-trybunalskim-polska-1808-1875?itemId=7540-F&amp;action=showRecord)

Custom HTML properties

### ★☆☆★☆ webtrees

[Example link](https://dev.webtrees.net/demo-stable/index.php?route=%2Fdemo-stable%2Ftree%2Fdemo%2Findividual%2FI10090%2FElizabeth-Angela-Marguerite-Bowes-Lyon)


### ★☆☆☆☆ FreeBMD

[Example link](https://www.freebmd.org.uk/cgi/information.pl?cite=UZgs5TDvhf%2FMVcQZKkuU5Q&amp;scan=1)

### ★☆☆☆☆ FreeCen

[Example link](https://www.freecen.org.uk/search_records/59055b2de9379091b13b29d7/john-nowakowski-1891-sussex-steyning-1851-)

### ★☆☆☆☆ FreeReg

[Example link](https://www.freereg.org.uk/search_records/5817ac7de93790eb7f5d69a6/mary-turney-abell-london-marriage-buckinghamshire-cheddington-1701-04-27)

### ★☆☆☆☆ sejm-wielki.pl

[Example link](http://www.sejm-wielki.pl/b/psb.20874.1)

### ★☆☆☆☆ Szukaj w archiwach

[Example link](https://www.szukajwarchiwach.gov.pl/jednostka/-/jednostka/9743252)

Open Graph annotations

### ★☆☆☆☆ TNG

[Example link](https://genealogiapolska.pl/getperson.php?personID=I10013&amp;tree=Wojtalik)

There is an option that can be turned on to enable downloading a GEDCOM file.

### ★☆☆☆☆ Zielona Góra — cmentarze

[Example link](http://www.mzp.pl/wyszukiwarka-grobow/szczegoly/11556)

### ☆☆☆☆★ Geneteka

[Example link](https://geneteka.genealodzy.pl/index.php?op=gt&amp;lang=pol&amp;bdm=B&amp;w=07mz&amp;rid=B&amp;search_lastname=wi%C4%99ch&amp;search_name=stanis%C5%82aw&amp;search_lastname2=&amp;search_name2=&amp;from_date=1880&amp;to_date=1890&amp;exac=1&amp;parents=1)

One can only link to search results but not individual records from the results. The records may contain links to scans hosted on other websites.

### ☆☆☆☆☆ straty.pl

[Example link](https://pewu.github.io/stratypl-link?1551543)

This is the only website that didn’t receive any stars. Unique URLs are not available on the website but can be provided by an [external service](https://pewu.github.io/stratypl-link).

---

I don’t have access to paid sites, so some of the popular ones are missing in the table. The [genscrape](https://github.com/rootsdev/genscrape) library is a valuable source for finding out how data can be obtained from genealogy websites.

As usual, not everything is binary, there are nuances in the data representations. For instance, although Geni uses Microdata, the links between family members are not included in the metadata, only in HTML links. Some websites that don’t explicitly expose structured data are quite easy to parse (consistent table headers) while others are not.

Since this is just some random sites I have chosen and the information in the table may become outdated (hopefully), I’m going to set up a GitHub repository to collect a more comprehensive table. EDIT: Repository created at [github.com/PeWu/genealogy-websites](https://github.com/PeWu/genealogy-websites)

In the next post, I’d like to take a closer look at existing research about genealogy data formats including the popular ones already used. Are the data formats used today enough to express what is needed for genealogy or do we need something different? Maybe GEDCOM is everything we will ever need?
