# Docs
Documentation for ao\_core, ao\_arch, and our api.

This repo is synced with our [ReadMe Documentation](https://docs.aolabs.ai/#/) with their bi-directional sync feature. Some information on how editing with git and ReadMe work together can be found on their page on [this topic](https://docs.readme.com/main/docs/editing-with-bi-directional-sync).

If a branch is made for a new version of documentation, it will not show up on ReadMe until a version with the same name is created through the ReadMe interface.

Internal links can be created with the form `[page name](doc:page-name)`.

Pages start with some metadata in the following form.
```markdown
---
title: Lorem Ipsum
excerpt: ''
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
```

The 'hidden' tag determines whether it is publicly viewable in the docs.

When a page has subpages, the main page becomes a folder with its content in an index.md file within that folder. In the example below the text you'd see when visiting the arch page would come from the index.md file, similar to index.html files on websites.
```
📂 project
├── 📁 Docs
│   ├── 📂 arch
│   │   ├── 📄 arch-config.md
│   │   ├── 📄 index.md
│   │   └── 📃 sidebar.yml
│   └── 📃 sidebar.yml
├── 📁 recipes
├── 📁 custompages
└── 📁 references
```
