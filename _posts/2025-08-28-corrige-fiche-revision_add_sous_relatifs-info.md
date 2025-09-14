---
layout: single
title: "Corrigé fiche révision - Nombres relatifs"
date: 2025-09-13
category: math
---

<style>
  .exo { margin: 1.25rem 0; padding-bottom: .5rem; border-bottom: 1px dashed #ddd; }
  .exo h3 { margin: 0 0 .5rem; }
  .prompt { margin: .25rem 0 .75rem; }
  .btn-reponse { cursor: pointer; border: 1px solid #444; background: #f8f8f8; padding: .35rem .6rem; border-radius: .5rem; font-size: .95rem; }
  .btn-reponse[aria-expanded="true"] { background: #eee; }
  .reponse { display: none; margin-top: .65rem; color: #b91c1c; }
  table { border-collapse: collapse; margin-top:.5rem; }
  td, th { border: 1px solid #999; padding: .35rem; text-align: center; }
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
  <h3>1) Placer des nombres relatifs</h3>
  <div class="prompt">Place les nombres suivants sur la droite numérique :  
  \(a=-7,\; b=-12,\; c=-3,\; d=-6,\; e=-3,5,\; f=-5,6,\; g=-7,8,\; h=-18\).</div>
  <button class="btn-reponse" onclick="toggleReponse('r1', this)" aria-expanded="false">Voir la réponse</button>
  <div class="reponse" id="r1">
    Sur l’axe gradué, de gauche à droite :  
    \(h=-18,\; b=-12,\; g=-7,8,\; a=-7,\; d=-6,\; f=-5,6,\; e=-3,5,\; c=-3\).
  </div>
</div>

<div class="exo" id="exo2">
  <h3>2) Calculs simples avec relatifs</h3>
  <div class="prompt">Effectue les calculs suivants :</div>
  <ol>
    <li>(-3) + 8 = <button class="btn-reponse" onclick="toggleReponse('r2a', this)">Voir la réponse</button>
      <div class="reponse" id="r2a"><strong>5</strong></div></li>
    <li>(-2) + (-6) = <button class="btn-reponse" onclick="toggleReponse('r2b', this)">Voir la réponse</button>
      <div class="reponse" id="r2b"><strong>-8</strong></div></li>
    <li>10 + (-10) = <button class="btn-reponse" onclick="toggleReponse('r2c', this)">Voir la réponse</button>
      <div class="reponse" id="r2c"><strong>0</strong></div></li>
    <li>3 − 10 = <button class="btn-reponse" onclick="toggleReponse('r2d', this)">Voir la réponse</button>
      <div class="reponse" id="r2d"><strong>-7</strong></div></li>
    <li>-2 − (-4) = <button class="btn-reponse" onclick="toggleReponse('r2e', this)">Voir la réponse</button>
      <div class="reponse" id="r2e"><strong>2</strong></div></li>
    <li>-4 − (-9) = <button class="btn-reponse" onclick="toggleReponse('r2f', this)">Voir la réponse</button>
      <div class="reponse" id="r2f"><strong>5</strong></div></li>
    <li>(-2) − (+5) = <button class="btn-reponse" onclick="toggleReponse('r2g', this)">Voir la réponse</button>
      <div class="reponse" id="r2g"><strong>-7</strong></div></li>
    <li>(+3) − (-4) = <button class="btn-reponse" onclick="toggleReponse('r2h', this)">Voir la réponse</button>
      <div class="reponse" id="r2h"><strong>7</strong></div></li>
    <li>(-2) + (-6) = <button class="btn-reponse" onclick="toggleReponse('r2i', this)">Voir la réponse</button>
      <div class="reponse" id="r2i"><strong>-8</strong></div></li>
    <li>(+6) − (+7) = <button class="btn-reponse" onclick="toggleReponse('r2j', this)">Voir la réponse</button>
      <div class="reponse" id="r2j"><strong>-1</strong></div></li>
    <li>7 + (+4) = <button class="btn-reponse" onclick="toggleReponse('r2k', this)">Voir la réponse</button>
      <div class="reponse" id="r2k"><strong>11</strong></div></li>
    <li>(-7) − (-4) = <button class="btn-reponse" onclick="toggleReponse('r2l', this)">Voir la réponse</button>
      <div class="reponse" id="r2l"><strong>-3</strong></div></li>
    <li>-7 − (+4) = <button class="btn-reponse" onclick="toggleReponse('r2m', this)">Voir la réponse</button>
      <div class="reponse" id="r2m"><strong>-11</strong></div></li>
    <li>-5 − (+8) = <button class="btn-reponse" onclick="toggleReponse('r2n', this)">Voir la réponse</button>
      <div class="reponse" id="r2n"><strong>-13</strong></div></li>
    <li>(+14) − (-23) = <button class="btn-reponse" onclick="toggleReponse('r2o', this)">Voir la réponse</button>
      <div class="reponse" id="r2o"><strong>37</strong></div></li>
    <li>(-4) − (+2) = <button class="btn-reponse" onclick="toggleReponse('r2p', this)">Voir la réponse</button>
      <div class="reponse" id="r2p"><strong>-6</strong></div></li>
    <li>(+6) − (+7) = <button class="btn-reponse" onclick="toggleReponse('r2q', this)">Voir la réponse</button>
      <div class="reponse" id="r2q"><strong>-1</strong></div></li>
    <li>(+6) − (+1) = <button class="btn-reponse" onclick="toggleReponse('r2r', this)">Voir la réponse</button>
      <div class="reponse" id="r2r"><strong>5</strong></div></li>
    <li>(+3) + (-6) = <button class="btn-reponse" onclick="toggleReponse('r2s', this)">Voir la réponse</button>
      <div class="reponse" id="r2s"><strong>-3</strong></div></li>
    <li>(-36) − (+27) = <button class="btn-reponse" onclick="toggleReponse('r2t', this)">Voir la réponse</button>
      <div class="reponse" id="r2t"><strong>-63</strong></div></li>
  </ol>
</div>

<div class="exo" id="exo3">
  <h3>3) Simplifier et calculer</h3>
  <ol>
    <li>6 + (-2) - 5 - (-4) + (-7) - (-1) = <button class="btn-reponse" onclick="toggleReponse('r3a', this)">Voir la réponse</button>
      <div class="reponse" id="r3a"><strong>-3</strong></div></li>
    <li>-3 - (-8) + (-2) - (-5) - 1 - (-7) = <button class="btn-reponse" onclick="toggleReponse('r3b', this)">Voir la réponse</button>
      <div class="reponse" id="r3b"><strong>14</strong></div></li>
    <li>-7 + (-5) + 2 - (-6) + (-4) - (-8) = <button class="btn-reponse" onclick="toggleReponse('r3c', this)">Voir la réponse</button>
      <div class="reponse" id="r3c"><strong>0</strong></div></li>
    <li>5 + (-9) + (-2) + 7 + (-3) - (-6) = <button class="btn-reponse" onclick="toggleReponse('r3d', this)">Voir la réponse</button>
      <div class="reponse" id="r3d"><strong>4</strong></div></li>
    <li>-9 - (-3) - 5 - (-1) + (-7) - (-4) = <button class="btn-reponse" onclick="toggleReponse('r3e', this)">Voir la réponse</button>
      <div class="reponse" id="r3e"><strong>-13</strong></div></li>
    <li>-2 - (-7) - (-3) + (-8) + 5 + (-9) = <button class="btn-reponse" onclick="toggleReponse('r3f', this)">Voir la réponse</button>
      <div class="reponse" id="r3f"><strong>-4</strong></div></li>
  </ol>
</div>

<div class="exo" id="exo4">
  <h3>4) Différences donnant +4</h3>
  <div class="prompt">Écrire 10 façons différentes d’obtenir +4 sous la forme d’une différence.</div>
  <button class="btn-reponse" onclick="toggleReponse('r4', this)">Voir la réponse</button>
  <div class="reponse" id="r4">
    Exemples possibles :  
    5−1, 6−2, 10−6, 0−(-4), -2−(-6), 8−4, 100−96, -10−(-14), 1,5−(-2,5), 50−46.
  </div>
</div>

<div class="exo" id="exo5">
  <h3>5) Classement décroissant</h3>
  <div class="prompt">Classer : \(+1,5;\; -9;\; -\frac{8}{4};\; +7^2;\; -3,03;\; -0,00051;\; +6^3;\; +121,4;\; -\frac{4}{7};\; 0\).</div>
  <button class="btn-reponse" onclick="toggleReponse('r5', this)">Voir la réponse</button>
  <div class="reponse" id="r5">
    \(+6^3 = 216\; >\; +121,4\; >\; +7^2 = 49\; >\; +1,5\; >\; 0\; >\; -0,00051\; >\; -\tfrac{4}{7}\; ≈ -0,57\; >\; -2\; >\; -3,03\; >\; -9\).
  </div>
