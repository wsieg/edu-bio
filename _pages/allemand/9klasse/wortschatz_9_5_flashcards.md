---
layout: single
title: Wortschatz (Substantive und Verben) Kapitel 5
permalink: /allemand_main/9klasse_main/wortschatz5_lernkarten
classes: wide
---

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="{{ site.baseurl }}/assets/css/style_flashcards_levels.css">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css">
</head>

<div class="container">
  <div class="switch-container">
    <div>
      <div class="switch-label">Niveau 2</div>
      <label class="switch">
        <input type="checkbox" id="level-2-toggle">
        <span class="slider round"></span>
      </label>
    </div>
    <div>
      <div class="switch-label">Niveau 3</div>
      <label class="switch">
        <input type="checkbox" id="level-3-toggle" disabled>
        <span class="slider round"></span>
      </label>
    </div>
  </div>
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
const flashcardData = {{ site.data.w9.wortschatz_9_5 | jsonify }};
console.log('Flashcard Data:', flashcardData);  // Debug statement
const varFront = 'fr';
const varBack = 'de';
const varArtikel = 'artikel_de';
const varPlural = "plural_de_end";
const varAudio = "audio";

let currentMemberIndex = Math.floor(Math.random() * flashcardData.length);
let selectedLevels = [1]; // By default, only level 1 is selected

// Initialize the flashcard with the first member's data
function initializeFlashcard() {
  updateFlashcard();
}

function updateFlashcard() {
  const filteredData = flashcardData.filter(item => selectedLevels.includes(Number(item.level)));
  console.log('Filtered Data:', filteredData);  // Debug statement
  if (filteredData.length === 0) {
    console.warn('No flashcards available for the selected levels.');
    document.getElementById('front-side').innerText = 'No flashcards available.';
    document.getElementById('back-side').innerText = '';
    return;
  }
  const randomIndex = Math.floor(Math.random() * filteredData.length);
  const member = filteredData[randomIndex];
  document.getElementById('front-side').innerText = member[varFront];
  setTimeout(() => {
    document.getElementById('back-side').innerHTML = `${member[varArtikel]} ${member[varBack]}, ${member[varPlural]}&nbsp;<i class="fas fa-volume-up" onclick="playAudio(event, '${member[varAudio]}')"></i>`;
  }, 300); // delay updating content to allow flip animation to complete
}

function flipCard() {
  document.querySelector('.flashcard').classList.toggle('flipped');
}

function getRandomMember() {
  const filteredData = flashcardData.filter(item => selectedLevels.includes(Number(item.level)));
  let randomIndex;
  do {
    randomIndex = Math.floor(Math.random() * filteredData.length);
  } while (randomIndex === currentMemberIndex);
  return randomIndex;
}

function nextMember() {
  if (document.querySelector('.flashcard').classList.contains('flipped')) {
    document.querySelector('.flashcard').classList.remove('flipped');
  }
  currentMemberIndex = getRandomMember();
  updateFlashcard();
}

// Function to toggle levels based on slider state
const level2Toggle = document.getElementById('level-2-toggle');
const level3Toggle = document.getElementById('level-3-toggle');

level2Toggle.addEventListener('change', function() {
  if (this.checked) {
    selectedLevels.push(2);
    level3Toggle.disabled = false;
  } else {
    selectedLevels = selectedLevels.filter(level => level !== 2 && level !== 3);
    level3Toggle.checked = false;
    level3Toggle.disabled = true;
  }
  updateFlashcard();
});

level3Toggle.addEventListener('change', function() {
  if (this.checked) {
    selectedLevels.push(3);
  } else {
    selectedLevels = selectedLevels.filter(level => level !== 3);
  }
  updateFlashcard();
});

// Function to play audio
function playAudio(event, url) {
  event.stopPropagation(); // Prevent the flashcard from flipping
  const audio = new Audio(url);
  audio.play();
}

// Initialize the flashcard when the page loads
document.addEventListener('DOMContentLoaded', initializeFlashcard);
</script>
