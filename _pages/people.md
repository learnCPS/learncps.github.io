---
layout: page
title: People
stitle: People
permalink: /people/
description:
nav: true
nav_order: 4
---

<h2> Principal Investigator </h2>

<div class="card mt-3 p-3">
  <div class="row align-items-center">
    <div class="col-sm-3 text-center">
      <img src="{{ '/assets/img/profile_pic.png' | relative_url }}" alt="Christos Mavridis" class="img-fluid z-depth-1 rounded-circle" style="max-width: 140px;">
    </div>
    <div class="col-sm-9 pi-info">
      <div class="pi-info-text">
        <h3 class="card-title font-weight-medium mt-3 mt-sm-0">Christos Mavridis</h3>
        <p class="card-text mb-2">Assistant Professor, TU Wien Informatics</p>
        <p class="card-text mb-0">
          <a target="_blank" rel="noopener noreferrer" href="https://mavridischristos.github.io/">Personal website</a>
          &middot;
          <a target="_blank" rel="noopener noreferrer" href="https://informatics.tuwien.ac.at/people/christos-mavridis">TU Wien page</a>
        </p>
      </div>
      <button type="button" class="pi-bio-toggle" aria-expanded="false" aria-controls="pi-bio">
        <i class="fa-regular fa-id-card"></i>
        <span>Bio</span>
        <i class="fa-solid fa-chevron-down pi-bio-chevron"></i>
      </button>
    </div>
  </div>
  <!-- Bio panel sits below the photo/info row so opening it never moves the photo -->
  <div class="pi-bio" id="pi-bio">
    <div class="pi-bio-inner">
      <div class="pi-bio-box">
        <button type="button" class="pi-bio-copy" title="Copy bio to clipboard"><i class="fa-regular fa-copy"></i> <span>Copy</span></button>
        <div class="pi-bio-text">
          <p>Christos Mavridis received his Diploma in electrical and computer engineering from the National Technical University of Athens, Greece, in 2017, and the M.S. and Ph.D. degrees in electrical and computer engineering at the University of Maryland, College Park, MD, in 2021. His research interests include optimization, learning, and control theory.</p>
          <p>He is currently an Assistant Professor at TU Wien Informatics. He has worked as a postdoc at KTH Royal Institute of Technology, Stockholm, and as a research scientist with Nokia Bell Labs, NJ, Xerox Palo Alto Research Center, CA, and Ericsson Research, Stockholm.</p>
          <p>Dr. Mavridis is an IEEE member, and a member of IEEE/CSS Technical Committee on Security and Privacy. He has received the A. James Clark School of Engineering Distinguished Graduate Fellowship and the Ann G. Wylie Dissertation Fellowship in 2017 and 2021, respectively. He has been a finalist in the Qualcomm Innovation Fellowship US, San Diego, CA, 2018, and has received the Best Student Paper Award in the IEEE International Conference on Intelligent Transportation Systems (ITSC), 2021.</p>
        </div>
      </div>
    </div>
  </div>
</div>

<script>
  document.querySelectorAll(".pi-bio-toggle").forEach(function (toggle) {
    var panel = document.getElementById(toggle.getAttribute("aria-controls"));
    toggle.addEventListener("click", function () {
      var open = toggle.getAttribute("aria-expanded") !== "true";
      toggle.setAttribute("aria-expanded", open);
      panel.classList.toggle("open", open);
    });
  });
  document.querySelectorAll(".pi-bio-copy").forEach(function (button) {
    button.addEventListener("click", function () {
      var paragraphs = button.parentElement.querySelectorAll(".pi-bio-text p");
      var text = Array.prototype.map.call(paragraphs, function (p) { return p.textContent.trim(); }).join("\n\n");
      navigator.clipboard.writeText(text).then(function () {
        var original = button.innerHTML;
        button.innerHTML = '<i class="fa-solid fa-check"></i> <span>Copied</span>';
        button.classList.add("copied");
        setTimeout(function () {
          button.innerHTML = original;
          button.classList.remove("copied");
        }, 1500);
      });
    });
  });
</script>
