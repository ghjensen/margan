---
title: About
layout: about
permalink: /about.html
# include CollectionBuilder info at bottom
credits: true
# featured-image value can be one objectid for a photo object in this collection, a relative path to an image in this project, or a full url to any image. If left blank, no featured image will appear at top of About page.
about-featured-image: objects/mario-verduzco-xSdFf1Lcx6o-unsplash.jpg
# set background-position for featured image, "center", "top", "bottom"
position: center
# major heading to display over featured image
heading: About MaRGAN
# paragraph text below heading in featured image
sub-heading: 
# additional padding added to the feature to increase size. Give value in em or px, e.g. "5em".
padding: 6em
# Edit the markdown on in this file to describe your collection
# Look in _includes/feature for options to easily add features to the page
---

## Overview

### Novel Religion
***Literary Representation and Re-imaging of Global Religious Practice***

The Mapping Religion in the Global Anglophone Novel (MaRGAN) project unites two features of the twentieth century: the rise of the novel as a global form and religious change following the impact of modernity upon religious practice. The connection between the two has often been difficult to record because what *religion* means differs from scholar to scholar and from context to context.

The project thus defines the religious content of the novel through its connection with one or more of 32 keywords such as `ritual`, `omens & visions`, and `holy people`. This approach enables the project to expand the kinds of texts construed as relevant to considerations of religion rather than focusing on a genre closely identified with a religious tradition (i.e., the Catholic novel); it thus facilitates comparison between texts that approach religion differently, whether that difference is marked by opposing views of religion, familiarity with different religious traditions, or concentration on a particular aspect of the variety of phenomena collected under the term *religion*. The project not only challenges understandings of the novel as a secular form through attention to the sheer range of religious representations present in this corpus of novels but also argues that these representations are responses to ongoing religious change. As the project demonstrates, the novel is a cultural form in which authors reflect on the consequences of, need for, or ongoing role of religion in societies undergoing widespread transformation. The novel, in this way, becomes an agent of religious change, exploring what religion may do to and for societies.

In its initial phase, MaRGAN will define a corpus of approximately 400 global anglophone novels published between 1890 and 1980 that engage with religion. The database powering the website categorizes these engagements using one or more pre-defined religious keywords (i.e., `ritual`) and annotates the novel’s relation to this keyword using free text. In addition, the database captures basic bibliographic information about the novels and biographic data about the author. The project thus assumes that the nature and value of a given representation of religion in a novel is responsive to the geographical, historical, and religious contexts of the author. 

The data is visualised in three ways: a timeline (to allow for developments over the 100 years of the project); word clouds (to reveal the frequency of certain keywords with respect to religion in novels); and a map (to allow for exploration of the geographical global).

### Project Data

The MaRGAN dataset currently features {% assign total_novels = site.data.novel | where_exp: "item", "item.objectid != nil" | size %}
<strong>{{ total_novels }}</strong> novels.
 
{% include index/carousel.html %}

You can browse, search, and explore the novels and their metadata using various site features:
- The [Browse](browse.html) page
- Word clouds of novel [Keywords](keywords.html) and [Locations](locations.html)
- A tabular [Timeline](timeline.html) of the novels
- A [Map](map.html) of the novels
- Project [Data](data.html) searches and downloads

Information about the authors is also featured on the above pages and on dedicated Author pages (coming soon!).

### Project Members

#### Project Team
- Elizabeth Anderson - *University of Aberdeen, UK*
- Jamie Callison - *University of Agder, Norway*
- Suzanne Hobson - *Queen Mary University of London, UK*
- Graham Jensen - *Independent, Canada*
- Mimi Winick - *Virginia Commonwealth University, USA*

#### Advisory Board
- J. Barton Scott - *University of Toronto, Canada*
- Michael Allan - *University of Oregon, USA*
- Kris J. Trujillo - *University of Chicago, USA*
- Shuhita Bhattacharjee - *Indian Institute of Technology Hyderabad, India*
- J. Winter Werner - *Wheaton College, MA, USA*
- Alana Vincent - *Umeå University, Sweden*
- Kees de Groot - *Tilburg University, Netherlands*

## Acknowledgements

We are grateful to the following students and individuals who assisted with data entry and other project tasks:

## About this Website

(To be added: a bit about Graham's work on the website, tools and workflows involved, etc.)