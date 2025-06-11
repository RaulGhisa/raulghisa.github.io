---
layout: default
title: Home
---

# {{ site.author.name }}

<div class="profile-section">
  <div class="profile-image">
    <img src="{{ site.author.photo | default: '/assets/images/profile.jpg' }}" alt="Profile photo" />
  </div>
  <div class="profile-info">
    <h2>PhD Student in Robotics</h2>
    <p><strong>{{ site.author.department | default: "Department of Computer Science" }}</strong><br>
    {{ site.author.university | default: "University Name" }}</p>
    
    <div class="contact-links">
      <a href="mailto:{{ site.author.email }}"><i class="fas fa-envelope"></i> Email</a>
      {% if site.author.cv %}<a href="{{ site.author.cv }}"><i class="fas fa-file-pdf"></i> CV</a>{% endif %}
      {% if site.author.google_scholar %}<a href="{{ site.author.google_scholar }}"><i class="ai ai-google-scholar"></i> Scholar</a>{% endif %}
      {% if site.author.github %}<a href="https://github.com/{{ site.author.github }}"><i class="fab fa-github"></i> GitHub</a>{% endif %}
      {% if site.author.twitter %}<a href="https://twitter.com/{{ site.author.twitter }}"><i class="fab fa-twitter"></i> Twitter</a>{% endif %}
    </div>
  </div>
</div>

## About

I'm a PhD student working on **robotic failures and fault tolerance**. My research focuses on understanding why robots fail and developing systems that can recover from failures gracefully.

{{ site.bio | default: "I'm interested in making robots more reliable and robust in real-world environments. My work spans failure detection, diagnosis, and recovery mechanisms in autonomous systems." }}

**Advisor**: {{ site.author.advisor | default: "Prof. [Advisor Name]" }}

---

## Research Focus

- **Robotic Failure Analysis**: Understanding failure modes in autonomous systems
- **Fault Detection & Diagnosis**: Real-time monitoring and failure identification
- **Recovery Mechanisms**: Developing strategies for graceful degradation and recovery
- **System Reliability**: Building more robust robotic architectures

---

## Recent Posts

{% assign sorted_posts = site.posts | sort: 'date' | reverse %}
{% for post in sorted_posts limit:8 %}
<div class="post-item">
  <div class="post-date">{{ post.date | date: "%b %Y" }}</div>
  <div class="post-content">
    <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
    <p>{{ post.excerpt | strip_html | truncatewords: 25 }}</p>
    {% if post.tags %}
    <div class="post-tags">
      {% for tag in post.tags %}
      <span class="tag">{{ tag }}</span>
      {% endfor %}
    </div>
    {% endif %}
  </div>
</div>
{% endfor %}

{% if site.posts.size == 0 %}
<div class="post-item">
  <div class="post-date">Jan 2025</div>
  <div class="post-content">
    <h3><a href="#">Failure Modes in Autonomous Navigation Systems</a></h3>
    <p>An analysis of common failure patterns observed in mobile robot navigation and their underlying causes...</p>
    <div class="post-tags">
      <span class="tag">navigation</span>
      <span class="tag">failure-analysis</span>
    </div>
  </div>
</div>

<div class="post-item">
  <div class="post-date">Dec 2024</div>
  <div class="post-content">
    <h3><a href="#">Recovery Strategies for Manipulation Failures</a></h3>
    <p>Exploring different approaches robots can use to recover from grasping and manipulation errors...</p>
    <div class="post-tags">
      <span class="tag">manipulation</span>
      <span class="tag">recovery</span>
    </div>
  </div>
</div>

<div class="post-item">
  <div class="post-date">Nov 2024</div>
  <div class="post-content">
    <h3><a href="#">Sensor Failure Detection in Real-Time</a></h3>
    <p>Methods for detecting when sensors provide unreliable data and how to handle sensor degradation...</p>
    <div class="post-tags">
      <span class="tag">sensors</span>
      <span class="tag">fault-detection</span>
    </div>
  </div>
</div>
{% endif %}

<p><a href="{{ '/posts/' | relative_url }}">→ View all posts</a></p>

---

## Publications

{% if site.publications %}
{% for pub in site.publications %}
<div class="publication">
  <h4>{{ pub.title }}</h4>
  <p class="authors">{{ pub.authors }}</p>
  <p class="venue"><em>{{ pub.venue }}</em>{% if pub.year %}, {{ pub.year }}{% endif %}</p>
  {% if pub.status %}<p class="status">{{ pub.status }}</p>{% endif %}
  {% if pub.links %}
  <div class="pub-links">
    {% for link in pub.links %}
    <a href="{{ link.url }}" class="pub-link">{{ link.name }}</a>
    {% endfor %}
  </div>
  {% endif %}
