---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

{% include base_path %}

<!-- New style rendering if publication categories are defined -->
{% if site.publication_category %}
  {% for category in site.publication_category  %}
    {% assign title_shown = false %}
    {% for post in site.publications reversed %}
      {% if post.category != category[0] %}
        {% continue %}
      {% endif %}
      {% unless title_shown %}
        <h2>{{ category[1].title }}</h2><hr />
        {% assign title_shown = true %}
      {% endunless %}
      {% include archive-single.html %}
    {% endfor %}
  {% endfor %}
{% else %}
  <h2>Featured Publications</h2>
  <hr />
  <div class="publication">
    <h3>“TinyLlama Chatbot for VIIT College”</h3>
    <p>
      Fine-tuned TinyLlama with 4-bit quantization and implemented RAG architecture for enhanced, up-to-date knowledge. 
      Used Baai embeddings model for generating embeddings.  
      <strong>Published in:</strong> IJRESM.
    </p>
  </div>
  <hr />
  <div class="publication">
    <h3>“Prediction of Optimal Joint Angles for Prosthetic Knee Design Using Gait Analysis”</h3>
    <p>
      Conducted under the guidance of Dr. Shehal Rathi. Evaluated RNN, Bidirectional LSTM, and Random Forest models to 
      predict joint angles with 95% accuracy, contributing to advancements in prosthetic design.  
      <strong>Featured in:</strong> IGI Global publication 
      <em>“Modern Digital Approaches to Care Technologies for Individuals with Disabilities.”</em>
    </p>
  </div>
{% endif %}
