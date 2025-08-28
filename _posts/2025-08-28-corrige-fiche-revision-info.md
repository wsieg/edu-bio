---
layout: single
title: "Corrigé fiche révision"
date: 2025-08-27
category: math
---


<!-- Bloc HTML/Markdown prêt pour Jekyll : exercices + bouton "Voir la réponse" qui affiche la correction en rouge -->

<style>
  .exo { margin: 1.25rem 0; padding-bottom: .5rem; border-bottom: 1px dashed #ddd; }
  .exo h3 { margin: 0 0 .5rem; }
  .prompt { margin: .25rem 0 .75rem; }
  .btn-reponse { cursor: pointer; border: 1px solid #444; background: #f8f8f8; padding: .35rem .6rem; border-radius: .5rem; font-size: .95rem; }
  .btn-reponse[aria-expanded="true"] { background: #eee; }
  .reponse { display: none; margin-top: .65rem; color: #b91c1c; }
  table.placeval { border-collapse: collapse; width: 100%; max-width: 800px; }
  .placeval th, .placeval td { border: 1px solid #999; padding: .35rem; text-align: center; }
  .subtle { color: #666; font-weight: normal; }
</style>

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async
 src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>


<script>
  function toggleReponse(id, btn){
    const el = document.getElementById(id);
    const isOpen = el.style.display === 'block';
    el.style.display = isOpen ? 'none' : 'block';
    if(btn){ btn.setAttribute('aria-expanded', String(!isOpen)); }
  }
</script>

<div class="exo" id="exo1">
  <h3>1) PPMC et PGDC</h3>
  <div class="prompt">Trouve le <strong>PPMC</strong> et le <strong>PGDC</strong> des nombres suivants : <strong>156</strong> et <strong>204</strong>.</div>
  <button class="btn-reponse" onclick="toggleReponse('r1', this)" aria-expanded="false">Voir la réponse</button>
  <div class="reponse" id="r1">
    156 = 2<sup>2</sup> × 3 × 13, &nbsp; 204 = 2<sup>2</sup> × 3 × 17<br>
    <strong>PGDC</strong>(156, 204) = 2<sup>2</sup> × 3 = <strong>12</strong><br>
    <strong>PPMC</strong>(156, 204) = 2<sup>2</sup> × 3 × 13 × 17  = <strong>2'652</strong>
  </div>
</div>

<div class="exo" id="exo2">
  <h3>2) Priorité des opérations</h3>
  <div class="prompt">Effectue les calculs suivants en respectant la priorité des opérations.</div>
  <ol>
    <li>36 − 4 · 5 = <button class="btn-reponse" onclick="toggleReponse('r2a', this)" aria-expanded="false">Voir la réponse</button>
      <div class="reponse" id="r2a">36 − 20 = <strong>16</strong></div>
    </li>
    <li>(6<sup>2</sup> + 3<sup>2</sup>) · 2 = <button class="btn-reponse" onclick="toggleReponse('r2b', this)" aria-expanded="false">Voir la réponse</button>
      <div class="reponse" id="r2b">(36 + 9) · 2 = 45 · 2 = <strong>90</strong></div>
    </li>
    <li>18 : 3 · 2 − 4 = <button class="btn-reponse" onclick="toggleReponse('r2c', this)" aria-expanded="false">Voir la réponse</button>
      <div class="reponse" id="r2c">18 : 3 = 6, puis 6 · 2 = 12, et 12 − 4 = <strong>8</strong></div>
    </li>
    <li>(8 − 3) · 4 + 2<sup>2</sup> = <button class="btn-reponse" onclick="toggleReponse('r2d', this)" aria-expanded="false">Voir la réponse</button>
      <div class="reponse" id="r2d">5 · 4 + 4 = 20 + 4 = <strong>24</strong></div>
    </li>
    <li>\(\dfrac{20}{5}\) + (7<sup>2</sup> − 10) = <button class="btn-reponse" onclick="toggleReponse('r2e', this)" aria-expanded="false">Voir la réponse</button>
      <div class="reponse" id="r2e">4 + (49 − 10) = 4 + 39 = <strong>43</strong></div>
    </li>
    <li>\(\dfrac{45 − (12 : 3 + 2^2)}{5}\) = <button class="btn-reponse" onclick="toggleReponse('r2f', this)" aria-expanded="false">Voir la réponse</button>
      <div class="reponse" id="r2f">12 : 3 = 4, 2<sup>2</sup> = 4 → 45 − (4 + 4) = 45 − 8 = 37, puis 37 : 5 = <strong>7,4</strong></div>
    </li>
  </ol>
</div>

<div class="exo" id="exo3">
  <h3>3) Valeur de position</h3>
  <div class="prompt">Place les nombres suivants dans le tableau : 23,7 ; 12 ; 6,901 ; 1'235,01 ; 0,002 ; 198,03.</div>
  <button class="btn-reponse" onclick="toggleReponse('r3', this)" aria-expanded="false">Voir la réponse</button>
  <div class="reponse" id="r3">
    <table class="placeval">
      <thead>
        <tr>
          <th colspan="6">Partie entière <span class="subtle">(classe milliers | classe unités)</span></th>
          <th></th>
          <th colspan="3">Partie décimale</th>
        </tr>
        <tr>
          <th>C</th><th>D</th><th>U</th><th>C</th><th>D</th><th>U</th>
          <th>,</th>
          <th>Dixièmes</th><th>Centièmes</th><th>Millièmes</th>
        </tr>
      </thead>
      <tbody>
        <tr><td></td><td></td><td></td><td></td><td>2</td><td>3</td><td>,</td><td>7</td><td></td><td></td></tr>
        <tr><td></td><td></td><td></td><td></td><td>1</td><td>2</td><td>,</td><td></td><td></td><td></td></tr>
        <tr><td></td><td></td><td></td><td></td><td></td><td>6</td><td>,</td><td>9</td><td>0</td><td>1</td></tr>
        <tr><td></td><td></td><td>1</td><td>2</td><td>3</td><td>5</td><td>,</td><td>0</td><td>1</td><td></td></tr>
        <tr><td></td><td></td><td></td><td></td><td></td><td>0</td><td>,</td><td>0</td><td>0</td><td>2</td></tr>
        <tr><td></td><td></td><td></td><td>1</td><td>9</td><td>8</td><td>,</td><td>0</td><td>3</td><td></td></tr>
      </tbody>
    </table>
    <div class="subtle" style="margin-top:.35rem">Ordre des lignes (du haut vers le bas) : 23,7 ; 12 ; 6,901 ; 1'235,01 ; 0,002 ; 198,03.</div>
  </div>
</div>

<div class="exo" id="exo4">
  <h3>4) Comparer des décimaux</h3>
  <div class="prompt">Complète avec &lt;, &gt; ou =.</div>
  <ol>
    <li>4,53 <button class="btn-reponse" onclick="toggleReponse('r4a', this)" aria-expanded="false">Voir la réponse</button>
      <div class="reponse" id="r4a"><strong>&gt;</strong> 4,503</div>
    </li>
    <li>0,706 <button class="btn-reponse" onclick="toggleReponse('r4b', this)" aria-expanded="false">Voir la réponse</button>
      <div class="reponse" id="r4b"><strong>&gt;</strong> 0,67</div>
    </li>
    <li>12,1 <button class="btn-reponse" onclick="toggleReponse('r4c', this)" aria-expanded="false">Voir la réponse</button>
      <div class="reponse" id="r4c"><strong>=</strong> 12,100</div>
    </li>
    <li>5,09 <button class="btn-reponse" onclick="toggleReponse('r4d', this)" aria-expanded="false">Voir la réponse</button>
      <div class="reponse" id="r4d"><strong>&lt;</strong> 5,9</div>
    </li>
    <li>10 <button class="btn-reponse" onclick="toggleReponse('r4e', this)" aria-expanded="false">Voir la réponse</button>
      <div class="reponse" id="r4e"><strong>=</strong> 10,0</div>
    </li>
    <li>23'485,98 <button class="btn-reponse" onclick="toggleReponse('r4f', this)" aria-expanded="false">Voir la réponse</button>
      <div class="reponse" id="r4f"><strong>&lt;</strong> 23'485,981</div>
    </li>
  </ol>
</div>

<div class="exo" id="exo5">
  <h3>5) Arrondis</h3>
  <div class="prompt">Arrondis les nombres suivants.</div>
  <div style="display:grid; grid-template-columns: repeat(3, 1fr); gap: .75rem;">
    <div>
      <strong>à l'unité</strong>
      <ul>
        <li>49,5 ≈ <button class="btn-reponse" onclick="toggleReponse('r5a', this)" aria-expanded="false">Voir la réponse</button>
          <div class="reponse" id="r5a"><strong>50</strong></div>
        </li>
        <li>132,499 ≈ <button class="btn-reponse" onclick="toggleReponse('r5b', this)" aria-expanded="false">Voir la réponse</button>
          <div class="reponse" id="r5b"><strong>132</strong></div>
        </li>
        <li>7,51 ≈ <button class="btn-reponse" onclick="toggleReponse('r5c', this)" aria-expanded="false">Voir la réponse</button>
          <div class="reponse" id="r5c"><strong>8</strong></div>
        </li>
      </ul>
    </div>
    <div>
      <strong>au dixième</strong>
      <ul>
        <li>12,05 ≈ <button class="btn-reponse" onclick="toggleReponse('r5d', this)" aria-expanded="false">Voir la réponse</button>
          <div class="reponse" id="r5d"><strong>12,1</strong></div>
        </li>
        <li>3,149 ≈ <button class="btn-reponse" onclick="toggleReponse('r5e', this)" aria-expanded="false">Voir la réponse</button>
          <div class="reponse" id="r5e"><strong>3,1</strong></div>
        </li>
        <li>87,649 ≈ <button class="btn-reponse" onclick="toggleReponse('r5f', this)" aria-expanded="false">Voir la réponse</button>
          <div class="reponse" id="r5f"><strong>87,6</strong></div>
        </li>
      </ul>
    </div>
    <div>
      <strong>au centième</strong>
      <ul>
        <li>0,005 ≈ <button class="btn-reponse" onclick="toggleReponse('r5g', this)" aria-expanded="false">Voir la réponse</button>
          <div class="reponse" id="r5g"><strong>0,01</strong></div>
        </li>
        <li>45,675 ≈ <button class="btn-reponse" onclick="toggleReponse('r5h', this)" aria-expanded="false">Voir la réponse</button>
          <div class="reponse" id="r5h"><strong>45,68</strong></div>
        </li>
        <li>123,9949 ≈ <button class="btn-reponse" onclick="toggleReponse('r5i', this)" aria-expanded="false">Voir la réponse</button>
          <div class="reponse" id="r5i"><strong>123,99</strong></div>
        </li>
      </ul>
    </div>
  </div>
</div>

<div class="exo" id="exo6">
  <h3>6) Ordre croissant</h3>
  <div class="prompt">Classe les nombres suivants dans l'ordre croissant : 4,8 ; 4,75 ; 4,805 ; 4,705.</div>
  <button class="btn-reponse" onclick="toggleReponse('r6', this)" aria-expanded="false">Voir la réponse</button>
  <div class="reponse" id="r6">4,705 &lt; 4,75 &lt; 4,8 &lt; <strong>4,805</strong> (donc l'ordre croissant est 4,705 ; 4,75 ; 4,8 ; 4,805).</div>
</div>

<div class="exo" id="exo7">
  <h3>7) Opérations avec des décimaux</h3>
  <div class="prompt">Effectue les calculs suivants (en posant si nécessaire) :</div>
  <ul>
    <li>8,041 + 9,16 = <button class="btn-reponse" onclick="toggleReponse('r7a', this)" aria-expanded="false">Voir la réponse</button>
      <div class="reponse" id="r7a"><strong>17,201</strong></div>
    </li>
    <li>6,99 − 2,507 = <button class="btn-reponse" onclick="toggleReponse('r7b', this)" aria-expanded="false">Voir la réponse</button>
      <div class="reponse" id="r7b"><strong>4,483</strong></div>
    </li>
    <li>4,09 · 7,121 = <button class="btn-reponse" onclick="toggleReponse('r7c', this)" aria-expanded="false">Voir la réponse</button>
      <div class="reponse" id="r7c"><strong>29,12489</strong></div>
    </li>
  </ul>
</div>
