---
layout: default
permalink: /electronics/
title: Electronics
h2: Engineering
---
<section50short>
<h2>Tinker away with electronic kits!</h2>
<p>Who doesn't like tinkering with electronic circuits to make LEDs light up and buzzers going off? The kits below give you everything you need if you like to play around with electronic components. Each one comes with enough to get you started, and there are many online resources that show you the many cool things you can do with these kits. You're only limited by your imagination!</p>
<p>If you build something cool, be sure to showcase it at the <a href="https://makerfaire.com/" target="_blank">Make Faire</a>, where you will also get inspired by others' creations!</p>
</section50short>
{% for comp in site.electronics %}  
<section50> 
  <h2 id="{{ comp.hash }}"><a href="{{ comp.toplink }}" target="_blank">{{ comp.heading }}</a></h2>

  <!-- Use capture to prevent outputting i -->
  {% capture _%}{% increment i %}{% endcapture %}
  {% assign mod = i | modulo:2 %}

  <!-- For even loop runs, put pic to left. Switch for odd -->
  {% if mod == 0 %}

    <div class="section50left">
    {% if comp.picsmall %}
      <img style="width:350px" src="{{ comp.pic }}">
    {% else %}
      <img src="{{ comp.pic }}">
    {% endif %}

    {% if comp.piccreator %}
      <div class="license">(
        <a href="{{ comp.piclink }}" target="_blank">Image</a>
        <a href="{{ comp.piclicense }}" target="_blank">licensed</a> from {{ comp.piccreator }}
        )</div>
    {% endif %}

    <h3> {{ comp.piccaption }} </h3>
    </div>

    <div class="section50right">
    <p style="font-size:18px"> {{ comp.description }} <br>
    <b>Grades:</b> {{ comp.grades }} </p>
    <ul class="compl2" style="line-height:1.75;">
      {{ comp.content }} 
    </ul>
    </div>

  {% else %}

    <div class="section50left">
    <p style="font-size:18px"> {{ comp.description }} <br>
    <b>Grades:</b> {{ comp.grades }} </p>
    <ul class="compl2" style="line-height:1.75;">
      {{ comp.content }} 
    </ul>
    </div>
 
    <div class="section50right">

    {% if comp.picsmall %}
      <img style="width:350px" src="{{ comp.pic }}">
    {% else %}
      <img src="{{ comp.pic }}">
    {% endif %}

    {% if comp.piccreator %}
      <div class="license">(
        <a href="{{ comp.piclink }}" target="_blank">Image</a>
        <a href="{{ comp.piclicense }}" target="_blank">licensed</a> from {{ comp.piccreator }}
        )</div>
    {% endif %}

    <h3> {{ comp.piccaption }} </h3>
    </div>

  {% endif %}

</section50>
<br>
{% endfor %}

