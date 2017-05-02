## The CSU Online Learning Exchange

This site was built to accommodate Version 2 of the CSU Online Learning Model and it's associated resources. These include the OLM Mixer and a growing collection of Strategies & Practice examples that illustrate how they can be utilised to increase student engagement.


### Updates

**May 2017**

- Fixing content
- Big found with old responsive video player - playing havoc with new flexbox elements. Old code has been replaced.

```css
.video-container {
    position: relative;
    padding-bottom: 56.25%;
    padding-top: 30px;
    height: 0;
    overflow: hidden;
    margin-bottom: 1rem;
    display: flex;
    flex-direction: column;
}

.video-container div {
  flex-grow: 1;
  position: relative;
}

.video-container iframe,
.video-container object,
.video-container embed {
    position: absolute;
    top: 0;
    left: 0;
    // flex: 1 1 auto;
    width: 100%;
    min-height: 100%;
}
```

**April 2017**

More updates
- fixes to Swiper.js components not playing nicely with Flexbox elements.
- new media added to pages throughout
- Improvements to Applications type and associated Case Studies
  - added Taster Videos script and front matter
- developing workflow for GitHub based editing
- swapped i2 references to Interact2 site wide

**March 2017**

#### Big Updates

- Moved Strategies from posts to a Collection
- New archive page created
- New "Applications" collection created to include Case Studies
- Added Range bars based of code found here: http://codepen.io/mukealicious/pen/jWoeZY
- Swapped site to Fluid Type as outlined here: https://css-tricks.com/snippets/css/fluid-typography/ & https://blog.codepen.io/2016/10/31/fluid-type-blogs/
- Fluid line height: http://codepen.io/timbrown/pen/akXvRw/

**6 March 2017**

Creating a stable update to build the next set of features. Will be updating CSS to be more responsive and improve the readability of the site.

- Tweaks to mixer code to reduce size of flyouts and slow down the animation
- Edits to text to fix minor mistakes
- Commenting out access to new Case Study pages - will build on separate branch and merge back in
- Planning to update styles and go for more responsive typography to improve readability

**15 September 2016**

- Added subject code to be indexed by search
- Added subject name to be indexed by search
- Added summary to Strategy List Pages + link to element
- Moved back button below summary text
- Testing out incorporation of [Swiper](http://idangero.us/swiper/) - [Add Multiples](https://github.com/nolimits4web/Swiper/blob/master/demos/24-multiple-swipers.html) - changed colour of next & prev - inline of SVG.

**24 August 2016**

- Added Search! Booyeah! Used [this tutorial for setting up lunar.js](http://jekyll.tips/jekyll-casts/jekyll-search-using-lunr-js/)
- Added Piwik tracking code for Analytics
- Updated favicon code and icons from [Real Favicon Generator](http://realfavicongenerator.net/)

**29th July 2016**

- Added videos to the Model & Elements pages
- Added Alt tags to images
- Minor fixes to text

**19th July 2016**

- Beginning to add real Strategies to the site

**17th July 2016**

- Updated mixer content, inverted table
- Updated content on all element pages
- Used ```<a name="tith"></a>``` to create anchor tags
- Added youtube Embedd via ```liquid {% include youtubePlayer.html id="ZThtaJ1_VUs" %}``` just swap out the ID and wrap in layout div

**15 July 2016**

- Replaced placeholder text on homepage
- Updated Mixer - inverted layout, added feedback button, added hero image,
- Remove QLT section in Strategies - can add back again later

```html
<div class="row u-release">
<div class="container">
    <h3>Collections</h3>
        <p>In essence what is the exemplar & how does it work? What did you ask the learners to do? How did they interact? What are the key points and critical factors? Explain it simply and clearly. ?</p>
    <div class="tile-icons">
        <div class="tiles pink-bg">
            <a href="{{ site.baseurl }}/tags/QLT9.html">
            <img src="{{ site.baseurl }}/images/qlt9-rev.png" class="u-full-width">
            <h4>QLT KPI 9</h4></a>
        </div>
        <div class="tiles pink-bg">
            <a href="{{ site.baseurl }}/tags/QLT11.html">
            <img src="{{ site.baseurl }}/images/qlt11-rev.png" class="u-full-width">
            <h4>QLT KPI 11</h4></a>
        </div>
            <div class="tiles pink-bg">
            <a href="{{ site.baseurl }}/tags/QLT12.html">
            <img src="{{ site.baseurl }}/images/qlt12-rev.png" class="u-full-width">
            <h4>QLT KPI 12</h4></a>
            </div>
    </div>
</div>
</div>    
```


### Tag Archive Pages

Archive pages have been created using the following code:

````liquid
<h3>Related post</h3>
{% assign listed_posts_urls = page.url | split: ' ' %}
{% for tag in page.tags %}
  {% for mypost in site.tags[tag] %}
    {% if listed_posts_urls contains mypost.url %}
    {% else %}
      <div>
        <h5><a href="{{ mypost.url }}">{{ mypost.title }}</a></h5>
      </div>
      {% assign listed_posts_urls = listed_posts_urls | push: mypost.url %}
    {% endif %}
  {% endfor %}
{% endfor %}
````

The pages are generated by creating Markdown files in the Tags folder with the following YAML information:

````yaml
layout: tags
title: "Learning Communities"
tags: "Learning Communities"
````

#### External code used in this project

- CSS Tags: [http://codepen.io/wbeeftink/pen/dIaDH](http://codepen.io/wbeeftink/pen/dIaDH)
- Nice CSS Lists: [https://jsfiddle.net/vandigroup/3Lvpt9rc/1/](https://jsfiddle.net/vandigroup/3Lvpt9rc/1/)
- Sorted Navigation: [http://www.unknownerror.org/opensource/jekyll/jekyll/q/stackoverflow/9053066/sorted-navigation-menu-with-jekyll-and-liquid](http://www.unknownerror.org/opensource/jekyll/jekyll/q/stackoverflow/9053066/sorted-navigation-menu-with-jekyll-and-liquid)
- Mixer built with this Flexbox code: [http://www.cssplay.co.uk/menu/cssplay-flexbox-gallery.html](http://www.cssplay.co.uk/menu/cssplay-flexbox-gallery.html)
- CSS for APA Referencing: [https://github.com/bertobox/CSS-for-APA-Style-references](https://github.com/bertobox/CSS-for-APA-Style-references)
- Skeleton-Sass: [https://github.com/WhatsNewSaes/Skeleton-Sass](https://github.com/WhatsNewSaes/Skeleton-Sass)
