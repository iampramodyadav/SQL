<!DOCTYPE html>
<!-- saved from url=(0072)file:///C:/Users/PRAMOD/Desktop/DB0201-l2%20_M2_SELECT_statement.md.html -->
<html lang="en"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><style data-merge-styles="true"></style>
    
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="stylesheet" href="./DB0201-l2 _M2_SELECT_statement_files/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
    <link rel="stylesheet" href="./DB0201-l2 _M2_SELECT_statement_files/default.min.css">
  <style type="text/css">/* this file is used for labs on cognitiveclass.ai that were written in markdown */

/* applies to images, i.e. "![]()" in markdown */
img {
  max-width: 100%;
  height: auto;
}

/* add padding and margins */
body {
  padding: 10px;
  margin: 10px;
}

/* applies to tables, i.e. "|--|--|" in markdown */
table td,
table th {
  padding: 0.75rem;
  vertical-align: top;
  border-top: 1px solid #dee2e6;
}

/* applies to using quotes, i.e. ">" in markdown */
blockquote {
  background: #f9f9f9;
  border-left: 10px solid #ccc;
  margin: 1.5em 10px;
  padding: 1em 10px 0.1em 10px;
  quotes: '\201C''\201D''\2018''\2019';
}

/* the headers need some spacing */

h1,
h2,
h3,
h4,
h5,
h6 {
  font-weight: 500;
  padding-top: 20px;
}

/* Add padding between nested list item */
ul > li > ul {
  padding-bottom: 1rem;
}

.code-badge-language {
  display: none;
}
.code-badge-copy-icon {
  background: url('data:image/svg+xml;base64,PHN2ZyBhcmlhLWhpZGRlbj0idHJ1ZSIgZm9jdXNhYmxlPSJmYWxzZSIgZGF0YS1wcmVmaXg9ImZhciIgZGF0YS1pY29uPSJjb3B5IiBjbGFzcz0ic3ZnLWlubGluZS0tZmEgZmEtY29weSBmYS13LTE0IiByb2xlPSJpbWciIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgdmlld0JveD0iMCAwIDQ0OCA1MTIiPjxwYXRoIGZpbGw9ImN1cnJlbnRDb2xvciIgZD0iTTQzMy45NDEgNjUuOTQxbC01MS44ODItNTEuODgyQTQ4IDQ4IDAgMCAwIDM0OC4xMTggMEgxNzZjLTI2LjUxIDAtNDggMjEuNDktNDggNDh2NDhINDhjLTI2LjUxIDAtNDggMjEuNDktNDggNDh2MzIwYzAgMjYuNTEgMjEuNDkgNDggNDggNDhoMjI0YzI2LjUxIDAgNDgtMjEuNDkgNDgtNDh2LTQ4aDgwYzI2LjUxIDAgNDgtMjEuNDkgNDgtNDhWOTkuODgyYTQ4IDQ4IDAgMCAwLTE0LjA1OS0zMy45NDF6TTI2NiA0NjRINTRhNiA2IDAgMCAxLTYtNlYxNTBhNiA2IDAgMCAxIDYtNmg3NHYyMjRjMCAyNi41MSAyMS40OSA0OCA0OCA0OGg5NnY0MmE2IDYgMCAwIDEtNiA2em0xMjgtOTZIMTgyYTYgNiAwIDAgMS02LTZWNTRhNiA2IDAgMCAxIDYtNmgxMDZ2ODhjMCAxMy4yNTUgMTAuNzQ1IDI0IDI0IDI0aDg4djIwMmE2IDYgMCAwIDEtNiA2em02LTI1NmgtNjRWNDhoOS42MzJjMS41OTEgMCAzLjExNy42MzIgNC4yNDMgMS43NTdsNDguMzY4IDQ4LjM2OGE2IDYgMCAwIDEgMS43NTcgNC4yNDNWMTEyeiI+PC9wYXRoPjwvc3ZnPg==');
  background-size: 100% 100%;
}

.code-badge {
  bottom: 0 !important;
  top: unset !important;
  background: unset !important;
}

