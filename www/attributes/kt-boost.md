---
layout: layout.njk
title: </> kutty - kt-boost
---

## `kt-boost`

The `kt-boost` attribute allows you to "boost" normal anchors and form tags to use AJAX instead.  This
has the [nice fallback](https://en.wikipedia.org/wiki/Progressive_enhancement) that, if the user does not 
have javascript enabled, the site will continue to work.

For anchor tags, clicking on the anchor will issue a `GET` request to the url specified in the `href` and
will push the url so that a history entry is created.  The target is the `<body>` tag, and the `innerHTML`
swap strategy is used by default.  All of these can be modified by using the appropriate attributes, except
the `click` trigger.

For forms the request will be converted into a `GET` or `POST`, based on the method in the `method` attribute
and will be triggered by a `submit`.  Again, the target will be the `body` of the page, and the `innerHTML`
swap will be used.

Here is an example of some boosted links:

```html
<div kt-boost="true">
  <a href="/page1">Go To Page 1</a>
  <a href="/page2">Go To Page 2</a>
</div>
```

### Notes

* `kt-boost` is inherited and can be placed on a parent element
* Only links that are to the same domain and that are not local anchors will be boosted
* All requests are done via AJAX, so keep that in mind when doing things like redirects