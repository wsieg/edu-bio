---
layout: single
title:
permalink: /allemand_main/
classes: wide
---

<head>
<style>
	* {
	box-sizing: border-box;
	}
	.container {
	width: 95%;
	margin: 0 auto; /* Center the container */
	}
	.column {
	float: left;
	width: 33.33%;
	padding: 5px;
	}
	.row::after {
	content: "";
	clear: both;
	display: table;
	}
	@media screen and (max-width: 500px) {
	.column {
		width: 100%;
	}
	}
	.card {
	box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
	transition: 0s;
	text-decoration: none!important; /* Remove underline from links */
	color: inherit; /* Inherit text color */
	display: block; /* Make the link block-level to cover the whole card */
	margin: 10px 0; /* Add some margin for spacing */
	}
	.card:hover {
	box-shadow: 0 8px 20px 0 rgba(0,0,0,0.45);
	}
	.card img {
	width: 100%;
	}
	.card h2 {
	margin: 0 0 18px 0;
	font-family: "Bebas Neue", cursive;
	font-size: 2.9rem;
	letter-spacing: 0.06em;
	}
	.container-content {
	padding: 0px 0px;
	text-align: center;
	}
</style>

</head>
<body>

Veuillez choisir votre degré.

<div class="container">
  <div class="row">
    <div class="column">
      <a href="{{ site.baseurl }}/allemand_main/9klasse_main/" class="card">
        <img src="{{ site.baseurl }}/assets/img/9klasse.webp" alt="Snow">
        <div class="container-content">
        </div>
      </a>
    </div>
    <div class="column">
      <a href="{{ site.baseurl }}/allemand_main/10klasse_main/" class="card">
        <img src="{{ site.baseurl }}/assets/img/img_avatar.png" alt="Snow">
      </a>
    </div>
    <div class="column">
      <a href="{{ site.baseurl }}/allemand_main/11klasse_main/" class="card">
        <img src="{{ site.baseurl }}/assets/img/img_avatar.png" alt="Snow">
        <div class="container-content">
          <!-- <h2><b>11. Klasse</b></h2> -->
        </div>
      </a>
    </div>
  </div>
</div>

</body>

