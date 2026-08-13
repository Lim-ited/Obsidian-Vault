---
aliases:
Title: "{{title}}"
Author:
{% for c in creators | selectattr("creatorType", "equalto", "author") %}  - "[[{% if c.name %}{{c.name}}{% else %}{{c.firstName}} {{c.lastName}}{% endif %}]]"
{% endfor %}{% if publicationTitle %}Journal: "[[{{publicationTitle}}]]"
{% endif %}tags:
{% for t in tags %}  - {{t.tag | replace(" - ", "/") | replace(" ", "-")}}
{% endfor %}
Type: References
Status: Unread
Date Read:
Created: {{importDate | format('YYYY-MM-DD HH:mm')}}
---

>[!LINK] 
>**Zotero**:: [Open in Zotero]({{select}})
> {%- for attachment in attachments | filterby("path", "endswith", ".pdf") %}
>  [{{attachment.title}}](file://{{attachment.path | replace(" ", "%20")}})  {%- endfor -%}.

> [!Cite]
> {{bibliography}}

> [!Summary]
> **Contribution**::
>
> **Related**::{% for relation in relations | selectattr("citekey") %} [[@{{relation.citekey}}]]{% if not loop.last %}, {% endif%} {% endfor %}
> 

>[!Info] 
> **Title**:: {{title}}  
> **Year**:: {{date | format("YYYY")}}   
> **Citekey**:: {{citekey}} {%- if itemType %}  
> **itemType**:: {{itemType}}{%- endif %}{%- if itemType == "journalArticle" %}  
> **Journal**:: *{{publicationTitle}}* {%- endif %}{%- if volume %}  
> **Volume**:: {{volume}} {%- endif %}{%- if issue %}  
> **Issue**:: {{issue}} {%- endif %}{%- if itemType == "bookSection" %}  
> **Book**:: {{publicationTitle}} {%- endif %}{%- if publisher %}  
> **Publisher**:: {{publisher}} {%- endif %}{%- if place %}  
> **Location**:: {{place}} {%- endif %}{%- if pages %}   
> **Pages**:: {{pages}} {%- endif %}{%- if DOI %}  
> **DOI**:: {{DOI}} {%- endif %}{%- if ISBN %}  
> **ISBN**:: {{ISBN}} {%- endif %}   

>[!Abstract]
>{% if abstractNote %}
{{abstractNote}}
{% endif %}

---
# Notes
{% if markdownNotes %}{{markdownNotes}}{% endif %}

----
# Annotations
{%- macro calloutType(a) -%}
{%- if a.type == "note" -%}note
{%- elif a.colorCategory == "Red" -%}warning
{%- elif a.colorCategory == "Green" -%}tip
{%- elif a.colorCategory == "Blue" -%}info
{%- else -%}quote
{%- endif -%}
{%- endmacro -%}

{% persist "annotations" %}
{%- set newAnnotations = annotations | filterby("date", "dateafter", lastImportDate) %} {%- if newAnnotations.length > 0 %}
### Imported: {{importDate | format("YYYY-MM-DD HH:mm")}}
{% for a in newAnnotations %}
> [!{{calloutType(a)}}] p. {{a.pageLabel}}
{%- if a.annotatedText %}
> {{a.annotatedText}}
{%- endif %}
{%- if a.comment %}
>
> **Comment:** {{a.comment}}
{%- endif %}
{% endfor %}
{%- endif %}
{% endpersist %}
