---
layout: page
title: Tijdlijn
permalink: /tijdlijn/
---
<style>
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
    background-color: #007bff;
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
    border: 3px solid #007bff;
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
    border: 1px solid #007bff;
  }
  .left .content::before {
    content: " ";
    height: 0;
    position: absolute;
    top: 18px;
    width: 0;
    z-index: 1;
    right: -10px;
    border: medium solid #007bff;
    border-width: 10px 0 10px 10px;
    border-color: transparent transparent transparent #007bff;
  }
  .right .content::before {
    content: " ";
    height: 0;
    position: absolute;
    top: 18px;
    width: 0;
    z-index: 1;
    left: -10px;
    border: medium solid #007bff;
    border-width: 10px 10px 10px 0;
    border-color: transparent #007bff transparent transparent;
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
      border-color: transparent #007bff transparent transparent;
    }
  }
</style>
<div class="timeline">
  {% assign events = site.data.timeline %}
  {% for event in events %}
    <div class="timeline-item {% cycle 'left', 'right' %}">
      <div class="content">
        <h2>{{ event.date }}</h2>
        <h3>{{ event.title }}</h3>
        <p>{{ event.description | markdownify}}</p>
      </div>
    </div>
  {% endfor %}
</div>