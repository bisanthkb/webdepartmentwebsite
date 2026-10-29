# Assignment 2: Design and Documentation of a College Department Website Using HTML

**Name:** [Your Name]  
**Roll Number:** [Your Roll Number]  
**Class / Semester:** S7 CSEA / Information Technology  
**Subject:** Web Technology / HTML  
**Date:** 29 October 2026  

---

## 1. Introduction

This report details the architectural design, implementation, and semantic structure of a multi-section departmental portal developed for the **Department of Artificial Intelligence & Data Science**. Built using strictly standards-compliant **HTML5** and inline CSS presentation styling, the website provides a comprehensive informational platform covering academic curricula, faculty profiles, research facilities, student admission enquiries, and contact information.

All content, interactive anchors, forms, tabular representations, and scalable graphical branding elements are encapsulated inside a single portable file, `index.html`, ensuring cross-platform browser compatibility without external dependency requirements.

---

## 2. HTML Document Structure

Every modern webpage adheres to a standardized structural skeleton defined by the W3C and WHATWG specifications:

* `<!DOCTYPE html>`: Declares the document type as HTML5, instructing browsers to render in standards compliance mode.
* `<html lang="en">`: The root container encompassing the document, where the `lang` attribute assists assistive screen readers and search engines.
* `<head>`: Holds technical metadata, viewport responsiveness declarations, character encoding parameters, and presentation rules.
* `<title>`: Defines the primary identifier shown in browser tab headings and search engine indexing.
* `<body>`: Houses all visible, accessible content presented to end users.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Department of Artificial Intelligence & Data Science</title>
</head>
<body>
  <!-- All rendered user-facing markup resides here -->
</body>
</html>
```

---

## 3. Headings and Paragraphs

A systematic typographical hierarchy (`<h1>` to `<h6>`) establishes visual flow and assistive accessibility:

* `<h1>`: Denotes the unique main title of the page (Department name).
* `<h2>`: Identifies each major thematic section (About, Programmes, Faculty, Facilities, Enquiry, Contact).
* `<h3>`: Delineates sub-categories such as facility descriptions or list classifications.
* `<p>`: Formats body text paragraphs.
* Inline semantic formatting:
  * `<strong>`: Flags critical text with strong editorial importance.
  * `<em>`: Applies stress emphasis.
  * `<hr>`: Signifies a thematic divisional break.

```html
<h2>About the Department</h2>
<p>The Department of Artificial Intelligence and Data Science was established in <strong>2021</strong>.
It offers an <em>interdisciplinary curriculum</em> blending theoretical foundations with practical engineering.</p>
<hr>
```

---

## 4. Lists

Content categorization is implemented via two distinct list structures:

* **Unordered List (`<ul>`):** Utilized for groupings where numerical sequence is non-hierarchical, such as core subject offerings.
* **Ordered List (`<ol>`):** Employs sequential enumeration to define structured progression, such as a chronological academic semester roadmap.
* **List Item (`<li>`):** Individual container elements within lists.

```html
<!-- Unordered List Example -->
<ul>
  <li>Foundations of Artificial Intelligence & Expert Systems</li>
  <li>Machine Learning and Deep Neural Networks</li>
  <li>Big Data Analytics & Distributed Data Processing</li>
</ul>

<!-- Ordered List Example -->
<ol>
  <li>Computational Thinking & Python Programming</li>
  <li>Data Structures, Algorithms & Object-Oriented Design</li>
  <li>Linear Algebra, Probability & Applied Statistics</li>
</ol>
```

---

## 5. Hyperlinks

Navigation and resource linking are established via anchor (`<a>`) elements driven by the `href` attribute:

* **In-Page Smooth Navigation:** Utilizes bookmark fragment anchors (`href="#faculty"`) mapped directly to section ID attributes (`<section id="faculty">`), enabling fluid single-page jumping.
* **External Cross-References:** Links pointing to external educational domains use `target="_blank"` alongside `rel="noopener"` for tab isolation and execution security.
* **Direct Mail Routing:** Employs the `mailto:` scheme to trigger the user's default electronic mail client.

```html
<!-- Internal bookmark jump link -->
<a href="#faculty">Faculty</a>

<!-- Secure external link -->
<a href="https://developer.mozilla.org/en-US/docs/Web/HTML" target="_blank" rel="noopener">MDN HTML Documentation</a>

