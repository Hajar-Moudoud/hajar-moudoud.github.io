---
layout: single
title: "Events"
permalink: /events/
author_profile: false
---

{% include base_path %}

<div class="events-container">
  <!-- Large Featured Event -->
  {% assign featured_event = site.events | where: "type", "featured" | first %}
  {% if featured_event %}
  <div class="featured-event">
    <div class="event-content">
      <div class="event-date">
        <span class="year">{{ featured_event.date | date: "%Y" }}</span>
      </div>
      <div class="event-details">
        <h2 class="event-title">{{ featured_event.title }}</h2>
        <p class="event-description">{{ featured_event.content | strip_html | truncate: 200 }}</p>
        {% assign featured_content_length = featured_event.content | strip_html | size %}
        {% if featured_content_length > 200 %}
        <a href="{{ featured_event.url | relative_url }}" class="read-more">Read more →</a>
        {% endif %}
        <div class="event-meta">
          <div class="event-venue">
            <h3>{{ featured_event.venue }}</h3>
            <p>{{ featured_event.date | date: "%b %d, %Y" }} — {{ featured_event.location }}</p>
          </div>
          {% if featured_event.logo %}
          <div class="event-logo">
            <img src="{{ base_path }}/images/{{ featured_event.logo }}" alt="{{ featured_event.venue }}" class="venue-logo">
          </div>
          {% endif %}
        </div>
      </div>
    </div>
  </div>
  {% endif %}

  <!-- Regular Events List -->
  <div class="events-list">
    {% assign regular_events = site.events | where: "type", "regular" | sort: "date" | reverse %}
    {% for event in regular_events %}
    <div class="event-item">
      <div class="event-info">
        <h3 class="event-title">{{ event.title }}</h3>
        <p class="event-description">{{ event.content | strip_html | truncate: 150 }}</p>
        {% assign content_length = event.content | strip_html | size %}
        {% if content_length > 150 %}
        <a href="{{ event.url | relative_url }}" class="read-more">Read more →</a>
        {% endif %}
        <div class="event-meta">
          <span class="event-date">{{ event.date | date: "%b %d, %Y" }}</span> —
          <span class="event-location">{{ event.location }}</span>
        </div>
      </div>
      {% if event.logo %}
      <div class="event-logo">
        <img src="{{ base_path }}/images/{{ event.logo }}" alt="{{ event.venue }}" class="venue-logo">
      </div>
      {% endif %}
    </div>
    {% endfor %}
  </div>
</div>