---
layout: page
title: LLM in Materials and Chemistry March Madness Hackathon
menu_title: Home
menu_icon: house-door
---


{:.secondary}
# {{ site.event_date }}

<!-- REMOVE THIS SECTION when you use this template -->
<div class="lead" markdown="1">
Welcome to the LLM March Madness Materials / Chemistry Hackathon, a virtual hackathon designed to explore and showcase innovative applications of large language models in the fields of materials science and chemistry. Participants from diverse backgrounds, including scientists, engineers, developers, and students, will come together to leverage the power of AI to address complex challenges and unlock new frontiers in these rapidly evolving domains.
</div>
<!-- END of section to remove -->

<div class="aside">
    <div id="countdown" class="text-center"></div>
    <h2><i class="bi bi-calendar3"></i> Event timeline</h2>
    <dl>
        {% if site.registration_status == "soon" or site.registration_status == "open" or site.registration_status == "demo" %}
            <dt>{{ site.registration_opens_date }}</dt>
            <dd>
                Applications open for participants<br>
                {% if site.registration_status == 'open' %}
                    <a href="{{ site.baseurl }}{% link registration.md %}" class="btn">Register now</a>
                {% elsif site.registration_status == 'closed' %}
                    <a class="btn disabled">Registration has closed</a>
                {% elsif site.registration_status == 'soon' %}
                    <a class="btn disabled">Registration opens soon</a>
                {% endif %}
            </dd>
        {% endif %}

        <dt>{{ site.registration_closes_date }}</dt>
        <dd>Applications close</dd>

        <dt>{{ site.event_date }}</dt>
        <dd>Hackathon date</dd>
    </dl>
</div>

{% if site.event_status != "over" %}

During the event, teams will collaborate on projects aimed at harnessing the potential of large language models, in topics such as generating novel chemical compound structures, optimizing materials for specific applications, predicting material properties, automating synthesis routes, and more. By fusing state-of-the-art AI techniques with deep scientific knowledge, the hackathon aims to accelerate research and development in materials and chemistry.

Join us for the excitement of innovation, collaboration, and discovery as we push the boundaries of what's possible in materials science and chemistry using large language models. Prepare to be amazed by the groundbreaking solutions that will emerge from this cutting-edge hackathon!

## Logistics

The event will take place virtually, using a combination of **video
conferencing** (Zoom) for meetings and seminars, and **discussion forums**
(Slack, Miro). Slack, Miro, and Zoom links will be shared upon registration. 

## Prizes

Will be announced soon! 


{% else %}


{% endif %}


## Sponsors 

- The Materials Research Coordination Network (MaRCN)
- The Materials Data Facility
- The Materials Research Data Alliance (MaRDA)
