---
layout: page
title: Exec Board
description: Cat ipsum dolor sit amet, the door is opening! how exciting oh, it's you, meh. Brown cats with pink ears. Steal the warm chair right after you get up meoooow damn that dog pretend you want to go out but then don't. Kitty power you call this cat food yet fall asleep upside-down. 
image: assets/images/exec-bg.jpg
nav-menu: true
---

<link rel="stylesheet" src="{{ "/assets/css/exec.css" | absolute_url }}" />
<div id="main" class="alt">
<section id="one">
	<div class="inner">
		<header class="major">
			<h1>Executive Board</h1>
		</header>
        <div class="row">
            {% for member in site.data.exec %}
            {% assign n = forloop.index | modulo: 3 %}
            {% assign rem = forloop.length | modulo: 3 %}
            {% assign last3 = forloop.length | minus: 3 %}
            {% assign lastn = forloop.length | minus: rem %}
                {% if n==0 %}
                {% if rem==0 and forloop.last %}
                <div class="4u$ 12u$(small) exec-box last-row">
                {% else %}
                <div class="4u$ 12u$(small) exec-box">
                {% endif %}
                {% else %}
                {% if rem==0 and forloop.index > last3 %}
                <div class="4u 12u$(small) exec-box last-row">
                {% elsif rem!=0 and forloop.index > lastn %}
                <div class="4u 12u$(small) exec-box last-row">
                {% else %}
                <div class="4u 12u$(small) exec-box">
                {% endif %}
                {% endif %}
                <span class="image fit"><img src="{{ member.image | absolute_url }}" class="exec-image"/></span>
                <h3>{{member.position}}</h3>
                <h4>{{member.name}}</h4>
                <p>{{member.description}}</p>
            </div>
            {% endfor %}
        </div>
    </div>
</section>
<script>
    function resizeHandler(){
        var images = document.getElementsByClassName("exec-image");
        for(var i=0; i<images.length; i++)
        {
            var w = images[i].clientWidth;
            images[i].style.height = w+"px";
        }
    }
    
    window.addEventListener('resize', resizeHandler);
    window.addEventListener('load', resizeHandler);
</script>
</div>