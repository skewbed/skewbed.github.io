---
layout: post
title:  "ZZ-CT Beginner Algs"
date:   2016-08-21 17:00:00
categories: main
---

<section class="algs">
  {% for alg in site.zzct-beg %}
    <div class="alg">
      <img src="http://stachu.cubing.net/v/visualcube.php?fmt=png&size=960&view=plan&sch=yddydd&case={{ alg }}" onclick="imgClick(event)">
      <div>{{ alg }}</div>
    </div>
  {% endfor %}
</section>

<section class="algs">
  {% for alg in site.lc-coll %}
    <div class="alg">
      {% if alg == "U2 x (R' U R U')(R' U R U')(R' U R U')"%}
      <img src="http://stachu.cubing.net/v/visualcube.php?fmt=png&size=960&view=plan&sch=brwgoy&case={{ alg }}" onclick="imgClick(event)">
      {% else %}
      <img src="http://stachu.cubing.net/v/visualcube.php?fmt=png&size=960&view=plan&case={{ alg }}" onclick="imgClick(event)">
      {% endif %}
      <div>{{ alg }}</div>
    </div>
  {% endfor %}
</section>

<section class="algs">
  {% for alg in site.oh-epll %}
    <div class="alg">
      <img src="http://stachu.cubing.net/v/visualcube.php?fmt=png&size=960&view=plan&stage=pll&case={{ alg }}" onclick="imgClick(event)">
      <div>{{ alg }}</div>
    </div>
  {% endfor %}
</section>

<script>
  window.onload = function() {
    if(localStorage.getItem("(R U2 R') U' (R U R' U') (R U' R')") == null) {
      [].slice.call(document.getElementsByClassName("alg")).forEach(function(a) {
        console.log("[[DEBUG]]")
        localStorage.setItem(a.innerText, "on");
      });
    } else {
      [].slice.call(document.getElementsByClassName("alg")).forEach(function(a) {
        if(localStorage.getItem(a.innerText) == "off") {
          a.children[0].className += " disabled";
        }
      });
    }
  }

  function imgClick(e) {
    <!-- console.log("[[IMGCLICK]]");
    if(e.target.className.indexOf("disabled") == -1) {
      console.log("[[DISABLE]]");
      e.target.className += "disabled";
      localStorage.setItem(e.target.parentElement.innerText, "off");
    } else {
      console.log("[[ENABLE]]");
      e.target.className = "";
      localStorage.setItem(e.target.parentElement.innerText, "on");
    } -->
  }
</script>
