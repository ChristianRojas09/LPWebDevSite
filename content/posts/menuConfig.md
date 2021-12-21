---
title: "Menu Configuration"
description: "This is a brief guide to menu configuration"
date: 2021-12-21T08:29:20-06:00
draft: false
---

### Menu Configuration

---

Menus in Hugo are simple, but powerful.

Menus are capable of:

- Placing content in one or many menus
- Nesting menus (can be difficult depending on the theme you choose)
- Menu entries can actually be created without the attachment of any content
    - Be careful of this, as it can result in 404 errors

This specific site has simple non-nested menus (though that is changing, as I work to implement nested drop down menus)

There are two ways to add content to a menu.

---

The first way, is to build out the menu in the config.toml. This way is mostly for non-content entries.

Ex: Say I want to create a menu item for the 'about' section of my site.

I would need to declare the menu and it's parameters:

```
[menu]
    [[menu.main]]
    identifier = "about"
    name = "about"
    url = "/about/"
    weight = 3
```
- The name is what you see on the front end.
- Identifier is what Hugo will look for when linking child pages to that menu. It is also what this menu will go by on the back end.
- You can manually choose your own URL slug
- **weight** is important. Weight decides what order your menu entry will go in.

---

The second way to add to a menu entry is on the content page itself!

There are a few ways to do this, but I find the advanced way to be the best - as you are able to define more parameters here.

This code will live in your front matter:

```
[menu]
  [menu.main]
    parent = 'posts'
    weight = 6
```

Note: If you notice. This page does not have any menu parameters in the front matter. This is because I already have the menu setup in the config.toml and when I created this page in PowerShell, I used the command:

```
hugo new posts/menuConfig.md
```

---

### Nesting

Nesting content is done in the parent field. 

The parent of an entry should be the identifier of another entry.

The following order is used to determine an Identifier:

``` 
.Name > .LinkTitle > .Title 
```

This means that .Title will be used unless .LinkTitle is present, etc. In practice, .Name and .Identifier are only used to structure relationships and therefore never displayed.

In this example, the top level of the menu is defined in your site config file. All content entries are attached to one of these entries via the .Parent field.

---

### Params

Params are also important fields in menus.

You can use these to add defined content to the menus.

A common use is to define a custom param to add css to a specific menu item.

Ex:

```
[menu]
[[menu.main]]
  identifier = 'about'
  name = 'about hugo'
  pre = "<i class='fa fa-heart'></i>"
  url = '/about/'
  weight = -110
  [menu.main.params]
    class = 'highlight-menu-item'
```

---

### Resources:

[Menu guide](https://gohugo.io/content-management/menus/)

[Menu templates](https://gohugo.io/templates/menu-templates/)
