---
layout: page
title: People
permalink: /people/
---

# People

## Past Speakers

{% if site.data.people.speakers.size > 0 %}

{% for speaker in site.data.people.speakers %}
<div class="person-card">
  <div class="person-info">
    <h3>{{ speaker.name | escape }}</h3>
    <p class="person-role">{{ speaker.affiliation | escape }}</p>
    <p>
      {% if speaker.session_url %}
        <a href="{{ speaker.session_url | escape }}">{{ speaker.talk | escape }}</a>
      {% else %}
        {{ speaker.talk | escape }}
      {% endif %}
      {% if speaker.slides_url %}
        &mdash; <a href="{{ speaker.slides_url | escape }}" target="_blank" rel="noopener noreferrer">Slides</a>
      {% endif %}
      <span class="person-date">{{ speaker.date }}</span>
    </p>
  </div>
</div>
{% endfor %}

{% else %}
<div class="about-card">
  <p><em>No past speakers yet — first session coming soon!</em></p>
</div>
{% endif %}

## Organizers

{% for person in site.data.people.organizers %}
<div class="person-card person-card--organizer">
  {% if person.image %}
  <img src="{{ person.image | relative_url }}" alt="{{ person.name | escape }}" class="person-avatar">
  {% endif %}
  <div class="person-info">
    <h3>{{ person.name | escape }}</h3>
    <p class="person-role">{{ person.role | escape }}</p>
    {% if person.bio %}<p>{{ person.bio | escape }}</p>{% endif %}
    <div class="person-links">
      {% if person.github %}
        <a href="{{ person.github | escape }}" target="_blank" rel="noopener noreferrer">GitHub</a>
      {% endif %}
      {% if person.linkedin %}
        <a href="{{ person.linkedin | escape }}" target="_blank" rel="noopener noreferrer">LinkedIn</a>
      {% endif %}
    </div>
  </div>
</div>
{% endfor %}
