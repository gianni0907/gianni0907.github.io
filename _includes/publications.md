<h2 id="publications" style="margin: 2px 0px -15px;">Selected Publications</h2>

<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main %}
<li>
<div class="pub-row{% unless link.image %} no-teaser{% endunless %}">
  {% if link.image %}
  <div class="col-sm-3 abbr" style="position: relative; padding-right: 15px; padding-left: 15px;">
    <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" alt="{{ link.title }}" loading="lazy">
    {% if link.venue_short %}<abbr class="badge">{{ link.venue_short }}</abbr>{% endif %}
  </div>
  {% endif %}
  <div class="col-sm-9" style="position: relative; padding-right: 15px; padding-left: {% if link.image %}20px{% else %}0{% endif %};">
    {% assign title_link = link.doi | default: link.pdf | default: link.website | default: link.page %}
    <div class="title">{% if title_link %}<a href="{{ title_link }}" target="_blank" rel="noopener">{{ link.title }}</a>{% else %}{{ link.title }}{% endif %}</div>
    <div class="author">{{ link.authors }}</div>
    <div class="periodical"><em>{{ link.venue }}</em></div>
    {% if link.description %}<div class="pub-description">{{ link.description }}</div>{% endif %}
    <div class="links">
      {% if link.pdf %}<a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" style="font-size:12px;">PDF</a>{% endif %}
      {% if link.doi %}<a href="{{ link.doi }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" style="font-size:12px;">DOI</a>{% endif %}
      {% if link.code %}<a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" style="font-size:12px;">Code</a>{% endif %}
      {% if link.website or link.page %}<a href="{{ link.website | default: link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" style="font-size:12px;">Website</a>{% endif %}
      {% if link.bibtex %}<a href="{{ link.bibtex }}" class="btn btn-sm z-depth-0" role="button" target="_blank" rel="noopener" style="font-size:12px;">BibTeX</a>{% endif %}
      {% if link.notes %}<strong><i style="color:#e74d3c">{{ link.notes }}</i></strong>{% endif %}
    </div>
  </div>
</div>
</li>
<br>
{% endfor %}

</ol>
</div>
