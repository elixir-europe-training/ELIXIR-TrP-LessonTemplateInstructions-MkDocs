# How to customize the ELIXIR-TrP-LessonTemplate-MkDocs
## 1.1 File strucutre overview
### index.md
This file renders the home page of the website and is found in the `/docs`folder. This is the first page a visitor to the website will see when using the base URL. It is by default called `About`in this template. It contains information about the trainig material and most headings corresponds to a Bioschemas property.
### mkdocs.yml
This file is where most of the layout options are made and where the [MkDocs](https://www.mkdocs.org/) theme [Material](https://squidfunk.github.io/mkdocs-material/) is specified. The navigation menu is customised here as well as the header and footer etc. 
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
Start by adding information to the About page (index.md).

### Adding/removing menu items
The left side navigation menu is specified in the `nav:` section of the `mkdocs.yml`file.  Add the title to be displayed in the menu for each chapter like this: `"title": chapters/filename.md` followed by the file name of the chapter. 

To add a new item in the menu:

1. Add a new file if needed by:
    i. navigating to the `docs` folder and then clicking `Add file` on the top right
    ii. name the new file
    iii. commit the new file to the `main` branch at the bottom of the page
2. Add a row `"title": chapter/filename.md` to the `nav`section of the `mkdocs.yml` file


### Modify the footer
Modify the Licence statement in the footer by editing the following section of the `mkdocs.yml` file

``` yml
# Footer
copyright: Creation of this material was funded by project# and is made availiable under a CC-BY 4.0 licence
```

### Removing the banner
When the training material is no longer under active devlopment, remove the banner at the top by removing the following section of the `main.html`file located in the `overrides` folder:

```html
{% block announce %}
This lesson is under active development and considered pre-alpha.
{% endblock %}
```

### Changing bioschemas json

In `overrides/main.html` there's also a block `site_meta`: 

```html
{% block site_meta %}
<script type="application/ld+json">
  {
    "@context": "https://schema.org/",
    "@type": "LearningResource",
    "@id": "https://elixir-europe-training.github.io/ELIXIR-lesson-template/",
    "http://purl.org/dc/terms/conformsTo": {
        "@type": "CreativeWork",
        "@id": "https://bioschemas.org/profiles/TrainingMaterial/1.0-RELEASE"
    },
    "description": "Template for ELIXIR lessons",
    "keywords": "FAIR, OPEN, Bioinformatics, Teaching",
    "name": "ELIXIR TrP lesson template",
    "license": "https://creativecommons.org/licenses/by/4.0/"
}
</script>
{% endblock %}
```

Change and add items to the json according to your requirements. More info on bioschemas TrainingMaterial profile [here](https://bioschemas.org/profiles/TrainingMaterial/1.0-RELEASE). 

### Add course content 
See next chapter for instructions how to add course content 
