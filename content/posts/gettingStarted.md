---
title: "Getting Started"
description: "This is a guide to getting started with Hugo!"
date: 2021-12-20T09:18:53-06:00
draft: false
---

# Now that you have installed and setup Hugo, here is a guide to help with the next steps.

---

- Familiarize yourself with the code base.
    - The most important files will be the config.toml, and your contents folder.
    - Files like the config.toml are very important to the structure of the site.
---

Hugo utilizes a few different languages: Markdown, HTML, CSS, JS, and Go. However, the ones you may use the most are CSS and Markdown.

- ex: markdown files like the _index.md files server as the base for your page. You can edit the content within the page and the server will update it upon saving.[^1]

---

To easily make changes in Hugo, I suggest using Command Prompt in Adminstration mode. There are several really good Hugo commands that will create pages in the right directories.[^2]

- ex: This will start the local server that will allow you to view your site.

```
hugo server -D 
```

This command will help you create new pages in your "content" directory:

```
hugo new page.md
```

Alternatively, if you would like you can also create the new file in a specific directory, like "posts" for example.

```
hugo new posts/page.md
```

---

### Site Configuration:

Within the config.toml file, there are a lot of different ways you could configure your theme and your site.

In this specific config.toml I have set up the site menu and declared other parameters that are important to the site, like the home page.

Every config file needs to have front matter. Front matter will define some important site characteristics, like which theme the site should be using. [^3]

Ex:

```
baseURL = 'http://example.org/'
languageCode = 'en-us'
title = 'LP Web Dev Team'
theme = "hugo-PaperMod"
```

- menu configuration also lives within the config.toml. I will create a separate post detailing menus and their intricacies.

---


### Footnotes:

[^1]: [Markdown cheat sheet](https://www.markdownguide.org/cheat-sheet/)
[^2]: [Hugo Quickstart guide](https://gohugo.io/getting-started/quick-start/)
[^3]: [Front matter information.](https://gohugo.io/content-management/front-matter/)