</div>
{% endfor %}
{% else %}
<div class="publication">
  <h4>Robust Failure Recovery in Multi-Robot Systems</h4>
  <p class="authors"><strong>{{ site.author.name | default: "Your Name" }}</strong>, {{ site.author.advisor | default: "Advisor Name" }}</p>
  <p class="venue"><em>IEEE International Conference on Robotics and Automation (ICRA)</em>, 2025</p>
  <p class="status">Under Review</p>
  <div class="pub-links">
    <a href="#" class="pub-link">PDF</a>
    <a href="#" class="pub-link">Code</a>
  </div>
</div>

<div class="publication">
  <h4>Learning from Robot Failures: A Data-Driven Approach</h4>
  <p class="authors"><strong>{{ site.author.name | default: "Your Name" }}</strong>, Co-author Name, {{ site.author.advisor | default: "Advisor Name" }}</p>
  <p class="venue"><em>Workshop on Robot Learning (WRL)</em>, 2024</p>
  <div class="pub-links">
    <a href="#" class="pub-link">PDF</a>
    <a href="#" class="pub-link">Poster</a>
  </div>
</div>
{% endif %}

---

## Contact

**Email**: [{{ site.author.email }}](mailto:{{ site.author.email }})  
**Office**: {{ site.author.office | default: "Graduate Student Office, Robotics Lab" }}

---

<style>
.profile-section {
  display: flex;
  gap: 2rem;
  margin-bottom: 2rem;
  align-items: flex-start;
}

.profile-image img {
  width: 180px;
  height: 180px;
  object-fit: cover;
  border-radius: 8px;
}

.profile-info h2 {
  margin-top: 0;
  color: #2c3e50;
}

.contact-links {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  margin-top: 1rem;
}

.contact-links a {
  text-decoration: none;
  padding: 0.4rem 0.8rem;
  background-color: #f8f9fa;
  border-radius: 4px;
  color: #495057;
  transition: background-color 0.2s;
  font-size: 0.9rem;
}

.contact-links a:hover {
  background-color: #e9ecef;
}

.post-item {
  display: flex;
  gap: 1rem;
  margin-bottom: 1.5rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid #eee;
}

.post-date {
  min-width: 80px;
  font-size: 0.9rem;
  color: #666;
  font-weight: 500;
}

.post-content {
  flex: 1;
}

.post-content h3 {
  margin: 0 0 0.5rem 0;
  font-size: 1.1rem;
}

.post-content h3 a {
  color: #2c3e50;
  text-decoration: none;
}

.post-content h3 a:hover {
  color: #3498db;
}

.post-content p {
  margin: 0.5rem 0;
  color: #555;
  line-height: 1.5;
}

.post-tags {
  margin-top: 0.5rem;
}

.tag {
  display: inline-block;
  background-color: #e9ecef;
  color: #495057;
  padding: 0.2rem 0.5rem;
  border-radius: 3px;
  font-size: 0.8rem;
  margin-right: 0.5rem;
}

.publication {
  margin-bottom: 1.5rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid #eee;
}

.publication h4 {
  margin-bottom: 0.5rem;
  color: #2c3e50;
  font-size: 1rem;
}

.authors {
  margin: 0.25rem 0;
  color: #555;
  font-size: 0.9rem;
}

.venue {
  margin: 0.25rem 0;
  color: #666;
  font-size: 0.9rem;
}

.status {
  margin: 0.25rem 0;
  color: #e67e22;
  font-style: italic;
  font-size: 0.85rem;
}

.pub-links {
  margin-top: 0.5rem;
}

.pub-link {
  display: inline-block;
  margin-right: 0.8rem;
  padding: 0.2rem 0.6rem;
  background-color: #3498db;
  color: white;
  text-decoration: none;
  border-radius: 3px;
  font-size: 0.8rem;
}

.pub-link:hover {
  background-color: #2980b9;
}

@media (max-width: 768px) {
  .profile-section {
    flex-direction: column;
    text-align: center;
  }
  
  .contact-links {
    justify-content: center;
  }
  
  .post-item {
    flex-direction: column;
    gap: 0.5rem;
  }
  
  .post-date {
    min-width: unset;
  }
}
</style>