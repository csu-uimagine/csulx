## The CSU Online Learning Exchange

This site was built to accomodate Version 2 of the CSU Online Learning Model and it's associacted resources. These include the OLM Mixer and a growing collection of Strategies & Practice examples that ilustrate how they can be utilised to increase student engagement. 


### Updates

**17th July 2016**

- Updated mixer content, inverted table
- Updated content on all element pages
- Used ```html <a name="tith"></a>``` to create anchor tags
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