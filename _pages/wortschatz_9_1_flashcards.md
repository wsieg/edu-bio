---
layout: single
title: Wortschatz Kapitel 1
permalink: /allemand_main/neuvieme/wortschatz1
classes: wide
---




<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
.flashcard-container {
  perspective: 1000px;
}
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.flashcard {
  width: 400px;
  height: 300px;
  text-align: center;
  cursor: pointer;
  position: relative;
  transform-style: preserve-3d;
  transition: transform 0.6s;
}
.flashcard.flipped {
  transform: rotateY(180deg);
}
.flashcard .front, .flashcard .back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px solid #ccc;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
}
.flashcard .front {
  background-color: #fff;
}
.flashcard .back {
  background-color: #f0f0f0;
  transform: rotateY(180deg);
}
button {
  margin-top: 20px;
  padding: 10px 20px;
  border: none;
  background-color: #007BFF;
  color: white;
  cursor: pointer;
  border-radius: 5px;
}
button:hover {
  background-color: #0056b3;
}
</style>


<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

</head>

<div class="container">
  <div class="flashcard-container">
    <div class="flashcard" onclick="flipCard()">
      <div class="front">{{ site.data.members[0].name }}</div>
      <div class="back">{{ site.data.members[0].github }}</div>
    </div>
  </div>
  <button onclick="nextMember()">Next Member</button>
</div>

  <script>
    const members = {{ site.data.members | jsonify }};
    let currentMemberIndex = 0;

    function flipCard() {
      document.querySelector('.flashcard').classList.toggle('flipped');
    }

    function getRandomMember() {
      let randomIndex;
      do {
        randomIndex = Math.floor(Math.random() * members.length);
      } while (randomIndex === currentMemberIndex);
      return randomIndex;
    }

    function nextMember() {
      currentMemberIndex = getRandomMember();
      document.querySelector('.flashcard .front').innerText = members[currentMemberIndex].name;
      document.querySelector('.flashcard .back').innerText = members[currentMemberIndex].github;
      if (document.querySelector('.flashcard').classList.contains('flipped')) {
        document.querySelector('.flashcard').classList.remove('flipped');
      }
    }
  </script>