.code-badge > .code-badge-check-icon {
  background: green;
}
.code-badge-check-icon {
  font-size: 1.2em;
  cursor: pointer;
  padding: 0 7px;
  background: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGFyaWEtaGlkZGVuPSJ0cnVlIiBmb2N1c2FibGU9ImZhbHNlIiBkYXRhLXByZWZpeD0iZmFzIiBkYXRhLWljb249ImNoZWNrIiBjbGFzcz0ic3ZnLWlubGluZS0tZmEgZmEtY2hlY2sgZmEtdy0xNiIgcm9sZT0iaW1nIiB2aWV3Qm94PSIwIDAgNTEyIDUxMiIgc3R5bGU9IiYjMTA7ICAgIGNvbG9yOiAjMmFmZjMyOyYjMTA7Ij48cGF0aCBmaWxsPSJjdXJyZW50Q29sb3IiIGQ9Ik0xNzMuODk4IDQzOS40MDRsLTE2Ni40LTE2Ni40Yy05Ljk5Ny05Ljk5Ny05Ljk5Ny0yNi4yMDYgMC0zNi4yMDRsMzYuMjAzLTM2LjIwNGM5Ljk5Ny05Ljk5OCAyNi4yMDctOS45OTggMzYuMjA0IDBMMTkyIDMxMi42OSA0MzIuMDk1IDcyLjU5NmM5Ljk5Ny05Ljk5NyAyNi4yMDctOS45OTcgMzYuMjA0IDBsMzYuMjAzIDM2LjIwNGM5Ljk5NyA5Ljk5NyA5Ljk5NyAyNi4yMDYgMCAzNi4yMDRsLTI5NC40IDI5NC40MDFjLTkuOTk4IDkuOTk3LTI2LjIwNyA5Ljk5Ny0zNi4yMDQtLjAwMXoiLz48L3N2Zz4=');
  background-size: 100% 100%;
}
</style><style type="text/css">
  @media print {
    .ms-editor-squiggler {
        display:none !important;
    }
  }
  .ms-editor-squiggler {
    all: initial;
    display: block !important;
    height: 0px !important;
  }</style><style type="text/css">/* this file is used for labs on cognitiveclass.ai that were written in markdown */

/* applies to images, i.e. "![]()" in markdown */
img {
  max-width: 100%;
  height: auto;
}

/* add padding and margins */
body {
  padding: 10px;
  margin: 10px;
}

/* applies to tables, i.e. "|--|--|" in markdown */
table td,
table th {
  padding: 0.75rem;
  vertical-align: top;
  border-top: 1px solid #dee2e6;
}

/* applies to using quotes, i.e. ">" in markdown */
blockquote {
  background: #f9f9f9;
  border-left: 10px solid #ccc;
  margin: 1.5em 10px;
  padding: 1em 10px 0.1em 10px;
  quotes: '\201C''\201D''\2018''\2019';
}

/* the headers need some spacing */

h1,
h2,
h3,
h4,
h5,
h6 {
  font-weight: 500;
  padding-top: 20px;
}

/* Add padding between nested list item */
ul > li > ul {
  padding-bottom: 1rem;
}

.code-badge-language {
  display: none;
}
.code-badge-copy-icon {
  background: url('data:image/svg+xml;base64,PHN2ZyBhcmlhLWhpZGRlbj0idHJ1ZSIgZm9jdXNhYmxlPSJmYWxzZSIgZGF0YS1wcmVmaXg9ImZhciIgZGF0YS1pY29uPSJjb3B5IiBjbGFzcz0ic3ZnLWlubGluZS0tZmEgZmEtY29weSBmYS13LTE0IiByb2xlPSJpbWciIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyIgdmlld0JveD0iMCAwIDQ0OCA1MTIiPjxwYXRoIGZpbGw9ImN1cnJlbnRDb2xvciIgZD0iTTQzMy45NDEgNjUuOTQxbC01MS44ODItNTEuODgyQTQ4IDQ4IDAgMCAwIDM0OC4xMTggMEgxNzZjLTI2LjUxIDAtNDggMjEuNDktNDggNDh2NDhINDhjLTI2LjUxIDAtNDggMjEuNDktNDggNDh2MzIwYzAgMjYuNTEgMjEuNDkgNDggNDggNDhoMjI0YzI2LjUxIDAgNDgtMjEuNDkgNDgtNDh2LTQ4aDgwYzI2LjUxIDAgNDgtMjEuNDkgNDgtNDhWOTkuODgyYTQ4IDQ4IDAgMCAwLTE0LjA1OS0zMy45NDF6TTI2NiA0NjRINTRhNiA2IDAgMCAxLTYtNlYxNTBhNiA2IDAgMCAxIDYtNmg3NHYyMjRjMCAyNi41MSAyMS40OSA0OCA0OCA0OGg5NnY0MmE2IDYgMCAwIDEtNiA2em0xMjgtOTZIMTgyYTYgNiAwIDAgMS02LTZWNTRhNiA2IDAgMCAxIDYtNmgxMDZ2ODhjMCAxMy4yNTUgMTAuNzQ1IDI0IDI0IDI0aDg4djIwMmE2IDYgMCAwIDEtNiA2em02LTI1NmgtNjRWNDhoOS42MzJjMS41OTEgMCAzLjExNy42MzIgNC4yNDMgMS43NTdsNDguMzY4IDQ4LjM2OGE2IDYgMCAwIDEgMS43NTcgNC4yNDNWMTEyeiI+PC9wYXRoPjwvc3ZnPg==');
  background-size: 100% 100%;
}

