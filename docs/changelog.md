---
title: Changelog
layout: default
nav_order: 8
---

# Changelog
{: .no_toc }

Pulled live from this project's [GitHub Releases](https://github.com/theflaknine/MSFS-Livery-Toolkit/releases) — every entry here is exactly what's posted there, newest first. If this list doesn't load, that page always works.

<div id="changelog-list">
  <p>Loading releases…</p>
</div>

<style>
  .changelog-entry {
    padding-bottom: 1.6em;
    margin-bottom: 1.6em;
    border-bottom: 1px solid #3a3a3a;
  }
  .changelog-entry:last-child {
    border-bottom: none;
  }
  .changelog-entry h2 {
    margin-bottom: 0.2em;
  }
  .changelog-entry h2 a {
    color: inherit;
  }
  .changelog-meta {
    font-size: 0.85em;
    opacity: 0.7;
    margin-bottom: 0.9em;
  }
  .changelog-badge {
    display: inline-block;
    font-size: 0.75em;
    font-weight: 600;
    padding: 0.1em 0.6em;
    border-radius: 1em;
    margin-left: 0.5em;
    background: #7c4a03;
    color: #ffd58a;
  }
  .changelog-body {
    font-size: 0.95em;
  }
  .changelog-body ul {
    padding-left: 1.4em;
  }
</style>

<script>
(function () {
  var container = document.getElementById('changelog-list');
  var apiUrl = 'https://api.github.com/repos/theflaknine/MSFS-Livery-Toolkit/releases';

  fetch(apiUrl, { headers: { Accept: 'application/vnd.github.html+json' } })
    .then(function (res) {
      if (!res.ok) { throw new Error('GitHub API returned ' + res.status); }
      return res.json();
    })
    .then(function (releases) {
      if (!releases.length) {
        container.innerHTML = '<p>No releases published yet.</p>';
        return;
      }

      releases.sort(function (a, b) {
        return new Date(b.published_at) - new Date(a.published_at);
      });

      var html = releases.map(function (release) {
        var title = release.name || release.tag_name;
        var date = release.published_at
          ? new Date(release.published_at).toLocaleDateString(undefined, { year: 'numeric', month: 'long', day: 'numeric' })
          : '';
        var badge = release.prerelease
          ? '<span class="changelog-badge">Pre-release</span>'
          : '';
        var body = release.body_html || '<p><em>No description provided.</em></p>';

        return (
          '<section class="changelog-entry">' +
            '<h2><a href="' + release.html_url + '" target="_blank" rel="noopener">' + title + '</a>' + badge + '</h2>' +
            '<div class="changelog-meta">' + date + '</div>' +
            '<div class="changelog-body">' + body + '</div>' +
          '</section>'
        );
      }).join('');

      container.innerHTML = html;
    })
    .catch(function (err) {
      container.innerHTML =
        '<p>Couldn\'t load releases right now (' + err.message + '). ' +
        'See them directly on <a href="https://github.com/theflaknine/MSFS-Livery-Toolkit/releases">GitHub</a>.</p>';
    });
})();
</script>
