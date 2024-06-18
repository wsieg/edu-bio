---
layout: single
title: Wortschatz Kapitel 3
permalink: /allemand_main/neuvieme/wortschatz3
classes: wide
---


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
  width: 40vw;
  height: 55vh;
  text-align: center;
  cursor: pointer;
  position: relative;
  transform-style: preserve-3d;
  transition: transform 0.45s;
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
  font-size: 46px; /* Default font size for larger screens */
}
/* Adjust font size for smaller screens */
@media (max-width: 768px) {
  .flashcard .front, .flashcard .back {
    font-size: 22px; /* Adjusted font size for smaller screens */
  }
  .flashcard {
    width: 85vw;
    height: 200px
  }
}
/* Specific styles for front and back */
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
        <div class="front" id="front-side"></div>
        <div class="back" id="back-side"></div>
      </div>
    </div>
    <button onclick="nextMember()">Suivant</button>
  </div>

  <script>
    // Define the flashcard data variable and field names
    const flashcardData = {{ site.data.wortschatz_9_1 | jsonify }};
    const varFront = 'french';
    const varBack = 'german';
    const varArtikel = 'artikel_de';

    let currentMemberIndex = Math.floor(Math.random() * flashcardData.length);

    // Initialize the flashcard with the first member's data
    function initializeFlashcard() {
      document.getElementById('front-side').innerText = flashcardData[currentMemberIndex][varFront];
      document.getElementById('back-side').innerText = flashcardData[currentMemberIndex][varArtikel] + " " + flashcardData[currentMemberIndex][varBack];
    }

    function flipCard() {
      document.querySelector('.flashcard').classList.toggle('flipped');
    }

    function getRandomMember() {
      let randomIndex;
      do {
        randomIndex = Math.floor(Math.random() * flashcardData.length);
      } while (randomIndex === currentMemberIndex);
      return randomIndex;
    }

    function nextMember() {
      if (document.querySelector('.flashcard').classList.contains('flipped')) {
        document.querySelector('.flashcard').classList.remove('flipped');
      }
      currentMemberIndex = getRandomMember();
        document.getElementById('front-side').innerText = flashcardData[currentMemberIndex][varFront];
      setTimeout(() => {
        document.getElementById('back-side').innerText = flashcardData[currentMemberIndex][varArtikel] + " " + flashcardData[currentMemberIndex][varBack];
      }, 300); // delay updating content to allow flip animation to complete
    }

    // Initialize the flashcard when the page loads
    document.addEventListener('DOMContentLoaded', initializeFlashcard);
  </script>

