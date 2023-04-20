---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://www.kaohoon.com/wp-content/uploads/2021/09/MFEC_2021-09-15.jpg
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# page transition
transition: slide-left
# use UnoCSS
css: unocss
download: true
---

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

## Streaming Dev Git & CICD

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->
---
transition: slide-up
src: ./pages/git-flow/git-flow.md
hide: false
---
---
transition: slide-up
src: ./pages/git-flow/git-flow-diagram.md
hide: false
---
---
transition: fade
src: ./pages/git-flow/git-flow-small.md
hide: false
---
---
transition: fade
src: ./pages/git-commit/git-commit.md
hide: false
---
---
transition: fade
src: ./pages/git-commit/git-commit-example.md
hide: false
---
---
transition: slide-left
src: ./pages/code/code-quality.md
hide: false
---
---
transition: slide-left
src: ./pages/code/sonar-image.md
hide: false
---
---
transition: slide-up
src: ./pages/code/ci.md
hide: false
---
---
transition: fade
src: ./pages/code/ci-example.md
hide: false
---
---
transition: fade
src: ./pages/code/ci-deploy.md
hide: false
---
---
transition: fade-out
src: ./pages/code/sonar.md
hide: false
---
---
transition: fade-out
src: ./pages/project/diagram.md
hide: false
---

---
transition: slide-up
src: ./pages/code/pr.md
hide: false
---
---
transition: fade
src: ./pages/code/pr-workflow.md
hide: false
---
