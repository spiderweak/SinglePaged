---
title: "Village associatif"
bg: villageasso
color : white
border-color: acces
fa-icon: group
---

<div class="section-lines section-top section-left"></div>
{% for group in site.data.assoc %}
  {% capture thecycle %}{% cycle 'even', 'odd' %}{% endcapture %}
  {% if thecycle == 'odd' %}
  {% if group == site.data.assoc.last %}
  <div class="activity section-left">
  {% else %}
  <div class="activity section-left section-bottom">
  {% endif %}
    <div class="row activity-info-wrapper valign-wrapper">
      <div class="col m3 activity-img valign">
        <img  src="img/{{group.image}}" alt="{{ group.title }}">
      </div>
      <div class="col m9 activity-info">
        <h4 class="activity-title"> {{ group.title }} </h4>
        <p class="col m12 activity-desc"> {{ group.text }} </p>
        {% if group.website %}
        <a class="waves-effect waves-light btn bg-{{ page.border-color }}" href="{{ group.website }}" target="blank">Leur site web</a>
        {% endif %}
        {% if group.funding %}
        <a class="waves-effect waves-light btn bg-{{ page.border-color }}" href="{{ group.funding }}" target="blank">Donnez</a>
        {% endif %}
      </div>
    </div>
  </div>
  {% else %}
  {% if group == site.data.assoc.last %}
  <div class="activity section-right">
  {% else %}
  <div class="activity section-right section-bottom">
  {% endif %}
    <div class="row activity-info-wrapper valign-wrapper">
      <div class="col m9 activity-info">
        <div class="col m3 activity-img valign hide-on-med-and-up">
          <img  src="img/{{group.image}}" alt="{{group.title}}">
        </div>
        <h4 class="activity-title"> {{ group.title }} </h4>
        <p class="col m12 activity-desc">{{ group.text }} </p>
        {% if group.website %}
        <a class="waves-effect waves-light btn bg-{{ page.border-color }}" href="{{ group.website }}" target="blank">Leur site web</a>
        {% endif %}
        {% if group.funding %}
        <a class="waves-effect waves-light btn bg-{{ page.border-color }}" href="{{ group.funding }}" target="blank">Donnez</a>
        {% endif %}
      </div>
      <div class="col m3 activity-img valign hide-on-small-only">
        <img  src="img/{{group.image}}" alt="{{group.title}}">
      </div>
    </div>
  </div>
  {% endif %}
{% endfor %}
{% if thecycle == 'even' %}
<div class="section-lines section-bottom section-left"></div>
  {% else %}
<div class="section-lines section-bottom section-right"></div>
{% endif %}
