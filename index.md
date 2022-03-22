# Welcome to Growr!

# Introduction
{% assign doclist = site.pages | sort: 'url'  %}
       {% for doc in doclist %}
            {% if doc.name contains '.md' and doc.url contains '/introduction/' %}
- [{{ doc.name }}]({{ site.baseurl }}{{ doc.url }})
            {% endif %}
        {% endfor %}

# How it works
{% assign doclist = site.pages | sort: 'url'  %}
       {% for doc in doclist %}
            {% if doc.name contains '.md' and doc.url contains '/flows/' %}
- [{{ doc.name }}]({{ site.baseurl }}{{ doc.url }})
            {% endif %}
        {% endfor %}

# Architecture
{% assign doclist = site.pages | sort: 'url'  %}
       {% for doc in doclist %}
            {% if doc.name contains '.md' and doc.url contains '/architecture/' %}
- [{{ doc.name }}]({{ site.baseurl }}{{ doc.url }})
            {% endif %}
        {% endfor %}

<script src="js/enable-mermaid.js"></script>