.code-badge {
  bottom: 0 !important;
  top: unset !important;
  background: unset !important;
}

.code-badge > .code-badge-check-icon {
  background: green;
}
.code-badge-check-icon {
  font-size: 1.2em;
  cursor: pointer;
  padding: 0 7px;
  background: url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGFyaWEtaGlkZGVuPSJ0cnVlIiBmb2N1c2FibGU9ImZhbHNlIiBkYXRhLXByZWZpeD0iZmFzIiBkYXRhLWljb249ImNoZWNrIiBjbGFzcz0ic3ZnLWlubGluZS0tZmEgZmEtY2hlY2sgZmEtdy0xNiIgcm9sZT0iaW1nIiB2aWV3Qm94PSIwIDAgNTEyIDUxMiIgc3R5bGU9IiYjMTA7ICAgIGNvbG9yOiAjMmFmZjMyOyYjMTA7Ij48cGF0aCBmaWxsPSJjdXJyZW50Q29sb3IiIGQ9Ik0xNzMuODk4IDQzOS40MDRsLTE2Ni40LTE2Ni40Yy05Ljk5Ny05Ljk5Ny05Ljk5Ny0yNi4yMDYgMC0zNi4yMDRsMzYuMjAzLTM2LjIwNGM5Ljk5Ny05Ljk5OCAyNi4yMDctOS45OTggMzYuMjA0IDBMMTkyIDMxMi42OSA0MzIuMDk1IDcyLjU5NmM5Ljk5Ny05Ljk5NyAyNi4yMDctOS45OTcgMzYuMjA0IDBsMzYuMjAzIDM2LjIwNGM5Ljk5NyA5Ljk5NyA5Ljk5NyAyNi4yMDYgMCAzNi4yMDRsLTI5NC40IDI5NC40MDFjLTkuOTk4IDkuOTk3LTI2LjIwNyA5Ljk5Ny0zNi4yMDQtLjAwMXoiLz48L3N2Zz4=');
  background-size: 100% 100%;
}
</style></head>
  <body data-new-gr-c-s-check-loaded="14.987.0" data-gr-ext-installed="">
    <h2>Reading: SELECT statement examples (2 mins)</h2>
    <img src="./DB0201-l2 _M2_SELECT_statement_files/IDSNlogo.png" width="200" height="200">
    <h2>Objectives</h2>
    <p>At the end of this lab you will be able to:</p>
    <ul>
      <li>use SELECT queries to retrieve data from the database</li>
    </ul>
    <p><b>Effort:</b> 2 min</p>
    <p>The general syntax of SELECT statments is:</p>
    <p><strong>select COLUMN1, COLUMN2, ... from TABLE1 ;</strong></p>
    <p>To retrieve all columns from the COUNTRY table we could use "*" instead of specifying individual column names:</p>
    <p><strong>select * from COUNTRY ;</strong></p>
    <p>The WHERE clause can be added to your query to filter results or get specific rows of data. To retrieve data for all rows in the COUNTRY table where the ID is less than 5:</p>
    <p><strong>select * from COUNTRY where ID &lt; 5 ;</strong></p>
    <p>In case of character based columns the values of the predicates in the where clause need to be enclosed in single quotes. To retrieve the data for the country with country code "CA" we would issue:</p>
    <p><strong>select * from COUNTRY where CCODE = 'CA';</strong></p>
    <p>In the lab that follows later in the module, you will apply these concepts and practice SELECT queries hands-on.</p>
    <p>Good luck!</p>
    <h2>Author(s)</h2>
    <h4>Rav Ahuja</h4>
    <h4></h4>
    <h2>Changelog</h2>
    <table>
      <thead>
        <tr>
          <th>Date</th>
          <th>Version</th>
          <th>Changed by</th>
          <th>Change Description</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>2020-08-31</td>
          <td>2.0</td>
          <td>Malika Singla</td>
          <td>Markdown file creation</td>
        </tr>
      </tbody>
    </table>
    <script>window.addEventListener('load', function() {
snFaculty.inject();
});</script>
    <script src="./DB0201-l2 _M2_SELECT_statement_files/inject.43989f87.js.download"></script>
    <script src="./DB0201-l2 _M2_SELECT_statement_files/highlight.min.js.download"></script>
    <script src="./DB0201-l2 _M2_SELECT_statement_files/highlightjs-badge.min.js.download"></script>
  

