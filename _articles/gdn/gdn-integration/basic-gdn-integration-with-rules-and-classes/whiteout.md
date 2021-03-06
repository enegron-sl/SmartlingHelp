---
layout: article
title: Whiteout
draft: false
Applies to:
  GDN: false
  Application-Resource-Files: false
  CMS-Connectors: false
edition:
redirect-url:
wistia:
  video: false
  id:
read-first:
  include: false
  sections:
    - section
  articles:
    - article
  others:
    - link:
      text:
further-reading:
  include: false
  sections:
    - section
  articles:
    - article
  others:
    - link:
      text:
migration-checklist:
  internal-links: true
  images: false
  FAQs: false
  related: false
  reviewed: false
---


The whiteout rule completely obscures the affected HTML when it is captured by Smartling. It will be served on your translated sites as it is on your source site, but will not be visible to translators at all.

Content with the Whiteout class is not stored anywhere in Smartling’s infrastructure.

The main reason for using a whiteout rule is to identify areas of your site that may show confidential client information, such as credit card details, to ensure these are never seen in Smartling.

## How to Apply

### Add the `sl_whiteout` class to your source code

~~~html
<div>
	<div class=”sl_whiteout”>
		Translators will not see this content.
	</div>
	<div>
		<p>This text will be seen and translated</p>
    </div>
</div>
~~~
