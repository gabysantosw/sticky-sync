# Sticky Notes

[Live Site](https://gabysantosw.github.io/\sticky-sync\_site\index.html)

---

## Installing SASS
- Using node, local installation: `npm install node-sass --save-dev`
- Compile: `npx node-sass input.scss output.css`
- Watch files for live coding: `npx node-sass --watch input.scss output.css`
  - `ctrl + C` to cancel watch
- NOTE: won't be using CSS custom properties when using SASS since there's still not enough compatibility.

## Adding node package
- `npm init` to generate the `package.json`
  - this file would include the node-sass dependencies

## Set the .gitignore
- create a `.gitignore` file with `node_modules/` and `package-lock.json`

## Pointy border experiments
Another interesting try:
```
width: 0;
height: 0;
border-top: 30px solid $darker;
border-right: 30px solid transparent;
```

## The ideal:
- set elements of markup to automatically get the class
  - `#` gets `<h2 class="sticky__title t-title">...` and so on
  - this would avoid the need of so much front matter

## Eleventy setup
- Local installation: `npm install --save-dev @11ty/eleventy`
- Running: `npx eleventy`
- Live serve: `npx eleventy --serve`
- Eleventy setup: create a `.eleventy.js` file
  - used to define the templates and the `source` folder
```js
module.exports = {
  dir: {
    input: "source",
  },
  markdownTemplateEngine: "njk",
  htmlTemplateEngine: "njk"
};
```

## Using Eleventy
- create the `source` folder
- add a `_includes` folder inside
  - create a `layout.njk` file with the base html of the site
- linking styles and script using nunjucks's `{% include 'file_path' %}`

## Avoiding Eleventy to render the .md as a single page, only add to collections
Set `permalik: false` to front matter
