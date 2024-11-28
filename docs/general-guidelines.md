# GitHub Organization Guidelines

This documentation provides guidelines for contributing to this GitHub organization.
It includes rules, conventions, and best practices to to help contributors work together effectively while maintaining a structured and accessible organization for all projects.

![](./assets/logo_ifremer_cnrs_github_git.png)

## Why hosting my project on this GitHub organization ?

- If your project involves multiple contributors, potentially working in parallel.
- If it requires efficient change tracking with a detailed history.
- If versioning is essential for archiving or referencing in other works (e.g., papers, reports, or derivative projects).
- If it is designed to endure and evolve over time.

This organization welcomes all types of development, including low-level software, 3D-printed models, electronic PCB designs, datasets, high-level applications, and more.

💡 *This organization is intended for official public repositories. For temporary, sandbox, or experimental projects, it is recommended to use your personal GitHub account or the GitLab instances provided by IFREMER or LIRMM.*


## Naming conventions

### General best practices for GitHub names

Use descriptive names that clearly indicate the purpose or function of the project. 
Stick to lowercase and hyphens for readability and keep names short and concise. 
Avoid special characters, using only letters, numbers, and hyphens for compatibility. Include context or scope when relevant. 
Finally, choose names that are future-proof and remain relevant as the project evolves.
Ensure the name is unique and have fun choosing it !

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

For project invoving PCB design and fabrication of electronic board. Serves to share the source including BOM, PCB layout, 2D/3D model, datasheet, ...  

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

Text.

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
- `urelease-frontnose-tungstenwire-v2-3dmodel`
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

### Multi-Purpose Projects

Text.

### Other projects

Be inventive or descriptive and follow best practices!

Examples : 

- `DinoVdeau`
- `dataflux-agent`
- `lora-sensors-in-marine-scenario-mkdocs`
- `loraship-toolbox`
- ...



## Versioning the sources

Text.

## Structure for the repositories

Text.

## Publishing rules

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