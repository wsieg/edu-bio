---
layout: single
title: Wortschatz (Substantive und Verben) Kapitel 1
permalink: /allemand_main/9klasse_main/wortschatz1_quiz
---

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="{{ site.baseurl }}/assets/css/style_flashcards_levels_quiz.css">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
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
    <div class="flashcard">
      <div class="front" id="front-side">
        <div class="french-word" id="french-word"></div>
        <div class="input-container">
          <input type="text" id="input-article" placeholder="Artikel" class="input-field1">
          <input type="text" id="input-word" placeholder="Wort" class="input-field2">
        </div>
        <div class="results">
          <div id="result-article" class="result-text1"></div>
          <div id="result-word" class="result-text2"></div>
        </div>
      </div>
    </div>
  </div>
  <div class="button-container">
    <button id="check-button" onclick="checkAnswer()">Überprüfen</button>
    <button id="next-button" onclick="updateFlashcard()">Suivant</button>
  </div>
</div>

<script>
// Define the flashcard data variable and field names
const flashcardData = {{ site.data.wortschatz_9_1 | jsonify }};
const varFront = 'fr';
const varBack = 'de';
const varArtikel = 'artikel_de';
const varPlural = 'plural_de_end';

let currentMemberIndex = Math.floor(Math.random() * flashcardData.length);
let selectedLevels = [1]; // By default, only level 1 is selected

// Initialize the flashcard with the first member's data
function initializeFlashcard() {
  updateFlashcard();
}

function updateFlashcard() {
  const filteredData = flashcardData.filter(item => selectedLevels.includes(parseInt(item.level)));
  if (filteredData.length === 0) {
    document.getElementById('french-word').innerText = 'No data available for selected level(s).';
    document.getElementById('input-article').disabled = true;
    document.getElementById('input-word').disabled = true;
    return;
  }
  document.getElementById('input-article').disabled = false;
  document.getElementById('input-word').disabled = false;

  currentMemberIndex = getRandomMemberIndex(filteredData); // Update currentMemberIndex with a new random index from filtered data
  const member = filteredData[currentMemberIndex]; // Get the member with the updated index
  document.getElementById('french-word').innerText = member[varFront];
  clearResults();
}

function checkAnswer() {
  const filteredData = flashcardData.filter(item => selectedLevels.includes(parseInt(item.level)));
  const member = filteredData[currentMemberIndex]; // Get the current member based on currentMemberIndex
  const inputArticle = document.getElementById('input-article').value.trim();
  const inputWord = document.getElementById('input-word').value.trim();

  const resultArticle = document.getElementById('result-article');
  const resultWord = document.getElementById('result-word');

  if (inputArticle.toLowerCase() === member[varArtikel].toLowerCase()) {
    resultArticle.style.color = 'green';
    resultArticle.innerHTML = `<i class="fa fa-check-circle" style="color: green;"></i> ${inputArticle}`;
  } else {
    resultArticle.style.color = 'red';
    resultArticle.innerHTML = `<i class="fa fa-times-circle" style="color:red;"></i> <s>${inputArticle}</s> <span style="color: #007BFF;">${member[varArtikel]}</span>`;
  }

  if (inputWord === member[varBack]) {
    resultWord.style.color = 'green';
    resultWord.innerHTML = `<i class="fa fa-check-circle" style="color:green;"></i> ${inputWord}`;
  } else {
    resultWord.style.color = 'red';
    resultWord.innerHTML = `<i class="fa fa-times-circle" style="color:red;"></i> <s>${inputWord}</s> <span style="color: #007BFF;">${member[varBack]}</span>`;
  }
}

// Function to get the next member index
function getRandomMemberIndex(filteredData) {
  let randomIndex;
  do {
    randomIndex = Math.floor(Math.random() * filteredData.length);
  } while (randomIndex === currentMemberIndex);
  return randomIndex;
}

function clearResults() {
  document.getElementById('input-article').value = '';
  document.getElementById('input-word').value = '';
  document.getElementById('result-article').innerText = '';
  document.getElementById('result-word').innerText = '';
}

// Function to toggle levels based on slider state
const level2Toggle = document.getElementById('level-2-toggle');
const level3Toggle = document.getElementById('level-3-toggle');

level2Toggle.addEventListener('change', function() {
  if (this.checked) {
    if (!selectedLevels.includes(2)) {
      selectedLevels.push(2);
    }
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
    if (!selectedLevels.includes(3)) {
      selectedLevels.push(3);
    }
  } else {
    selectedLevels = selectedLevels.filter(level => level !== 3);
  }
  updateFlashcard();
});

// Initialize the flashcard when the page loads
document.addEventListener('DOMContentLoaded', initializeFlashcard);
</script>