<style>
@media print {
   .code-badge { display: none; }
}
    .code-badge-pre {
        position: relative;
    }
    .code-badge {
        display: flex;
        flex-direction: row;
        white-space: normal;
        background: transparent;
        background: #333;
        color: white;
        font-size: 0.875em;
        opacity: 0.5;
        transition: opacity linear 0.5s;
        border-radius: 0 0 0 7px;
        padding: 5px 8px 5px 8px;
        position: absolute;
        right: 0;
        top: 0;
    }
    .code-badge.active {
        opacity: 0.8;
    }

    .code-badge:hover {
        opacity: .95;
    }

    .code-badge a,
    .code-badge a:hover {
        text-decoration: none;
    }

    .code-badge-language {
        margin-right: 10px;
        font-weight: 600;
        color: goldenrod;
    }
    .code-badge-copy-icon {
        font-size: 1.2em;
        cursor: pointer;
        padding: 0 7px;
        margin-top:2;
    }
    .fa.text-success:{ color: limegreen !important }
</style><div id="CodeBadgeTemplate" style="display:none">
    <div class="code-badge">
        <div class="code-badge-language">{{language}}</div>
        <div title="Copy to clipboard">
            <i class="{{copyIconClass}} code-badge-copy-icon"></i>
        </div>
     </div>
