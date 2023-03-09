# How to customize the ELIXIR-TrP-LessonTemplate-MkDocs
## 1.1 File strucutre overview
### index.md
This file renders the home page of the website and is found in the `/docs`folder. This is the first page a visitor to the website will see when using the base URL. It is by default called `About`in this template. It contains information about the trainig material and most headings corresponds to a Bioschemas property.
### mkdocs.yml
This file is where most of the layout options are made and where the [MkDocs](https://www.mkdocs.org/) theme [Material](https://squidfunk.github.io/mkdocs-material/)is specified. The navigation menu is customised here as well as the header and footer etc. 
### README.md
This file is displayed by default on the main page of the GitHub repository and liked in the About section. It should contain important information about the repository on how to use the material and explain how to contribute. 
### LICENCE.md 
This file is linked in the About section of the GitHub repository and should contain a full licence statement. By default it is set to the Creative Commons [Attribution-ShareAlike 4.0 International (CC BY-SA 4.0) license](https://creativecommons.org/licenses/by-sa/4.0/legalcode)

### docs folder
The docs folder contains several subfolders

- `/chapters` contains documents for course content, one `chapter_X.md` per topic
- `/assets/images` contains images that are embedded in the course content


## 1.2 Customizing the new repository

### About/index page
Start by adding information to the [About page](../../docs/index.md)

### Adding/removing menu items
The left side navigation menu is specified in the `nav:` section of the `mkdocs.yml`file

```yml
nav:
    - About: index.md
    - Course Content:
      - "How to set up a new repository based on the ELIXIR-TrP-LessonTemplate-MkDocs": chapters/chapter_01.md
      - "How to customize the ELIXIR-TrP-LessonTemplate-MkDocs": chapters/chapter_02.md
      - "How to add content using GitHub editor": chapters/chapter_03.md
```
Add the title to be displayed in the menu for each chapter like this: `"title": chapter/filename.md` followed by the file name of the chapter. 

To add a new item in the menu:
1. Add a new file if needed by:
    1. navigating to the `docs` folder and then clicking `Add file` on the top right
    2. name the new file
    3. commit the new file to the `main` branch at the bottom of the page
1. Add a row `"title": chapter/filename.md` to the `nav`section of the `mkdocs.yml` file


### Modify the footer
Modify the Licence statement in the footer by editing the following section of the `mkdocs.yml` file

``` yml
# Footer
copyright: Creation of this material was funded by project# and is made availiable under a CC-BY 4.0 licence
```

### Removing the banner
When the trainig material is no longer under active devlopment, remove the banner at the top by removing the following section of the `main.yml`file located in the `overrides` folder:

```html
{% block announce %}
This lesson is under active development and considered pre-alpha.
{% endblock %}
```

### Add course content 
See next chapter for instructions how to add course content 
