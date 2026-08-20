{% bq %}
*Page: {{ zt.pageLabel }}*
[Link to Zotero]({{ zt.backlink }})

{{ zt.imgLink | embed }}{{ zt.text }}
{% if zt.comment %}

→ *{{ zt.comment }}*
{% endif %}
^zotero-{{ zt.key }}
{% endbq %}