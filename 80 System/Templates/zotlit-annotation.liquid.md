{% bq %}
{{ zt.imgLink | embed }}{{ zt.text }}
{% if zt.comment %}

→ *{{ zt.comment }}*
{% endif %}
{% if zt.pageLabel %}

*Page {{ zt.pageLabel }}*
{% endif %}
{% endbq %}

^zt-{{ zt.key }}