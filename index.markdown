---
layout: default
title: Home
---

<div class="profile-section">
  <div class="profile-image">
    <img src="{{ site.author.photo | default: '/assets/images/profile.jpg' }}" alt="Profile photo" />
  </div>
  <div class="profile-info">
    <h2>{{ site.author.name }}</h2>
    <div class="contact-links">
      <a href="mailto:{{ site.author.email }}?subject=Hello"><i class="far fa-envelope" title="Email">&nbsp;</i>email</a> 
      {% if site.author.cv %}<a href="{{ site.author.cv }}"><i class="fas fa-file-pdf"></i> CV</a>{% endif %}
      {% if site.author.google_scholar %}<a href="{{ site.author.google_scholar }}"><i class="ai ai-google-scholar"></i> scholar</a>{% endif %}
      {% if site.author.github %}<a href="https://github.com/{{ site.author.github }}"><i class="fab fa-github"></i> github</a>{% endif %}
      {% if site.author.twitter %}<a href="https://twitter.com/{{ site.author.twitter }}"><i class="fab fa-twitter"></i> twitter</a>{% endif %}
    </div>
  </div>
</div>

## About

I'm a PhD student at University of Nottingham, working on robotic manipulation failures and making robots more reliable and robust in real-world environments. My research focuses on understanding why robots fail and developing systems that can recover from failures gracefully with human help.

**Advisor**: <a href="https://www.nottingham.ac.uk/computerscience/people/ayse.kucukyilmaz">{{ site.author.advisor_ayse }}</a>, <a href="https://www.nottingham.ac.uk/computerscience/People/luis.figueredo">{{ site.author.advisor_luis }}</a>, <a href="https://www.nottingham.ac.uk/computerscience/people/ender.ozcan">{{ site.author.advisor_ender }}</a>

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
<!-- <p><a href="{{ '/posts/' | relative_url }}">→ View all posts</a></p> -->

---

## Publications
{% for pub in site.publications %}
<div class="publication">
  <h4><a href="{{ pub.link }}">{{ pub.title }}</a></h4>
  <p class="authors">{{ pub.authors }}</p>
  <p class="venue"><em>{{ pub.venue }}</em>{% if pub.year %}, {{ pub.year }}{% endif %}</p>
  {% if pub.status %}<p class="status">{{ pub.status }}</p>{% endif %}
</div>
{% endfor %}

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
  border-radius: 5%;
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
  /* padding-bottom: 1rem; */
  /* border-bottom: 1px solid #eee; */
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
  /* padding-bottom: 1rem;
  border-bottom: 1px solid #eee; */
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
