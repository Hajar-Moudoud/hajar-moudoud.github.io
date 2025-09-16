---
layout: single
title: "Students"
permalink: /students/
author_profile: false
---

<div class="students-container">
  <!-- PhD Students -->
  <div class="student-group">
    <h3>Ph.D. Students</h3>
    <div class="students-grid">
      {% assign phd_students = site.students | where: "type", "phd" | sort: "order" %}
      {% for student in phd_students %}
        <div class="student-card">
          <div class="student-avatar">
            <img src="{{ base_path }}/images/{{ student.photo }}" alt="{{ student.name }}" class="student-photo">
          </div>
          <div class="student-info">
            <h4 class="student-name">{{ student.name }}</h4>
            <p class="student-affiliation">{{ student.affiliation }}</p>
          </div>
        </div>
      {% endfor %}
    </div>
  </div>

  <!-- Master's Students -->
  <div class="student-group">
    <h3>Master's Students</h3>
    <div class="students-grid">
      {% assign msc_students = site.students | where: "type", "msc" | sort: "order" %}
      {% for student in msc_students %}
        <div class="student-card">
          <div class="student-avatar">
            <img src="{{ base_path }}/images/{{ student.photo }}" alt="{{ student.name }}" class="student-photo">
          </div>
          <div class="student-info">
            <h4 class="student-name">{{ student.name }}</h4>
            <p class="student-affiliation">{{ student.affiliation }}</p>
          </div>
        </div>
      {% endfor %}
    </div>
  </div>
</div>