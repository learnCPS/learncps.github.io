---
layout: page
permalink: /publications/
title: Publications
stitle: Publications
description: 
jyears: [2026,2025,2024,2023]
cyears: [2026,2025,2024,2023,2022,2021,2020,2019,2018]
byears: [2025]
pyears: [2019]
nav: true
nav_order: 2
---

<span style="font-family:monospace;">
Peer-Reviewed Publications, Book Chapters, Patents 
<br> (<a href="https://scholar.google.com/citations?user=msjXTH4AAAAJ&hl=en" title="Google Scholar">Google Scholar <i class="ai ai-google-scholar"></i></a>)
</span>

<br>
## <span style="font-family:monospace;">Journal Publications</span>

<!-- _pages/publications.md -->

<div class="publications">

{%- for y in page.jyears %}
  {% bibliography -f journals -q @*[year={{y}}]* %}
{% endfor %}

</div>


<br>
## <span style="font-family:monospace;">Conference Publications</span>

<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.cyears %}
  {% bibliography -f conferences -q @*[year={{y}}]* %}
{% endfor %}

</div>

<br>
## <span style="font-family:monospace;">Book Chapters</span>

<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.byears %}
  {% bibliography -f books -q @*[year={{y}}]* %}
{% endfor %}

</div>

<br>
## <span style="font-family:monospace;">Patents</span>

<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.pyears %}
  {% bibliography -f patents -q @*[year={{y}}]* %}
{% endfor %}

</div>