<!-- Mail protocol link -->
<a href="mailto:aids-dept@college.edu">aids-dept@college.edu</a>
```

---

## 6. Images and Scalable Graphics

Visual branding is rendered directly in the header using an inline Scalable Vector Graphics (`<svg>`) element:

* Vector representation maintains sharp resolution across display pixel densities.
* Configured with accessible `viewBox`, geometric primitives (`<circle>`), and high-contrast typographical elements (`<text>`).
* In traditional image tags (`<img>`), the `alt` attribute is mandatory to fulfill Web Content Accessibility Guidelines (WCAG) for screen readers and offline fallback states.

```html
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 120 120" width="75" height="75">
  <circle cx="60" cy="60" r="56" fill="#1e293b" stroke="#38bdf8" stroke-width="3"/>
  <text x="60" y="65" font-family="Arial" font-size="30" font-weight="bold" fill="#ffffff" text-anchor="middle">AI&amp;DS</text>
</svg>
```

---

## 7. Tables

Structured data regarding faculty hierarchies and credentials is formatted using tabular data elements:

* `<table>`: Container encapsulation.
* `<caption>`: Accessible programmatic description of the table's contents.
* `<thead>` & `<tbody>`: Logical separation between column headers and tabular data rows.
* `<tr>`: Table row container.
* `<th>`: Header cell (bold and centered by default).
* `<td>`: Standard tabular data cell.

```html
<table>
  <caption>Department Faculty Directory</caption>
  <thead>
    <tr>
      <th>Name</th>
      <th>Designation</th>
      <th>Area of Specialization</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Dr. Rajesh Sharma</td>
      <td>Professor and Head</td>
      <td>Deep Learning & Computer Vision</td>
    </tr>
    <tr>
      <td>Dr. Meera Nambiar</td>
      <td>Associate Professor</td>
      <td>Natural Language Processing</td>
    </tr>
  </tbody>
</table>
```

---

## 8. Forms and Client-Side Input Validation

User data collection is implemented via an interactive HTML5 form leveraging native validation constraints without JavaScript:

* `<form action="#" method="post">`: Defines transmission routing and POST packaging.
* `<label for="...">`: Explicitly binds to input IDs, expanding clickable hit areas and enabling screen-reader accessibility.
* Native HTML5 Input Types:
  * `type="text"`: Plain text input for names.
  * `type="email"`: Verifies standardized email formatting syntax.
  * `type="tel"` with `pattern="[0-9]{10}"`: Validates standard 10-digit telephone numbers via regular expression.
  * `required`: Prevents submission if mandatory fields remain blank.
* `<select>` and `<option>`: Dropdown selection menu for degree preferences.
* `<textarea>`: Multi-line freeform feedback input.
* `<button type="submit">`: Triggers form transmission.

```html
<form action="#" method="post">
  <label for="fullname">Full Name</label>
  <input type="text" id="fullname" name="fullname" required>

  <label for="email">Email Address</label>
  <input type="email" id="email" name="email" required>

  <label for="phone">Phone Number (10 digits)</label>
  <input type="tel" id="phone" name="phone" pattern="[0-9]{10}" required>

  <label for="degree">Degree Level</label>
  <select id="degree" name="degree">
    <option value="btech">B.Tech in AI & Data Science</option>
    <option value="mtech">M.Tech in Data Science</option>
  </select>

  <button type="submit">Submit Enquiry</button>
</form>
```

---

## 9. Semantic HTML Elements

Semantic markup explicitly imparts contextual meaning to content areas rather than merely governing visual styling:

| Semantic Element | Purpose in Departmental Website |
| :--- | :--- |
| `<header>` | Masthead container housing the department logo, college title, and subtitle. |
| `<nav>` | Global navigation bar containing internal jump links. |
| `<main>` | Isolates the central, unique content of the page from headers and footers. |
| `<section>` | Demarcates logical, self-contained sections (About, Programmes, Faculty, Facilities, Enquiry, Contact). |
| `<article>` | Encapsulates independent, reusable content blocks (individual laboratories and research centres). |
| `<address>` | Formats institutional contact coordinates and communication links. |
| `<footer>` | Encapsulates copyright statements and institutional legal notices. |

```html
<header> ... </header>
<nav> ... </nav>
<main>
  <section id="programmes"> ... </section>
  <section id="facilities">
    <article> ... </article>
  </section>
  <section id="contact">
    <address> ... </address>
  </section>
</main>
<footer> ... </footer>
```

---

## 10. Conclusion

The developed web assignment exemplifies the expressive capabilities of native **HTML5** when reinforced by clean semantic structuring. By combining semantic containers, intuitive navigational anchors, accessible data tables, and client-side validated input forms, the page achieves high performance, clean responsiveness, and full compliance with modern web accessibility guidelines.

---

## References

1. **MDN Web Docs:** *HTML: HyperText Markup Language*, https://developer.mozilla.org/en-US/docs/Web/HTML
2. **W3Schools:** *HTML5 Semantic Elements and Forms*, https://www.w3schools.com/html
3. **WHATWG:** *HTML Living Standard Specification*, https://html.spec.whatwg.org
4. **web.dev:** *Learn HTML & Accessible Web Patterns*, https://web.dev/learn/html
