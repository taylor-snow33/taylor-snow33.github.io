# The DIY Smart RV community
This group is a place to discuss various aspects of monitoring and automating of different RV systems. We encourage members to share ideas, ask questions, and collaborate on projects.

This project is intended to be the website for the community to share the custom solutions needed to turning your RV into a Smart RV. 

- **Discord**: https://discord.gg/Z7ykyGVR
- **Facebook Group**: https://www.facebook.com/groups/diysmartrv/

## Contributing
Simply clone this GitHub Repo locally to get started. 

```bash
git@github.com:taylor-snow33/taylor-snow33.github.io.git
```

#### Getting your local enviornment going
When you first open this project in VS Code it will ask you if you want to start the container. To make this easier on yourself, you should say yes, which will take a few minuites to load the dependancies. 


**Start the Jekyll Server**

To run the site locally, use the following command:
```bash
$ bundle exec jekyll s
```

#### Creating your first post
This tutorial will guide you how to write a post in the Chirpy template, and it’s worth reading even if you’ve used Jekyll before, as many features require specific variables to be set.

Naming and Path
Create a new file named YYYY-MM-DD-TITLE.md and put it in the _posts of the root directory. Please note that the EXTENSION must be one of md and markdown. If you want to save time of creating files, please consider using the plugin Jekyll-Compose to accomplish this.

Basically, you need to fill the Front Matter as below at the top of the post:

```yml
---
title: TITLE
date: YYYY-MM-DD HH:MM:SS +/-TTTT
categories: [TOP_CATEGORIE, SUB_CATEGORIE]
tags: [TAG]     # TAG names should always be lowercase
author: #your ID
---
```

#### Setting up your author ID
Adding author information in _data/authors.yml
```yml
<author_id>:
  name: <full name>
  twitter: <twitter_of_author>
  url: <homepage_of_author>
```

### Dependancies

- **Solution**: [Jekyll](https://jekyllrb.com/)
- **Base Theme**: [Chirpy](https://chirpy.cotes.page/)
- **Hosted**: [GitHub Pages](https://pages.github.com/)
