<h2 id="projects" style="margin: 2px 0px -15px;">Selected Projects</h2>

<div class="publications">
<ol class="bibliography">

{% for item in site.data.projects.main %}
<li>
{% assign media = item.video | default: item.image %}
<div class="pub-row{% unless media %} no-teaser{% endunless %}">
  {% if media %}
  <div class="col-sm-3 abbr" style="position: relative; padding-right: 15px; padding-left: 15px;">
    {% if item.video %}
    <video src="{{ item.video }}" class="teaser img-fluid z-depth-1" autoplay muted loop playsinline preload="metadata" aria-label="{{ item.title }}"></video>
    {% else %}
    <img src="{{ item.image }}" class="teaser img-fluid z-depth-1" alt="{{ item.title }}" loading="lazy">
    {% endif %}
  </div>
  {% endif %}
  <div class="col-sm-9" style="position: relative; padding-right: 15px; padding-left: {% if media %}20px{% else %}0{% endif %};">
    {% assign title_link = item.url | default: item.code | default: item.paper %}
    <div class="title">{% if title_link %}<a href="{{ title_link }}" target="_blank" rel="noopener">{{ item.title }}</a>{% else %}{{ item.title }}{% endif %}</div>
    <div class="pub-description">{{ item.description }}</div>
    {% if item.tags %}<div class="tags">{% for tag in item.tags %}<span class="tag">{{ tag }}</span>{% endfor %}</div>{% endif %}
    <div class="links">
      {% if item.code %}<a href="{{ item.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" style="font-size:12px;">Code</a>{% endif %}
      {% if item.paper %}<a href="{{ item.paper }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" style="font-size:12px;">Paper</a>{% endif %}
      {% if item.youtube %}<a href="{{ item.youtube }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" style="font-size:12px;">Video</a>{% endif %}
    </div>
  </div>
</div>
</li>
<br>
{% endfor %}

</ol>
</div>
