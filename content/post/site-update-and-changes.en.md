---
author: "Maciej Budzyński"
title: "Site Refresh and Update"
date: "2025-01-06T13:00:00+02:00"
categories: ["programming"]
tags: ["programming", "go", "hugo"]

---

I haven't written here for a very long time, and my activity was limited to the annual update of the copyright notice. Due to the Hugo update, I was forced to refresh the site and update the content here.

<!--more-->

## Template Change

To change the template, I performed the following steps:

1. Removed the old template with my modifications `hugo-dusk`.
2. Added the new template `PaperMod` to the `themes` directory.
3. Migrated the `config.toml` file to `hugo.yaml`.

## Configuration

After changing the template, I had to adjust the site configuration. I made the following changes in the `hugo.yaml` file:

- Updated the `params` section with new settings available in the `PaperMod` template.
- Added new configuration sections that allow better content and site appearance management.

## Articles in English

Another new feature on the site is articles in English. To add support for multiple languages, I made the following changes:

1. Added the `languages` section in the `hugo.yaml` file:

```yaml
languages:
  pl:
    languageName: "Polski"
    weight: 1
  en:
    languageName: "English"
    weight: 2
```

2. All articles were duplicated and their names changed from `*.md` to `*.en.md`
3. These articles were translated using AI tools.

Thanks to these changes, the site is now available for both Polish and English-speaking users.

I hope you will like these changes and that they will make it easier to use the site, and I hope to publish more content here.