# Esoptra Middleman Docs Template

## Creating a new docs repository

- `git clone git@github.com:esoptra/middleman-docs-template.git new-repository-name`
- `cd new-repository-name`
- `git remote rm origin`
- `git remote add origin git@github.com:esoptra/new-repository-name.git`
- `git remote add upstream git@github.com:esoptra/middleman-docs-template.git`
- `git push origin -u master`

## Introduction

This Middleman template is based on the [Slate](https://github.com/lord/slate) Middleman template. To get things up and running, please read the [README-SLATE.md](./README-SLATE.md) file.

By default, the Slate template only provides one layout **(menu - content - code)**. We've made a few adaptations to the Slate template to support an additional layout **(menu - content)**. This way, we can choose for each page separately which layout we want to use.

## Adding a page

Open up the `./data/navigation.yml` file and add a new entry:

```yml
- file:  new-page.html
  title: New Page
```

Duplicate the `./source/template.html.md` file and rename it to `new-page.html.md`. Adjust the options at the top as needed.

## Choosing a layout

As mentioned in the introduction, there are two layouts you can choose from:

1. **menu - content**
2. **menu - content - code**

If the amount of code examples you want to include is limited we'd suggest using the first layout, otherwise use the second.

The usage of a layout is based on the amount of language tabs defined at the top of each page.

If you leave the `language_tabs` array empty, the first layout is used. If you specify one or more languages, the second layout will be used.

## Using includes

If the amount of content for a page becomes to big or you want to reuse a specific piece of content, you can use **includes**.

For example:

```markdown
includes:
  - include1
  - include2
```

will include `./includes/_include1.md` and `./includes/_include2.md` at the bottom of the page.

## General remarks

- A page **MUST** have only **ONE H1** heading, otherwise generating the secondary navigation will not work as expected.
- Filenames of includes **MUST** begin with an **underscore**.
