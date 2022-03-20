# Welcome to Growr!

# Where to start?
Repository for detailed protocol documentation
- [Introduction](/introduction/)
- [How it works](/flows/)
- [Architecture](/architecture/)

# Table of contents:
{% assign doclist = site.pages | sort: 'url'  %}
       {% for doc in doclist %}
            {% if doc.name contains '.md' %}
                - [{{ doc.url }}]({{ site.baseurl }}{{ doc.url }})
            {% endif %}
        {% endfor %}
