---
layout: page
title: Сотрудники
permalink: /employees/
navbar: true
---
{% for empl in site.data.employees %}
	{% assign name = empl[0] %}
	{% assign emp = empl[1] %}

	{% if emp.former %}{% continue %}{% endif %}	
<h3><a href="{{site.baseurl}}/employees/{{name}}">
{% if emp.firstname %}{{emp.firstname}}{% endif %}{% if emp.patronymic %} {{emp.patronymic}}{% endif %}{% if emp.surname %} {{emp.surname}}{% endif %}</a>{% if emp.degree %}<i>, {{emp.degree}}</i>{% endif %}{% if emp.position %}<i>, {{emp.position}}</i>{% endif %}</h3>

	{% if emp.image %}
<p align="center"><img src="{{site.baseurl}}/img/employees/{{emp.image}}"></img></p>
	{% endif %}

	{% if site.data.bio[name].plain %}
<p>{{site.data.bio[name].plain }}</p>
	{% endif %} 

	{% if emp.email %}
<p>e-mail <a href="mailto:{{emp.email}}">{{emp.email}}</a></p>
	{% endif %}

	{% if emp.homephone %}
<p>тел. {{emp.homephone}} (дом.) </p>
	{% endif %}

	{% if emp.cellphone %}
<p>тел. {{emp.cellphone}} (моб.) </p>
	{% endif %}

	{% if emp.workphone %}
<p>тел. {{emp.workphone}} (раб.) </p>
	{% endif %}

	{% if emp.fax %}
<p>факс {{emp.fax}}</p>
	{% endif %}
---
{% endfor %}
