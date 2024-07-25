
## Creating a new repository

### Create a new repository from the template

In your web browser, browse to the [ELIXIR-TrP-LessonTemplate-MkDocs](https://github.com/elixir-europe-training/ELIXIR-TrP-LessonTemplate-MkDocs) repository on GitHub. Click the green **Use this template** button on the top right.

In the pop-up window:

   1. Choose an organisation where the repository will be hosted (typically elixir-europe-training)
   2. Enter a name for the new repository (keep in mind that this will be part of the URL)
   3. Decide if the repository should be Public (most likely) or Private
   4. Make sure to tick `Include all branches`
   5. Click **`Create repository from template`**

<figure>
    <img src="../../assets/images/create_from_template.png" width="800"/>
</figure>

### Add collaborators

Go to settings and select `Collaborators and teams` under `Access` in the left side menu 

1. Click one of the green buttons `add people`  or `add teams`
2. Select a person or a team to invite
3. Selet the appropriate role 
4. Click `add user to this repository`

### Update the README.md

1. Go to the `<> Code` tab and click the README.md file
2. Add information about the new ELIXIR Lesson.

## Using github actions to deploy gh-pages

### Go to settings and select `pages` in the left side menu
       
<figure>
<img src="../../assets/images/settings-pages-02.png" width="800"/>
</figure>

1. click on `None`under Branch and select the `gh-pages` branch
2. press `Save`

 When the site is deployed, it will take a few minutes, a box on top will display the url to the live site.

### Go to settings and select Actions -> General in the left side menu

<figure>
<img src="../../assets/images/settings_actions.png" width="600"/>
</figure>

1. at the top under `Actions permissions` check the option "Allow all actions and reusable workflows"     
2. scroll down to `Workflow permissions`and check the options "Read and Write permissions" + "Allow GitHub Actions to create and approve pull requests"

### Add URL to About section of the repository

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


### Update site name, repository name and url in the mkdocs.yml file

1. Go to the `<> Code` tab and edit the mkdocs.yml file
2. Update the `site_name` tag at the top of the file to the name of your lesson.
3. Update the **Repository** section with the respective `repo_name`and `repo_url` of the lesson you have just created.
