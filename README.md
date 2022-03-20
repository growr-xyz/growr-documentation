# Welcome to Growr!

# Where to start?
Repository for detailed protocol documentation
- [Introduction](/introduction/)
- [How it works](/flows/)
- [Architecture](/architecture/)

# Full index:
{% assign doclist = site.pages | sort: 'url'  %}
    <ul>
       {% for doc in doclist %}
            {% if doc.name contains '.md' %}
                <li><a href="{{ site.baseurl }}{{ doc.url }}">{{ doc.url }}</a></li>
            {% endif %}
        {% endfor %}
    </ul>
