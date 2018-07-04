---
title: IIIF
categories: topics
tags: featured
excerpt: Library of Congress IIIF API to manipulate images from Library of Congress collections
---

## What is International Image Interoperability Framework (IIIF)?
> In short, IIIF enables better, faster and cheaper image delivery. The IIIF gives users a rich set of baseline functionality for `viewing`, `zooming`, and `assembling` the best mix of resources and tools to `view`, `compare`, `manipulate` and work with images on the Web, an experience made `portable–shareable`, `citable`, and `embeddable`.

## URL?
Each part of URL determines what and how the image is returned. To learn more in-depth please see [here](http://iiif.io/api/image/2.1/).
<pre><code>{scheme}://{server}{/prefix}/{identifier}/{region}/{size}/{rotation}/{quality}.{format}
</code></pre>

* scheme - Indicates the use of the HTTP or HTTPS protocol in calling the service.
* server - The host server on which the service resides. The parameter may also include a port number.
* prefix - The path on the host server to the service. This prefix is optional, but may be useful when the host server supports multiple services. The prefix may contain multiple path segments, delimited by slashes, but all other special characters must be encoded. See URI Encoding and Decoding for more information.
* identifier - The identifier of the requested image. This may be an ark, URN, filename, or other identifier. Special characters must be URI encoded.
* region - The region parameter defines the rectangular portion of the full image to be returned. Region can be specified by pixel coordinates, percentage or by the value “full”, which specifies that the entire image should be returned.
* size - The size parameter determines the dimensions to which the extracted region is to be scaled.
* rotation - The rotation parameter specifies mirroring and rotation. A leading exclamation mark (“!”) indicates that the image should be mirrored by reflection on the vertical axis before any rotation is applied. The numerical value represents the number of degrees of clockwise rotation, and may be any floating point number from 0 to 360.
* quality - The quality parameter determines whether the image is delivered in color, grayscale or black and white.
* format - The format of the returned image is expressed as an extension at the end of the URI.

## API for Chronicling America
* `Server`
{% highlight yaml %}
http://chroniclingamerica.loc.gov/
{% endhighlight %}
* `Search` the newspaper directory and digitized page contents using `OpenSearch`. Example below searches "michigan", JSON response, starting at page 5.
{% highlight yaml %}
http://chroniclingamerica.loc.gov/search/titles/results/?terms=michigan&format=json&page=5 
{% endhighlight %}
* `URL pattern`. Example below shows third available page from first edition, January 5, 1900.
{% highlight yaml %}
http://chroniclingamerica.loc.gov/lccn/sn86069873/1900-01-05/ed-1/seq-3/
{% endhighlight %}
* `Auto Suggest` API for looking up `newspaper titles`
* `JSON` views of Chronicling America resources. Example below shows third available page from first edition, January 5, 1900.
{% highlight yaml %}
http://chroniclingamerica.loc.gov/lccn/sn86069873/1900-01-05/ed-1/seq-3.json
{% endhighlight %}
* `Bulk Data` for `research` and external services. Below example shows detailed information about a specific batch.
{% highlight yaml %}
http://chroniclingamerica.loc.gov/batches/batch_dlc_jamaica_ver01.json 
{% endhighlight %}

To learn more in-depth please see [here](https://chroniclingamerica.loc.gov/about/api/)

### IPython Examples
#### Import libraries
```python
from IPython.display import Image, display
```
<pre><code>import requests
from IPython.display import Image, display
</code></pre>

#### Get JSON
<pre><code>r = requests.get("http://chroniclingamerica.loc.gov/lccn/sn86069873/1900-01-05/ed-1/seq-1.json")
r.json()
</code></pre>
<pre><code>OUTPUT:
  {u'issue': {u'date_issued': u'1900-01-05',
  u'url': u'http://chroniclingamerica.loc.gov/lccn/sn86069873/1900-01-05/ed-1.json'},
  u'jp2': u'http://chroniclingamerica.loc.gov/lccn/sn86069873/1900-01-05/ed-1/seq-1.jp2',
  u'ocr': u'http://chroniclingamerica.loc.gov/lccn/sn86069873/1900-01-05/ed-1/seq-1/ocr.xml',
  u'pdf': u'http://chroniclingamerica.loc.gov/lccn/sn86069873/1900-01-05/ed-1/seq-1.pdf',
  u'sequence': 1,
  u'text': u'http://chroniclingamerica.loc.gov/lccn/sn86069873/1900-01-05/ed-1/seq-1/ocr.txt',
  u'title': {u'name': u'The Bourbon news.',
  u'url': u'http://chroniclingamerica.loc.gov/lccn/sn86069873.json'}}
</code></pre>

<hr />
## REFERENCE
[Guide for IIIF](https://github.com/LibraryOfCongress/data-exploration/blob/master/IIIF.ipynb)