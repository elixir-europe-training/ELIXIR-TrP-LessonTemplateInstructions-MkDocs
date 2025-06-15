
## File structure overview

The most important files in the repository are markdown (`.md`) files, containing the website content, and configuration files that specify the layout and theme of the website. The most important configuration file is `mkdocs.yml` which specifies the layout and theme of the website. Below we explain the most important files and how to customize them.

The template is based on [mkdocs material](https://squidfunk.github.io/mkdocs-material/), so most features are inherited from this theme, and ample documentation can be found on their [website](https://squidfunk.github.io/mkdocs-material/).

### index.md

This file renders the home page of the website and is found in the `/docs`folder. This is the first page a visitor to the website will see when using the base URL. It is by default called `About`in this template. It contains information about the trainig material.

### mkdocs.yml

This file is where most of the layout options are made and where the [MkDocs](https://www.mkdocs.org/) theme [Material](https://squidfunk.github.io/mkdocs-material/) is specified. The navigation menu is customised here as well as the header and footer etc. 

### README.md

This file is displayed by default on the main page of the GitHub repository and liked in the About section. It should contain important information about the repository on how to use the material and explain how to contribute. 

### LICENCE.md
This file is linked in the `About section` of the GitHub repository and should contain a full licence statement. By default it is set to the Creative Commons [Attribution-ShareAlike 4.0 International (CC BY-SA 4.0) license](https://creativecommons.org/licenses/by-sa/4.0/legalcode). This file is also used to specify the licence for the Zenodo record of the lesson if using the Zenodo-Github integration.

### .zenodo.json
This file is used to specify metadata for the Zenodo record of the lesson. It is empty by default. Refer to the [Credit and recognition chapter](../chapters/chapter_04.md#prepare-a-zenodojson-file) for instructions on how to populate this file. 

### CITATION.CFF
This file is used to specify metadata for the lesson in a format that can be used by the [Citation File Format (CFF)](https://citation-file-format.github.io/). It is used to provide information about how to cite the lesson in the `About section` of the GitHub repository. As a default, this file contains citation information for the lesson template itself. You need to edit this file to provide citation information for your lesson.


### docs folder

The docs folder contains several subfolders

- `/chapters` contains documents for course content, one `chapter_X.md` per topic
- `/assets/images` contains images that are embedded in the course content


## Customizing the new repository

### About/index page

Start by adding information to the About page (index.md).

### Adding/removing menu items

The left side navigation menu is specified in the `nav:` section of the `mkdocs.yml`file.  Add the title to be displayed in the menu for each chapter like this: `"title": chapters/filename.md` followed by the file name of the chapter. 

To add a new item in the menu:

1. Add a new file if needed by:
    1. navigating to the `docs` folder and then clicking `Add file` on the top right
    2. name the new file
    3. commit the new file to the `main` branch at the bottom of the page
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

### Adding bioschemas markup

For adding metadata to your training material, it is recommended to use [bioschemas](https://bioschemas.org/) markup. More info on bioschemas TrainingMaterial profile [here](https://bioschemas.org/profiles/TrainingMaterial). 

To add bioschemas to your website html use the extension [`addbioschemas`](https://pypi.org/project/addbioschemas/). Everything should be set up in the template to use this extension.

To add metadata create either a json or yaml file with bioschemas markup. In the template, an example is stored in `_data`:

```yaml title='_data/metadata.yml'
"@context": https://schema.org/
"@type": LearningResource
"@id": https://elixir-europe-training.github.io/ELIXIR-TrP-LessonTemplate-MkDocs/
http://purl.org/dc/terms/conformsTo:
  "@type": CreativeWork
  "@id": https://bioschemas.org/profiles/TrainingMaterial/1.0-RELEASE
description: Template for ELIXIR lessons
keywords: FAIR, OPEN, Bioinformatics, Teaching
name: ELIXIR Training Lesson template
# lookup at https://spdx.org/licenses/
license: CC-BY-4.0
author:
- "@type": Person
  name: Geert van Geest
  email: geert.vangeest@sib.swiss
  github: GeertvanGeest
  orcid: 0000-0002-1561-078X
- "@type": Person
  name: Elin Kronander
  github: elinkronander
  orcid: 0000-0003-0280-6318
```

After that, add a placeholder in the markdown file you'd like to add the metadata to:

```markdown 
[add-bioschemas file='_data/metadata.yml']
```

!!! important "Markdown before placeholder"
    In combination with mkdocs-material the placeholder should be placed after markdown text, so never at the very top of the page. See this [GitHub issue](https://github.com/GeertvanGeest/addbioschemas/issues/5). 

<!-- This wi ll result in a formatted json-LD script tag in the html body.  -->

### Add course content

See next chapter for instructions how to add course content 
