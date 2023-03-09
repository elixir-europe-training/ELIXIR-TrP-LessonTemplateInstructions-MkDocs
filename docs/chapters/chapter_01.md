# How to set up a new repository based on the ELIXIR-TrP-LessonTemplate-MkDocs"

## 1.1 Creating a new repository
#### Go to [https://github.com/elixir-europe-training/ELIXIR-TrP-lesson-template](https://github.com/elixir-europe-training/ELIXIR-TrP-lesson-template), then: 
#### 1.  Click the green `use template` button to the top right and choose `Create a new repository`. 
  
 <figure>
    <img src="../../assets/images/create_from_template.png" width="800"/>
    </figure>
In the pop-up window:

   1. Choose an organisation where the repository will be hosted
   2. Enter a name for the new repository (keep in mind that this will be part of the URL)
   3. Decide if the repository should be Public (most likely) or Private
   4. Make sure to tick `Include all branches`
   5. Click `Create repository from template`

#### 2. Add collaborators
Go to settings and select `Collaborators` under `Access` in the left side menu 

1. Click one of the green buttons `add people`  or `add teams`
2. Select a person or a team to invite
3. Selet the appropriate role 
4. Click `add user to this repository`

#### 3. Update the README.md
1. Go to the `<> Code` tab and click the README.md file
2. Add information about the new repository
    - Who has requested this repository
    - What project or which ELIXIR-node is this repository being used in 


## 1.2 Using github actions to deploy gh-pages
#### 1. Go to settings and select `pages` in the left side menu
       
<figure>
<img src="../../assets/images/settings-pages-02.png" width="800"/>
</figure>

1. click on `None`under Branch and select the `gh-pages` branch
2. press `Save`

 When the site is deployd, it will take a few minutes, a box on the top will display the url to th live site.

#### 2. Go to settings and select actions in the left side menu

<figure>
<img src="../../assets/images/settings_actions.png" width="600"/>
</figure>
    
1. scroll down to `Workflow permissions`
1. check the option "Read and Write permissions" 

#### 3. Add URL to About section of the repository

1. Go to the `<> Code` tab and click the `About`settings wheel on the right side
    <figure>
  <img src="../..//assets/images/repo_about_settings01.png" width="800"/>
    </figure>
2. In the pop-up `Edit repository details`: 
    1. tick the `Use your GitHub Pages website` to automatically fill the Website URL
    <figure>
  <img src="../..//assets/images/repo_about_settings02.png" width="600"/>
    </figure>
    3. press `Save changes`


#### 4. Update site name, repository name and url in the mkdocs.yml file
1. Go to the `<> Code` tab and edit the mkdocs.yml file
2. Update the site name at the top of the file by editing the following

``` yml
site_name: Instructions how to use the ELIXIR-TrP-LessonTemplate-MkDocs
```

2. Update the section below with the `repo_name`and `repo_url`

``` yaml
#Repository
repo_name: elixir-europe-training/ELIXIR-TrP-LessonTemplateInstructions-MkDocs
repo_url: https://github.com/elixir-europe-training/ELIXIR-TrP-LessonTemplateInstructions-MkDocs
```
