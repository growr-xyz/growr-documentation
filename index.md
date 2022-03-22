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
sequenceDiagram;
    participant Lender (via dApp);
    participant Pond Factory;
    activate Lender (via dApp);
    Lender (via dApp)->>+Pond Factory SC: Request pond creation;
    Note right of Lender (via dApp): Provide parameters, eligibility criteria, VR address;
    Pond Factory SC->>Pond Factory SC: Validate parameters;
    Pond Factory SC->>Pond SC: Create pond;
    Pond Factory SC-->>-Lender (via dApp): "Pond address";
    deactivate Lender (via dApp);
```
