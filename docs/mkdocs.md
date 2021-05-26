# MkDocs

[TOC]

[MkDocs](https://www.mkdocs.org/) is a very nice documentation system. I use it to take notes for coding and deployed my mkdocs project on github pages.

## Create new project

```
mkdocs new <my-project>
```

## Preview project

```
mkdocs serve
```

This will show you the preview page before it been published.

## Deploy project on github pages

Once you finish the writing, you can push the project dir to github repo. The `mkdocs gh-deploy` command can help to delpoy project and gerate static web page automatically. All you need to do is to perform the following commands in the project directory. The static web will be pushed to `gh-pages` branch

```
mkdocs gh-deploy --clean
```

!!! Note

        You need to preset the `pages` in the `Settings` to build github page site from `gh-pages` branch.