</div><div class="betternet-wrapper"></div><editor-card style="position:absolute;top:0px;left:0px;z-index:auto;display: block !important"><div dir="ltr" style="all: initial;"><div style="color: initial; font: initial; font-feature-settings: initial; font-kerning: initial; font-optical-sizing: initial; font-variation-settings: initial; forced-color-adjust: initial; text-orientation: initial; text-rendering: initial; -webkit-font-smoothing: initial; -webkit-locale: initial; -webkit-text-orientation: initial; -webkit-writing-mode: initial; writing-mode: initial; zoom: initial; place-content: initial; place-items: initial; place-self: initial; alignment-baseline: initial; animation: initial; appearance: initial; aspect-ratio: initial; backdrop-filter: initial; backface-visibility: initial; background: initial; background-blend-mode: initial; baseline-shift: initial; block-size: initial; border-block: initial; border: initial; border-radius: initial; border-collapse: initial; border-end-end-radius: initial; border-end-start-radius: initial; border-inline: initial; border-start-end-radius: initial; border-start-start-radius: initial; inset: initial; box-shadow: initial; box-sizing: initial; break-after: initial; break-before: initial; break-inside: initial; buffered-rendering: initial; caption-side: initial; caret-color: initial; clear: initial; clip: initial; clip-path: initial; clip-rule: initial; color-interpolation: initial; color-interpolation-filters: initial; color-rendering: initial; color-scheme: initial; columns: initial; column-fill: initial; gap: initial; column-rule: initial; column-span: initial; contain: initial; contain-intrinsic-size: initial; content: initial; content-visibility: initial; counter-increment: initial; counter-reset: initial; counter-set: initial; cursor: initial; cx: initial; cy: initial; d: initial; display: initial; dominant-baseline: initial; empty-cells: initial; fill: initial; fill-opacity: initial; fill-rule: initial; filter: initial; flex: initial; flex-flow: initial; float: initial; flood-color: initial; flood-opacity: initial; grid: initial; grid-area: initial; height: initial; hyphens: initial; image-orientation: initial; image-rendering: initial; inline-size: initial; inset-block: initial; inset-inline: initial; isolation: initial; letter-spacing: initial; lighting-color: initial; line-break: initial; list-style: initial; margin-block: initial; margin: initial; margin-inline: initial; marker: initial; mask: initial; mask-type: initial; max-block-size: initial; max-height: initial; max-inline-size: initial; max-width: initial; min-block-size: initial; min-height: initial; min-inline-size: initial; min-width: initial; mix-blend-mode: initial; object-fit: initial; object-position: initial; offset: initial; opacity: initial; order: initial; origin-trial-test-property: initial; orphans: initial; outline: initial; outline-offset: initial; overflow-anchor: initial; overflow-clip-margin: initial; overflow-wrap: initial; overflow: initial; overscroll-behavior-block: initial; overscroll-behavior-inline: initial; overscroll-behavior: initial; padding-block: initial; padding: initial; padding-inline: initial; page: initial; page-orientation: initial; paint-order: initial; perspective: initial; perspective-origin: initial; pointer-events: initial; position: absolute; quotes: initial; r: initial; resize: initial; ruby-position: initial; rx: initial; ry: initial; scroll-behavior: initial; scroll-margin-block: initial; scroll-margin: initial; scroll-margin-inline: initial; scroll-padding-block: initial; scroll-padding: initial; scroll-padding-inline: initial; scroll-snap-align: initial; scroll-snap-stop: initial; scroll-snap-type: initial; shape-image-threshold: initial; shape-margin: initial; shape-outside: initial; shape-rendering: initial; size: initial; speak: initial; stop-color: initial; stop-opacity: initial; stroke: initial; stroke-dasharray: initial; stroke-dashoffset: initial; stroke-linecap: initial; stroke-linejoin: initial; stroke-miterlimit: initial; stroke-opacity: initial; stroke-width: initial; tab-size: initial; table-layout: initial; text-align: initial; text-align-last: initial; text-anchor: initial; text-combine-upright: initial; text-decoration: initial; text-decoration-skip-ink: initial; text-indent: initial; text-overflow: initial; text-shadow: initial; text-size-adjust: initial; text-transform: initial; text-underline-offset: initial; text-underline-position: initial; touch-action: initial; transform: initial; transform-box: initial; transform-origin: initial; transform-style: initial; transition: initial; user-select: initial; vector-effect: initial; vertical-align: initial; visibility: initial; -webkit-app-region: initial; border-spacing: initial; -webkit-border-image: initial; -webkit-box-align: initial; -webkit-box-decoration-break: initial; -webkit-box-direction: initial; -webkit-box-flex: initial; -webkit-box-ordinal-group: initial; -webkit-box-orient: initial; -webkit-box-pack: initial; -webkit-box-reflect: initial; -webkit-highlight: initial; -webkit-hyphenate-character: initial; -webkit-line-break: initial; -webkit-line-clamp: initial; -webkit-mask-box-image: initial; -webkit-mask: initial; -webkit-mask-composite: initial; -webkit-perspective-origin-x: initial; -webkit-perspective-origin-y: initial; -webkit-print-color-adjust: initial; -webkit-rtl-ordering: initial; -webkit-ruby-position: initial; -webkit-tap-highlight-color: initial; -webkit-text-combine: initial; -webkit-text-decorations-in-effect: initial; -webkit-text-emphasis: initial; -webkit-text-emphasis-position: initial; -webkit-text-fill-color: initial; -webkit-text-security: initial; -webkit-text-stroke: initial; -webkit-transform-origin-x: initial; -webkit-transform-origin-y: initial; -webkit-transform-origin-z: initial; -webkit-user-drag: initial; -webkit-user-modify: initial; white-space: initial; widows: initial; width: initial; will-change: initial; word-break: initial; word-spacing: initial; x: initial; y: initial; z-index: 2147483647;"><link rel="stylesheet" href="chrome-extension://hokifickgkhplphjiodbggjmoafhignh/fonts/fabric-icons.css"><div style="all: initial;"></div></div></div></editor-card></body></html>