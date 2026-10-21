---
layout: page
title: Publication Planner
stitle: Publication Planner
permalink: /publication-planner/
description:
nav: false
---

<div class="conference-calendar">

<h2> Conference Calendar </h2>
<p class="cal-intro">Submission deadlines and conference dates by research direction. Select a direction below to filter.</p>

{% include conference_calendar.liquid %}

<br>
<br>

<h2> Conferences </h2>
<p class="cal-intro">All tracked conferences by research direction. Select a direction below to filter.</p>

{% include direction_list.liquid data_key="conferences" %}

<br>
<br>

<h2> Journals </h2>
<p class="cal-intro">All tracked journals by research direction. Select a direction below to filter.</p>

{% include direction_list.liquid data_key="journal_list" %}

</div>

<script>
  (function () {
    // Direction buttons toggle independently, so several can be active at
    // once. "All" clears the selection; deselecting the last direction
    // falls back to "All".
    document.querySelectorAll('.cal-filter-group').forEach(function (group) {
      var allBtn = group.querySelector('.cal-filter[data-filter="all"]');
      var dirBtns = group.querySelectorAll('.cal-filter:not([data-filter="all"])');
      var rows = group.querySelectorAll('[data-direction]');

      function apply() {
        var selected = [];
        dirBtns.forEach(function (b) {
          if (b.classList.contains('active')) selected.push(b.getAttribute('data-filter'));
        });
        allBtn.classList.toggle('active', selected.length === 0);
        rows.forEach(function (row) {
          var show = selected.length === 0 || selected.indexOf(row.getAttribute('data-direction')) !== -1;
          row.style.display = show ? '' : 'none';
        });
      }

      allBtn.addEventListener('click', function () {
        dirBtns.forEach(function (b) { b.classList.remove('active'); });
        apply();
      });
      dirBtns.forEach(function (btn) {
        btn.addEventListener('click', function () {
          btn.classList.toggle('active');
          apply();
        });
      });
    });

    // "Print / PDF": print only the calendar (with the current filter), on a
    // landscape page. The browser's print dialog offers A4/Letter and
    // "Save as PDF". See #cal-print-root in _sass/_base.scss.
    document.querySelectorAll('.cal-print-btn').forEach(function (btn) {
      btn.addEventListener('click', function () {
        var area = btn.closest('.cal-filter-group').querySelector('.cal-print-area');
        var root = document.createElement('div');
        root.id = 'cal-print-root';
        root.className = 'conference-calendar';
        root.appendChild(area.cloneNode(true));
        document.body.appendChild(root);

        var pageStyle = document.createElement('style');
        pageStyle.textContent = '@page { size: landscape; margin: 0; }';
        document.head.appendChild(pageStyle);
        document.documentElement.classList.add('cal-printing');

        function cleanup() {
          window.removeEventListener('afterprint', cleanup);
          root.remove();
          pageStyle.remove();
          document.documentElement.classList.remove('cal-printing');
        }
        window.addEventListener('afterprint', cleanup);
        window.print();
      });
    });
  })();
</script>
