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
<code>{scheme}://{server}{/prefix}/{identifier}/{region}/{size}/{rotation}/{quality}.{format}</code>
* scheme - Indicates the use of the HTTP or HTTPS protocol in calling the service.
* server - The host server on which the service resides. The parameter may also include a port number.
* prefix - The path on the host server to the service. This prefix is optional, but may be useful when the host server supports multiple services. The prefix may contain multiple path segments, delimited by slashes, but all other special characters must be encoded. See URI Encoding and Decoding for more information.
* identifier - The identifier of the requested image. This may be an ark, URN, filename, or other identifier. Special characters must be URI encoded.
* region - The region parameter defines the rectangular portion of the full image to be returned. Region can be specified by pixel coordinates, percentage or by the value “full”, which specifies that the entire image should be returned.
* size - The size parameter determines the dimensions to which the extracted region is to be scaled.
* rotation - The rotation parameter specifies mirroring and rotation. A leading exclamation mark (“!”) indicates that the image should be mirrored by reflection on the vertical axis before any rotation is applied. The numerical value represents the number of degrees of clockwise rotation, and may be any floating point number from 0 to 360.
* quality - The quality parameter determines whether the image is delivered in color, grayscale or black and white.
* format - The format of the returned image is expressed as an extension at the end of the URI.

<pre><code>
import requests
from IPython.display import Image, display
</code></pre>

### Example
<pre><code>
r = requests.get("http://tile.loc.gov/image-services/iiif/service:sgp:sgpbatches:batch_dlc_anacostia_ver01:data:sn84025948:0023728866A:1942081001:0202/info.json")
r.json()
</code></pre>
<code>
  {'@context': 'http://iiif.io/api/image/2/context.json',
 '@id': 'https://tile.loc.gov/image-services/iiif/service:sgp:sgpbatches:batch_dlc_anacostia_ver01:data:sn84025948:0023728866A:1942081001:0202',
 'height': 4663,
 'profile': ['http://iiif.io/api/image/2/level2.json',
  {'formats': ['jpg', 'jp2', 'tif', 'pdf', 'gif', 'png', 'webp'],
   'qualities': ['default', 'native', 'color', 'gray', 'bitonal'],
   'supports': ['baseUriRedirect',
    'cors',
    'jsonldMediaType',
    'mirroring',
    'regionByPct',
    'regionByPx',
    'rotationBy90s',
    'sizeByWhListed',
    'sizeByForcedWh',
    'sizeByH',
    'sizeByPct',
    'sizeByW',
    'sizeByWh']}],
 'protocol': 'http://iiif.io/api/image',
 'tiles': [{'scaleFactors': [1, 2, 4, 8, 16, 32, 64], 'width': 512}],
 'width': 3156}
</code>

## REFERENCE
[Guide for IIIF](https://github.com/LibraryOfCongress/data-exploration/blob/master/IIIF.ipynb)