# Welcome to Growr!

# Introduction
{% assign doclist = site.pages | sort: 'url'  %}
       {% for doc in doclist %}
            {% if doc.name contains '.md' and doc.url contains '/introduction/' %}
- [{{ doc.title }}]({{ site.baseurl }}{{ doc.url }})
            {% endif %}
        {% endfor %}

# How it works
{% assign doclist = site.pages | sort: 'url'  %}
       {% for doc in doclist %}
            {% if doc.name contains '.md' and doc.url contains '/flows/' %}
- [{{ doc.title }}]({{ site.baseurl }}{{ doc.url }})
            {% endif %}
        {% endfor %}

# Architecture
{% assign doclist = site.pages | sort: 'url'  %}
       {% for doc in doclist %}
            {% if doc.name contains '.md' and doc.url contains '/architecture/' %}
- [{{ doc.title }}]({{ site.baseurl }}{{ doc.url }})
            {% endif %}
        {% endfor %}

