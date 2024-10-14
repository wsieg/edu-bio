---
layout: single
title: Wortschatz (Substantive und Verben) Kapitel 2
permalink: /allemand_main/9klasse_main/wortschatz2_derdiedas
classes: wide
---

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="{{ site.baseurl }}/assets/css/style_flashcards_levels_derdiedas.css">
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
      <div class="front" id="front-side"></div>
    </div>
    <div class="button-container">
      <button class="artikel-button" id="button-der" onclick="checkAnswer('der')">der</button>
      <button class="artikel-button" id="button-die" onclick="checkAnswer('die')">die</button>
      <button class="artikel-button" id="button-das" onclick="checkAnswer('das')">das</button>
    </div>
  </div>
  <button onclick="nextMember()">weiter</button>
</div>

<script>
const flashcardData = {{ site.data.w9.wortschatz_9_2 | jsonify }};
const varBack = 'de';
const varArtikel = 'artikel_de';

let currentMemberIndex = Math.floor(Math.random() * flashcardData.length);
let selectedLevels = [1]; 

function initializeFlashcard() {
  updateFlashcard();
}

function updateFlashcard() {
  const filteredData = flashcardData.filter(item => selectedLevels.includes(item.level) && item.wortart === 'substantiv');
  const randomIndex = Math.floor(Math.random() * filteredData.length);
  const member = filteredData[randomIndex];
  document.getElementById('front-side').innerText = member[varBack];
  currentMemberIndex = randomIndex;

  resetButtons();
}

function resetButtons() {
  document.querySelectorAll('.artikel-button').forEach(button => {
    button.style.backgroundColor = '#007BFF';
    button.style.transform = 'scale(1)';
    button.style.opacity = '1';
    button.disabled = false;
  });
}

function checkAnswer(selectedArtikel) {
  const filteredData = flashcardData.filter(item => selectedLevels.includes(item.level) && item.wortart === 'substantiv');
  const member = filteredData[currentMemberIndex];
  const correctArtikel = member[varArtikel];

  document.querySelectorAll('.artikel-button').forEach(button => {
    button.disabled = true;
    if (button.innerText === selectedArtikel) {
      if (selectedArtikel === correctArtikel) {
        button.style.backgroundColor = 'green';
        button.style.transform = 'scale(1.1)';
      } else {
        button.style.backgroundColor = 'red';
        button.style.opacity = '0.6';
      }
    } else {
      button.style.opacity = '0.6';
      if (button.innerText === correctArtikel) {
        button.style.backgroundColor = 'green';
        button.style.transform = 'scale(1.1)';
      }
    }
  });
}

function getRandomMember() {
  const filteredData = flashcardData.filter(item => selectedLevels.includes(item.level) && item.wortart === 'substantiv');
  let randomIndex;
  do {
    randomIndex = Math.floor(Math.random() * filteredData.length);
  } while (randomIndex === currentMemberIndex);
  return randomIndex;
}

function nextMember() {
  currentMemberIndex = getRandomMember();
  updateFlashcard();
}

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

document.addEventListener('DOMContentLoaded', initializeFlashcard);
</script>
