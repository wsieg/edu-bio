---
layout: single
title: Wortschatz Kapitel 2
permalink: /allemand_main/neuvieme/wortschatz2
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
      <div class="front">{{ site.data.flashcardData[0].varfront }}</div>
      <div class="back">{{ site.data.flashcardData[0].github }}</div>
    </div>
  </div>
  <button onclick="nextWord()">Suivant</button>
</div>

  <script>
  // Define the flashcard data variable
    const flashcardData = {{ site.data.members | jsonify }};
    let currentIndex = Math.floor(Math.random() * flashcardData.length);
    const varfront = "name"
    const varback = "github"

    function flipCard() {
      document.querySelector('.flashcard').classList.toggle('flipped');
    }

    function getRandomWord() {
      let randomIndex;
      do {
        randomIndex = Math.floor(Math.random() * flashcardData.length);
      } while (randomIndex === currentIndex);
      return randomIndex;
    }

    function nextWord() {
      currentIndex = getRandomWord();
      document.querySelector('.flashcard .front').innerText = flashcardData[currentIndex][varfront];
      document.querySelector('.flashcard .back').innerText = flashcardData[currentIndex][varback];
      if (document.querySelector('.flashcard').classList.contains('flipped')) {
        document.querySelector('.flashcard').classList.remove('flipped');
      }
    }

    // Initialize the flashcard when the page loads
    document.addEventListener('DOMContentLoaded', initializeFlashcard);
  </script>





