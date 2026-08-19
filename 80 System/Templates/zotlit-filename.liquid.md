{{ zt.citationKey | default: zt.DOI | default: zt.title | default: zt.key }}{% suffix %}
<%= it.citekey ?? it.title ?? it.key %>.md

