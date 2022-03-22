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

```mermaid
sequenceDiagram
       participant Test1
       participant Test2
       Test1->>Test2
```

<script>
var config = {
    startOnLoad:true,
    theme: 'forest',
    flowchart:{
            useMaxWidth:false,
            htmlLabels:true
        }
};
mermaid.initialize(config);
window.mermaid.init(undefined, document.querySelectorAll('.language-mermaid'));
</script>

