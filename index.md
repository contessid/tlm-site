---
layout: home
title: "Trento Local Minimum"
permalink: /
---

<!-- Upcoming Sessions Table -->
<section class="upcoming-sessions">
  <h2>Upcoming Sessions</h2>
  <p class="upcoming-subtitle">Tentative schedule — topics and speakers may change.</p>

  <table class="session-table">
    <thead>
      <tr>
        <th>Date</th>
        <th>Type</th>
        <th>Title</th>
        <th>Details</th>
      </tr>
    </thead>
    <tbody>
      {% for s in site.data.upcoming.sessions %}
      <tr class="session-row session-{{ s.type | escape }}">
        <td>{% if s.date contains "TBD" %}{{ s.date }}{% else %}{{ s.date | date: "%b %d, %Y" }}{% endif %}{% if s.time %} <small>({{ s.time }})</small>{% endif %}</td>
        <td>
          {% if s.type == "talk" %}
            <span class="badge badge-talk">🎤 Talk</span>
          {% elsif s.type == "lab" %}
            <span class="badge badge-lab">🧪 Lab</span>
          {% endif %}
        </td>
        <td>
          <strong>{{ s.title | escape }}</strong>
          {% if s.speaker and s.speaker != "" %}
            <br><small>{{ s.speaker | escape }}</small>
          {% endif %}
          {% if s.paper and s.paper != "" %}
            <br><small>
              {% if s.paper_url and s.paper_url != "" %}
                <a href="{{ s.paper_url | escape }}" target="_blank">{{ s.paper | escape }}</a>
              {% else %}
                {{ s.paper | escape }}
              {% endif %}
            </small>
          {% endif %}
        </td>
        <td>
          {% if s.repo_url and s.repo_url != "" %}
            <a href="{{ s.repo_url | escape }}" target="_blank">Repo →</a>
          {% endif %}
          {% if s.notes and s.notes != "" %}
            <small>{{ s.notes | escape }}</small>
          {% endif %}
        </td>
      </tr>
      {% endfor %}
    </tbody>
  </table>
</section>
