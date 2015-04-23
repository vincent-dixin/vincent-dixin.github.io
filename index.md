---
layout: page
title: Hello World!111
tagline: Supporting tagline
---
{% include JB/setup %}

<div id="article-list">
  {% for post in site.posts  %}
  
    {% capture this_year %}{{ post.date | date: "%Y" }}{% endcapture %}
    {% capture this_month %}{{ post.date | date: "%B" }}{% endcapture %}
    {% capture this_date %}{{ post.date | date: "%e" }}{% endcapture %}
    {% capture next_year %}{{ post.previous.date | date: "%Y" }}{% endcapture %}
    {% capture next_month %}{{ post.previous.date | date: "%B" }}{% endcapture %}
    <div class="article well clearfix">
    	<div class="data-article hidden-xs">
			<span class="month">{{this_month}}</span>
			<span class="day">{{this_date}}</span>
		</div><section class="hidden-xs"><div class="title-article"><h1><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></h1></div><div class="tag-article"><span class="label label-zan"><i class="fa fa-tags"></i><a href="{{ BASE_PATH }}/categories.html#{{ post.category }}-ref" rel="category tag">{{ post.category }}</a></span><span class="label label-zan"><i class="fa fa-user"></i> <a href="http://www.hudixin.net/author/admin" title="由胡迪新发布" rel="author">胡迪新</a>/span><span class="label label-zan"><i class="fa fa-eye"></i></span><div class="content-article"><div class="alert alert-zan">{{ post.excerpt }}</div></div></div></section>  </div>
{% endfor %}
