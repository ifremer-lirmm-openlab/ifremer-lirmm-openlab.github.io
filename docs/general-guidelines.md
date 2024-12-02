# GitHub Organization Guidelines

This documentation provides guidelines for contributing to this GitHub organization.
It includes rules, conventions, and best practices to to help contributors work together effectively.

![](./assets/logo_ifremer_cnrs_github_git.png)

**Topics :**

- [Why hosting my project on this organization ?](#why-hosting-my-project-on-this-organization-)
- [Naming conventions](#naming-conventions)
- [Using branches during developpement](#using-branches-during-developpement)
- [Versioning the sources](#versioning-the-sources)
- [Structure of repositories](#structure-of-repositories)
- [Documenting the projects](#documenting-the-projects)
- [(Bonus) Tips and useful ressources](#bonus-tips-and-useful-ressources)

---

## Why hosting my project on this organization ?

- If your project involves multiple contributors, potentially working in parallel.
- If it requires efficient change tracking with a detailed history.
- If versioning is essential for archiving or referencing in other works (e.g., papers, reports, or derivative projects).
- If it is designed to endure and evolve over time.

This organization welcomes all types of development, including low-level software, 3D-printed models, electronic PCB designs, datasets, high-level applications, and more.

💡 *This organization is intended for official public repositories. For temporary, sandbox, or experimental projects, it is recommended to use your personal GitHub account or the GitLab instances provided by IFREMER or LIRMM.*


## Naming conventions

### General best practices for GitHub names

- Use descriptive names that clearly indicate the purpose or function of the project. 
- Stick to lowercase and hyphens for readability and keep names short and concise. 
- Avoid special characters, using only letters, numbers, and hyphens for compatibility.
- Finally, choose names that are future-proof and remain relevant as the project evolves.
- Ensure the name is unique and have fun choosing it !

### Naming rules for specific project types

We recommend the following naming conventions for the project types identified below. These are not strict rules but rather best practices to enhance readability.

> Legend : 
> `<...>` = word to replace. 
> `*` =  optional fields.

#### Embedded softwares

For projects involving source code or firmware targeting specific electronic platforms.

Recommend naming convention :

`<mainname>-<type>-<feature*>-<platform>-firmware`

Description :

- `mainname` : The primary name that relates to the application, project, institution, or a predefined special name.
- `type` : the device's type or function.
- `feature` : (optional) should relates to the main features, such as involved sensors, type of RF communication, algorithms, ...  
- `platform` : the target platform name

Examples : 

- `seaturtle-tag-depthlora-iotboard-firmware`
- `urelease-logger-depthgpslora-iotboard-firmware`
- `loraship-logger-gpslora-fncboard-firmware`
- `bia-sensor-embedfft-fncboard-firmware`
- `bananatwo-tracker-prestempargos-stm32l4-firmware`
- `echologgerS500-spicommunication-raspi-firmware`
- `edna-pumpcontroler-blueos-arduino-firmware`
- ...

#### Electronic boards and PCBs

For projects involving PCB design and fabrication of electronic board. These serve to share the source including BOM, PCB layout, 2D/3D model, datasheet, ...  

Recommend naming convention :

`<mainname>-<feature*>-<version*>-cadfiles`

Description :

- `mainname` : The primary name that relates to the application, project, institution, or a predefined special name.
- `feature` : (optional) should relates to the main features, such as the embeded sensors, major or new functions, type, ... 
- `version` : (optional) Use it to differentiate major changes in design, if all version will be maintained over time.

Examples : 

- `iotboard-multisensorlora-cadfiles`
- `fncboard-multisensorlora-v1-cadfiles`
- `fncboard-multisensor-v2-cadfiles`
- `biaboard-externadc-cadfiles`
- `argoskineis-daugtherboard-v1-cadfiles`
- `cricketl0-assettrackerlora-cadfiles`
- ...

#### 3D-printed models

Projects to share sources of 3D-printed design.

Recommend naming convention :

`<mainname>-<type*>-<feature*>-<version*>-3dmodel`

Description :

- `mainname` : The primary name that relates to the application, project, institution, or a predefined special name.
- `feature` : (optional) should relates to the main features or specificity.
- `version` : (optional) Use it to differentiate major changes in design, if all version will be maintained over time.

Examples : 

- `seaturtle-tag-externant-v1-3dmodel`
- `fish-tag-survivalrate-v1-3dmodel`
- `urelease-tag-magconnector-3dmodel`
- `dcp-logger-solarpowered-3dmodel`
- `plancha-antennasupport-circular-3dmodel`
- ...

### Datasets, Data analysis and Data viewers

Projects to share dataset, analysis scripts, data workflow, ...
Oten demanded by scientific journals to support the publication. 

Recommend naming convention :

`<anyname>-dataset`, `<anyname>-dataprocessing`,  `<anyname>-workflow`, `<anyname>-dashboard` or `<anyname>-dataviewer`

Names can have a `<version>` field at the end if need.

Description :

- `anyname` : Any names that reflects the content. Names should be future-proof if cited in publication.

Examples : 

- `seaturtle-tag-diving-indianocean-2022-dataset`
- `plancha-workflow-v1`
- `loraship-expe-autoreport-dataprocessing`
- `urelease-taaf-dashboard`
- ...


### Other projects

Be inventive or descriptive and follow best practices!

Examples : 

- `DinoVdeau`
- `dataflux-agent`
- `lora-sensors-in-marine-scenario-mkdocs`
- `loraship-toolbox`
- ...

## Using branches during developpement

Branching is one of Git’s most powerful features to help you avoid mixing up different lines of development. You should use branches extensively in your development workflows: for new features, bug fixes, experiments, ideas…

For most of our developments, we recommend following the standardized **GitHub Flow** (see image below). This approach involves maintaining a `main` branch while creating parallel branches for new features or bug fixes. These branches are regularly merged back into `main` once the code is stable and reviewed. Stable states of the `main` branch are marked using *tags* and the *release* mechanism for archiving and future reference (see the section [Versioning the Sources](#versioning-the-sources) below).

![](./assets/github_workflow_diagram.png)

*Figure. Illustration of the GitHub Flow. [Image source](https://medium.com/@sreekanth.thummala/choosing-the-right-git-branching-strategy-a-comparative-analysis-f5e635443423).*

🔍 Consult these links for more details about git branches and the GitHub workflow :

- [https://about.gitlab.com/topics/version-control/version-control-best-practices/](https://about.gitlab.com/topics/version-control/version-control-best-practices/)
- [https://docs.github.com/en/get-started/using-github/github-flow](https://docs.github.com/en/get-started/using-github/github-flow)
- [https://medium.com/@sreekanth.thummala/choosing-the-right-git-branching-strategy-a-comparative-analysis-f5e635443423](https://medium.com/@sreekanth.thummala/choosing-the-right-git-branching-strategy-a-comparative-analysis-f5e635443423)


## Versioning the sources

Git provides powerful features for tracking and managing source versions through objects called *Tags* and *Releases*.  *Releases* are deployable software iterations you can package and make available for a wider audience to download and use. Releases are based on *Tags*, which mark a specific point in your repository's history. 

In our workflow, we will use *Tags* and *Releases* to mark important steps during the project lifetime.
These include versions used for specific experiments, final designs intended for production or fabrication, and project states that need to be referenced in technical reports or scientific papers.

Namming the versions follows a standardized procedure that is based on the [Semantic Versioning 2.0.0](https://semver.org/) specification.

Recommend naming convention : 

`v<major>.<minor>.<patch>-<extraname*>`

Description :

- `major` : Major increments when new functionality is not backwards compatible
- `minor` : Minor increments every time backwards compatible functionality is added.
- `patch` : Patch increments every time you release a build with bug fixes or small changes.
- `extraname` : (Optional) this field can serve to add a more readable information to better identify the purpose of this release.

Examples : 

- `v1.0.0` (start of the design. Version below that are test ones that wont be published)
- `v1.0.5` (small changes or bug fixes)
- `v1.1.0` (new feature added)
- `v1.1.2-expemalte2022` (version used for experiment in Malte in 2022)
- `v1.1.3-papernature2023` (version referenced in a publication in 2023)
- `v2.0.0` (marks major changes were the design has changed a lots in term of functionnalities)
- ...

🔍 Consult this link to learn how to create a *Tags* and *Releases* for a GitHub project : 
[https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository?tool=webui](https://docs.github.com/en/repositories/releasing-projects-on-github/managing-releases-in-a-repository?tool=webui).


💡 *A specific case where multiple versions of a design require separate repositories arises when these versions will be independant, both maintained and will evolve in parallel. In such situations, it is best to create a dedicated Git repository for each version, using names that relates to each others.*




## Structure of repositories

Text.


## Documenting the projects

Text.

## (Bonus) Tips and useful ressources

### Tips for git 

Cloning a git repository to your machine 

```
# Replace `owner/repo` with the owner and name of the repository to clone
git clone https://github.com/owner/repo.git

# change into the `repo` directory
cd repo
```

Checking and publishing changes on the `main` branch

```
# check the sate of your local files against the distant repository
git status

# make changes to local files
# for example, edit `file1.md` and `file2.md` using the text editor

# stage the changed files
git add file1.md file2.md

# take a snapshot of the staging area (anything that's been added)
git commit -m "my commit message"

# push changes to github
git push origin main
```

Creating and modifying a new branch

```
# create a new branch to store any new changes
git branch my-branch

# switch to that branch (line of development)
git checkout my-branch

# make changes, for example, edit `file1.md` and `file2.md` using the text editor

# stage the changed files
git add file1.md file2.md

# take a snapshot of the staging area (anything that's been added)
git commit -m "my commit message"

# push changes to github
git push --set-upstream origin my-branch
```

### External Docs and Useful Links

#### Working with Git

Basis for Git :

[https://docs.github.com/en/get-started/using-git](https://docs.github.com/en/get-started/using-git)

[https://git-scm.com/docs](https://git-scm.com/docs)

Git with Visual Studio Code :

[https://code.visualstudio.com/docs/sourcecontrol/intro-to-git](https://code.visualstudio.com/docs/sourcecontrol/intro-to-git)

#### Working with Markdown files

Getting started : 

[https://www.markdownguide.org/getting-started/](https://www.markdownguide.org/getting-started/)

Basic syntax : 

[https://www.markdownguide.org/basic-syntax/](https://www.markdownguide.org/basic-syntax/)

Markdown in Python :

[https://www.honeybadger.io/blog/python-markdown/](https://www.honeybadger.io/blog/python-markdown/)

[https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.to_markdown.html](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.to_markdown.html)

#### Choosing an open source license

List of commons open-source license :

[https://choosealicense.com/](https://choosealicense.com/)

[https://choosealicense.com/appendix/](https://choosealicense.com/appendix/)

The MIT license : 

[https://en.wikipedia.org/wiki/MIT_License](https://en.wikipedia.org/wiki/MIT_License)

The Creative Commons license : 

[https://creativecommons.org/share-your-work/cclicenses/](https://creativecommons.org/share-your-work/cclicenses/)

#### Building your documentation

Using Mkdocs tool :

[https://www.mkdocs.org/getting-started/](https://www.mkdocs.org/getting-started/)

Using GitHub pages :

[https://docs.github.com/en/pages/getting-started-with-github-pages](https://docs.github.com/en/pages/getting-started-with-github-pages)