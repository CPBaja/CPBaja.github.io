# 🎨 CSS / SCSS Tutorials

Welcome to the CSS and SCSS learning guide! This document explains how we style our web applications, make them look professional, and the best resources to help you master responsive design.

## What is CSS / SCSS Used For?

On our team, **CSS (Cascading Style Sheets) is used to style our frontend web applications**, such as PartSync and DataVis. If HTML is the skeleton of our apps, CSS is the skin and clothing—it dictates colors, fonts, layouts, animations, and how the app adapts to different screen sizes (like mobile phones vs. desktop monitors).

Instead of plain CSS, **we exclusively use SCSS (Sass)**. SCSS is a preprocessor scripting language that compiles into CSS. It gives us powerful programming features that regular CSS lacks, such as variables, nested rules, and mixins, allowing us to write much cleaner and more reusable styling code.



Because we use **Angular**, our SCSS is automatically scoped to individual components. This means the styles you write for the `part-list.component.scss` file will *only* apply to that specific component, preventing your styles from accidentally leaking and breaking other parts of the application.

---

## Prerequisites

Before writing styles for our web apps, ensure your editor is set up:
1. **VSCode:** Installed and configured.
2. *(Optional but Recommended)* **SCSS Formatter Extension:** Tools like Prettier can help automatically format your SCSS files on save, keeping indentation clean. Note that Angular's CLI automatically handles the compilation of SCSS to CSS, so you do not need a separate compiler extension.

---

## 📚 Learning Resources

Styling can be frustrating for beginners, but understanding the core rules of layout makes it much easier. Choose the track below that fits your experience level.

### 1. The Absolute Basics (For Beginners)
If you are new to web design, you need to understand how standard CSS selectors, properties, and layouts work before adding SCSS features.
* **[MDN Web Docs: CSS Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics)**: Read this to understand how CSS targets HTML elements.
* **[A Complete Guide to Flexbox (CSS-Tricks)](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)**: **Read this.** Flexbox is the primary way we align items (like centering text or creating navigation bars) in modern web development. You will use this constantly.
* **[A Complete Guide to Grid (CSS-Tricks)](https://css-tricks.com/snippets/css/complete-guide-grid/)**: Grid is used for larger, two-dimensional layouts, like the main dashboard structure of DataVis.

### 2. SCSS Features (For Intermediate Developers)
Once you know CSS, learn how SCSS makes your life easier.
* **[Sass Official Guide (Learn Sass)](https://sass-lang.com/guide)**: Read the sections on **Variables**, **Nesting**, and **Modules**. These are the three features we use the most to keep our stylesheets organized.

### 3. Angular Component Styling
Learn how Angular applies your SCSS to the DOM (Document Object Model).
* **[Angular.dev: Component Styling](https://angular.dev/guide/components/styling)**: Understand how View Encapsulation works, and how to use the `:host` pseudo-class selector to style the container of your Angular component.

---

## 🛑 Team Best Practices for SCSS

When styling team projects like PartSync, adhere to these rules:
* **Avoid `!important`:** Using `!important` to force a style to apply is almost always a sign of poorly structured CSS. Fix your CSS specificity instead.
* **Keep Nesting Shallow:** SCSS allows you to nest selectors inside each other. Do not nest more than 3 levels deep. Deep nesting creates massive, overly specific CSS that is hard to override and slow for the browser to parse.
* **Use Global Variables:** Never hardcode brand colors (like Cal Poly green or gold) or standard spacing units directly into a component's SCSS file. Always import and use the team's global SCSS variables (e.g., `color: $team-primary-green;`).
* **Design Responsively:** Always assume someone might open PartSync on their phone while standing in the machine shop. Use relative units (`rem`, `%`, `vh`, `vw`) instead of fixed pixels (`px`) where appropriate, and use media queries to adjust layouts for smaller screens.