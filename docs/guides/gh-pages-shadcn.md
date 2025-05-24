---
title: Shadcn styled Mkdoc setup
---

This very blog is built using [Mkdocs](https://www.mkdocs.org/) and [shadcn/ui](https://ui.shadcn.com/). The theme is a custom build of the shadcn/ui components, styled with Tailwind CSS. The goal is to create a clean, modern, and responsive design that showcases my work and thoughts effectively. This is using [mkdocs-shadcn](https://github.com/asiffer/mkdocs-shadcn) theme.

## Pre-requisites

- [Python](https://www.python.org/downloads/)

## Setup Project

- Mkdocs are built using Python there fore lets start by creating a virtual environment.

```bash
python -m venv venv
```

- Activate the virtual environment.

```bash
# On Windows
venv\Scripts\activate

# On MacOS/Linux
source venv/bin/activate
```

## Setup Github

- Create a new repository on GitHub. You can name it anything you like, but for this example, we'll call it `my-blog`.

!!! note
      If you use `<username>.github.io` as the repository name, GitHub will automatically publish it to `<username>.github.io`. Otherwise, you can use a custom domain or subdomain. This is a good option if you want to start a blog or portfolio site.
