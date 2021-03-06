---
title: GDN Integration
layout: section
subsections:
  - title: Basic GDN Integration using Rules and Classes
  - title: Advanced HTML Integration
subarticles:
  - title: JavaScript in the GDN
  - title: JSON in the GDN
  - title: Creating Localized Content
  - title: Search Integration
  - title: Third-Party Form and Button Integration
  - title: How to Specify a Language-Specific CSS
  - title: Handle Plurals in a GDN Project
  - title: Translate Text in Buttons, Tabs, and, Navigation
  - title: GDN - Create Pattern Match Rules
  - title: Specifying Professional and Community Translation Content in the GDN
wistia:
  video: false
  id:
migration-checklist:
  internal-links: false
  images: false
  FAQs: false
  related: false
  reviewed: false
---


Once you have your basic [DNS setup](/support/sections/gdn-hosting-setup/) working correctly and your requests are being handled by Smartling’s GDN proxy, you have a number of options for controlling how Smartling captures your content for translation and how your translation content is deployed. There are three basic methods of controlling your GDN integration:

* Creating ‘Rules’ in the Smartling Dashboard,
* Tagging HTML elements on your pages with special Smartling classes, and
* Tagging your JavaScript and JSON content using Smartling directives.


The methods you use most for your project will depend on how your website is set up. If you are assembling a significant amount of the DOM on the client-side, you will need to work with JavaScript and JSON integration. If you are serving static content or server-generated pages, you can use HTML classes, or write Rules in the Dashboard for simpler functions.

### General Tips

#### Well-formed HTML is important

Smartling needs to parse your content just like a browser. However, Smartling necessarily parses HTML in a less forgiving way than most browsers, so it's important that your HTML is compliant with [HTML5 standards](https://www.w3.org/TR/html5/).

#### Remember that the GDN is a proxy service!

The GDN handles all HTML and JSON requests for you and replaces translatable strings with the appropriate translation on the fly. Therefore, any tags or directives need to be part of a request. For example, adding Smartling classes to DOM elements built dynamically on the client-side will have no effect.

#### Consider your translators. Consider localization best practices.

GDN integration gives you a lot of power over how content is captured and parsed. But remember to consider how to give your Translators what they need to provide good translations. To take an extreme example, it’s quite possible to create an integration to capture each word on your site as it’s own string. This would certainly decrease the number of words you need to translate, but it would make it impossible to provide a quality translation of each page. Strings and segments are the basic units of translation for a reason. Think before you chop them up.

#### Dynamic Content is Harder

Static content is the simplest to serve through the GDN. Almost every website has some dynamic content and one of the main purposes of GDN integration is to help you to handle your dynamic content efficiently, but if your project uses Single Page Application architecture, such as AngularJS, a files-based approach may be more effective.

### A Note on Examples

There are countless ways to build and serve websites and web apps. In our examples, we use mustache.js and jQuery to template strings and build DOM elements on the client-side, and straight HTML or EJS templating to demonstrate static or server-built pages. You may not be able to copy/paste our examples directly into your project, but the same general techniques will work regardless of the framework you are using.