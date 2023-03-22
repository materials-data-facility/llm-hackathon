---
title: Hackathon registration
menu_title: Registration
menu_icon: clipboard-check
event_status:
 - soon
---

{:.lead}
Participation is FREE. 
We can't wait to see what you build!
{% if site.registration_status
== "soon" or site.registration_status == "demo" %}Registration opens on
{{ site.registration_opens_date }}.{% endif %} The closing date for applications
is {{ site.registration_closes_date }}.

<div class="aside" markdown="1">
This virtual event will require some commitment prior to and including the
Hackathon Event which will take part from {{ site.event_date }}.

{% if site.registration_status == "soon" or site.registration_status == "demo" %}
  <a class="btn disabled">Registration opens soon</a>
{% endif %}
{% if site.registration_status == "open" or site.registration_status == "demo" %}
  [Register now](https://www.eventbrite.com/e/llm-march-madness-materials-chemistry-hackathon-tickets-588455154207){:.btn target="_blank"}
{% endif %}
{% if site.registration_status == "closed" or site.registration_status == "demo" %}
  <a class="btn disabled">Registration has closed</a>
{% endif %}

The closing date for applications is {{ site.registration_closes_date }}.
</div>

The registration is open to all students, postdocs, and all problem-solvers.
Join our virtual hackathon and use your intellect and energy to make a difference. We need YOU to help solve urgent societal problems in materials and chemistry 🌟

Prior to the hackathon, this event will require that you think of problems you might want to solve and start forming teams. 
During the hackathon, the organizers will be available to support you. 