</div>

<div class="exo" id="exo6">
  <h3>6) Problème</h3>
  <div class="prompt">Je pense à un nombre. J’ajoute -7, je prends la valeur absolue, j’obtiens 3. Quel est ce nombre ?</div>
  <button class="btn-reponse" onclick="toggleReponse('r6', this)">Voir la réponse</button>
  <div class="reponse" id="r6">
    Soit \(x\) le nombre. On a \(|x-7|=3\).  
    Donc \(x-7=3 \implies x=10\) ou \(x-7=-3 \implies x=4\).  
    <strong>Réponse : 4 ou 10.</strong>
  </div>
</div>

<div class="exo" id="exo7">
  <h3>7) Variation de population</h3>
  <div class="prompt">Population initiale : 209 habitants. Complète avec les naissances (+), décès (−), arrivées (+), départs (−).</div>
  <button class="btn-reponse" onclick="toggleReponse('r7', this)">Voir la réponse</button>
  <div class="reponse" id="r7">
    <ul>
      <li>Janvier : +2 −4 −1 = <strong>-3</strong></li>
      <li>Mars : +3 +1 = <strong>+4</strong></li>
      <li>Avril : +1 −2 +3 −4 = <strong>-2</strong></li>
      <li>Juin : +2 −1 = <strong>+1</strong></li>
      <li>Septembre : +1 −1 +5 −2 = <strong>+3</strong></li>
      <li>Octobre : +3 +3 −5 = <strong>+1</strong></li>
      <li>Décembre : +1 −1 +2 −8 = <strong>-6</strong></li>
    </ul>
    Variation totale = -3 +4 -2 +1 +3 +1 -6 = <strong>-2</strong>.  
    Donc population finale = 209 − 2 = <strong>207 habitants</strong>.
  </div>
</div>
