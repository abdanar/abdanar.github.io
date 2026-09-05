---
layout: post
title: "Introducing MathGenealogy: A Modern Interface for Mathematical Genealogy"
date: 05-09-2026
---

This is a short post about a project I developed called `MathGenealogy`, which provides a modern interface for exploring the Mathematics Genealogy Project database.

My main motivation was to create a more user-friendly and visually appealing way to navigate the extensive network of mathematicians and their academic lineages. As you may know, the original [Mathematics Genealogy Project website](https://www.genealogy.math.ndsu.nodak.edu/index.php) already exists and serves as the primary source of data. However, its interface is somewhat dated and offers limited interactive functionality. With the capabilities of modern web technologies and AI-assisted development, I saw an opportunity to build a more intuitive and engaging way to explore this information.

The source code for `MathGenealogy` is available in the [GitHub repository](https://github.com/abdanar/mathgenealogy), where you can also find the documentation and instructions for running the project locally. The website is also available [here](https://abdanar.github.io/mathgenealogy/) and provides an interactive interface for exploring the academic genealogy of mathematicians. The homepage resembles a search engine: you can search for a mathematician by name and navigate directly to their profile. For example, suppose you want to explore Leonhard Euler's academic genealogy. You can type either `Leonhard Euler` or simply `Euler` into the search bar. You can then select his name from the suggestions or press Enter to view a list of mathematicians matching your query. After selecting the correct result, you are taken to a profile containing information such as academic advisors, students, dissertation details, institutions, and other relevant information. Euler's profile is shown below. Note that its appearance may vary depending on the selected color scheme, as the website supports both light and dark modes.

<div class="theme-image" style="max-width: 890px; margin: 0 auto;">
  <img class="theme-image-light" src="/assets/img/euler_light.png" alt="Leonhard Euler profile on MathGenealogy">
  <img class="theme-image-dark" src="/assets/img/euler_dark.png" alt="Leonhard Euler profile on MathGenealogy">
</div>

<br>

Another feature of the website is the ability to find a directed academic genealogy path between two mathematicians. For instance, you can explore the academic connection between Dirichlet and Lindemann by entering their names in the corresponding search fields and viewing the resulting path.

<div class="theme-image" style="max-width: 890px; margin: 0 auto;">
  <img class="theme-image-light" src="/assets/img/rel_light.png" alt="Academic genealogy path on MathGenealogy">
  <img class="theme-image-dark" src="/assets/img/rel_dark.png" alt="Academic genealogy path on MathGenealogy">
</div>

<br>
Although `MathGenealogy` provides a modern interface and additional interactive features, it still relies on data from the original Mathematics Genealogy Project. Any limitations or inaccuracies in the source data may therefore also be reflected on the website. It is also important to keep in mind that `MathGenealogy` is a personal project and may not provide complete information for every mathematician. When accuracy is particularly important, I recommend cross-referencing the information with the original Mathematics Genealogy Project. In future updates, I plan to continue improving the interface, adding new features, and making mathematical genealogy easier to explore.

Enjoy exploring the academic genealogy of mathematicians!
