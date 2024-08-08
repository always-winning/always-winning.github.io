---
layout: page
title: Tijdlijn
permalink: /tijdlijn/
---
<style>

  .direct-link {
    font-size: 9px;
    margin-top: 5px;
  }
  .direct-link a {
    text-decoration: none;
    color: #418756;
  }
  
  .timeline {
    position: relative;
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px 0;
    font-size: 14px;
  }
  .timeline::after {
    content: '';
    position: absolute;
    width: 2px;
    background-color: #418756;
    top: 0;
    bottom: 0;
    left: 50%;
    margin-left: -1px;
  }
  .timeline-item {
    padding: 5px 30px;
    position: relative;
    background-color: inherit;
    width: 50%;
    box-sizing: border-box;
  }
  .timeline-item::after {
    content: '';
    position: absolute;
    width: 20px;
    height: 20px;
    background-color: white;
    border: 3px solid #418756;
    top: 22px;
    border-radius: 50%;
    z-index: 1;
  }
  .left {
    left: 0;
  }
  .right {
    left: 50%;
  }
  .left::after {
    right: -10px;
  }
  .right::after {
    left: -10px;
  }
  .content {
    padding: 15px 20px;
    background-color: white;
    position: relative;
    border-radius: 6px;
    border: 1px solid #418756;
  }
  .left .content::before {
    content: " ";
    height: 0;
    position: absolute;
    top: 18px;
    width: 0;
    z-index: 1;
    right: -10px;
    border: medium solid #418756;
    border-width: 10px 0 10px 10px;
    border-color: transparent transparent transparent #418756;
  }
  .right .content::before {
    content: " ";
    height: 0;
    position: absolute;
    top: 18px;
    width: 0;
    z-index: 1;
    left: -10px;
    border: medium solid #418756;
    border-width: 10px 10px 10px 0;
    border-color: transparent #418756 transparent transparent;
  }
  .content h2 {
    font-size: 16px;
    margin-bottom: 5px;
  }
  .content h3 {
    font-weight: bold;
    font-size: 16px;
    margin-bottom: 5px;
  }
  .content p {
    font-size: 14px;
    margin-bottom: 0;
  }
  @media screen and (max-width: 800px) {
    .timeline::after {
      left: 31px;
    }
    .timeline-item {
      width: 100%;
      padding-left: 70px;
      padding-right: 25px;
    }
    .timeline-item::after {
      left: 21px;
    }
    .left::after {
      left: 21px;
    }
    .right {
      left: 0%;
    }
    .left .content::before,
    .right .content::before {
      left: -10px;
      border-width: 10px 10px 10px 0;
      border-color: transparent #418756 transparent transparent;
    }
  }
</style>


De juridische strijd tussen Nederlandse gokkers en online casino's is het resultaat van jarenlang illegaal opereren van deze bedrijven in Nederland. Voor 1 oktober 2021 was online gokken in Nederland verboden, maar veel buitenlandse casino's, vaak gevestigd in Malta vanwege de gunstige belastingwetten en soepele regelgeving, boden hun diensten toch aan Nederlandse spelers aan. Met de legalisering van online gokken in Nederland kwam de mogelijkheid voor gedupeerde spelers om hun verloren geld terug te vorderen. Dit leidde tot een golf van rechtszaken, waarbij de rechtmatigheid van de kansspelovereenkomsten en de zorgplicht van de casino's centraal staan. De Maltese gokwet Bill 55, die gokbedrijven beschermt tegen buitenlandse vonnissen, voegt een extra laag complexiteit toe aan de situatie.


<div class="timeline">
  {% assign events = site.data.timeline %}
  {% for event in events %}
    <div class="timeline-item {% cycle 'left', 'right' %}" id="{{ event.id }}">
      <div class="content">
        <h2>{{ event.date }}</h2>
        <h3>{{ event.title }}</h3>
        <p>{{ event.description | markdownify}}</p>
        <p class="direct-link">
          <a href="#{{ event.id }}">Directe link</a>
        </p>
      </div>
    </div>
  {% endfor %}
</div>
