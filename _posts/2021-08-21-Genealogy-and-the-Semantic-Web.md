---
layout: post
title: Genealogy and the Semantic Web
tag:
- semanticweb
- genealogy
- family-tree
- linked-data
imagecredit_id: "@lauracathleen"
imagecredit_name: "Laura Fuhrman"
comments: true
---

![]({{ site.baseurl }}/images/laura-fuhrman-73OJLcahQHg-unsplash.jpg)

_Originally posted on [Medium](https://medium.com/@pwiech/genealogy-and-the-semantic-web-76e0f23f41e?source=friends_link&sk=f2906a996668735ce77801002fa55fb6)_

## Copy-pasting genealogy

<!-- excerpt-start -->

Thousands of hours have already gone into existing genealogical research. A lot of this time was spent by amateurs, volunteers and people passionate about genealogy. People are transcribing and indexing documents, collecting and aggregating information from different sources and publishing their work in various forms.

There are lots of centralized databases collecting the work of genealogists. The biggest ones contain millions of records. For example, [Wikitree](https://www.wikitree.com/) has over 27 million profiles, [Geneteka](https://geneteka.genealodzy.pl/) has over 38 million records, [Werelate](https://www.werelate.org/) has around 3 million profiles, [dbpedia](https://www.dbpedia.org/) has 1.6 million person records, and there are many more. Moreover, there are also countless very small sites publishing information about tens or hundreds of ancestors and relatives, often based on one of the popular genealogy site-building tools like [webtrees](https://webtrees.net/) or [TNG](https://tngsitebuilding.com/) or as reports from genealogy applications.

As an amateur genealogist I search the Web for mentions of my relatives. I use the search feature on different pages or just search using Google. When I find an interesting piece of information such as a birth record from a local archive or burial information from a cemetery's website, I copy the information to my personal genealogy database. Usually, I add a note with a reference to the source but sometimes I forget :-/

<!-- excerpt-end -->

I may also want to later publish my findings. I would like to be able to publish the data in a way that would allow other genealogists to easily make use of the information together with the original source references. The majority of ways I can publish my data will only allow others to manually copy the information. I can publish a [GEDCOM](https://en.wikipedia.org/wiki/GEDCOM) file but in most cases it is quite useless for others (although better than nothing).

## Problems

There are a number of problems here. Firstly, manually copying data is error prone, some information may get lost or be incorrectly interpreted. I'll only copy the information that I find relevant, skipping things that are not interesting for me but may be interesting for others. Apart from obvious copying errors such as typos, I may accidentally swap the first and last name or copy just the town name without the more detailed jurisdiction ([problem explained](https://xkcd.com/2480/)).

Secondly, if I don't note down the source of the information I copy, I immediately make the information less reliable. What if I find contradicting information elsewhere? How do I know which one is true or at least more credible? WikiTree requires all entered information to have a source and it is a really great rule. I have found lots of information about my relatives in other people's MyHeritage trees but I have no idea how good the information is and where it came from because there are no sources given. In the end, when I publish my research (e.g. on WikiTree), I'd like to be able to cite sources for everything I have gathered.

Finally, I'd like to be able to collect information from online sources easily. I find something on WikiTree or [Find a Grave](https://www.findagrave.com/) - with a single click I add it to my database connecting to the right person. This should work the other way around too. When I publish my research, others should also be able to get this information with a single click.

There are more problems with genealogy data representation and linking but I'd like to focus on the ones above as I find them the most frustrating.

## The promise of the Semantic Web

Now, here comes the [Semantic Web](https://en.wikipedia.org/wiki/Semantic_Web). It offers a promise of a web of linked data with easy referencing and well-defined semantics. The hype around the Semantic Web culminated in the early 2000s and quite a lot of research and technology has been created since then. Family relationships are sometimes used as [examples of using Semantic Web technologies](https://blog.tilde.pro/semantic-web-technologies-on-an-example-of-family-trees-7518f3f835a9). But is there anything that can be used for real-world genealogy applications?

Can the Semantic Web be a solution to the problems mentioned above? Certainly not to the one about ease of use - this is something that needs to be built. However, maybe it could help with the problems of referencing information sources and copying data retaining correct semantics. Imagine that all websites that publish information useful for genealogists always also publish a computer-friendly version of the information. This would allow creation of a number of tools that help genealogists, including easier referencing of information, automated analysis and inferences and searching across websites.

I'd like to dive deeper into possible applications of Semantic Web technologies in the field of genealogy. I hope to continue with further posts on this topic. In the meantime, please let me know in the comments if you have any ideas or suggestions.

---

Next: [Structured data on genealogy websites]()
