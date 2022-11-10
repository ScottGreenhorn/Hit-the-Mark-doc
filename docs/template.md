# Site setup
Quick guide to setting up a Jekyll site to plug in content.

This assumes the Just the Docs template is being used to publish a site to Github Pages.

## Copy the template
To begin, the Just the Docs template is available as a starting point for the new page. The template includes the Jekyll and Ruby components that are required, and does not require any additional local resources.

### Create a repo from the template
1. In Github, navigate to the [Just the Docs template](https://github.com/just-the-docs/just-the-docs-template)
2. Click the **Use this template** button
3. In the **Create a new repository** page, in the **Owner** box, specify your Github user name
1. In the **Repository name** box, specify the name for the repository that will use the template
1. In the Public/Private area, select whether the new repo is publicly available or private to you.
1. Click **Create repository from template**.

The template creates a repository with the Just the Docs default branding and settings.

## Configure the template site
Configurations for the site's appearance are set in the _config.yml file. This is a YAML file that defines the settings for each page in the site, and can include the URL for the site, styles, and the 'edit this page' link for editing the markdown files in Github.

### Configure the _config.yml file
1. In the root of your repo, click **_config.yml**
2. Click the pencil button to begin editing.
3. When finished, click **Commit changes**, and optionally specify or create a branch to make the changes in.

### Configure site information
1. Edit the **_config.yml** file.
2. Modify the following:
- **title**: The title for the site. This appears at the top of the sidebar and the title bar of the homepage
- **description**: Metadata information about the site
- **url**: The URL for the site. If you are using Github Pages, this should be `https://your-user-name.github.io`

  For example, https://ScottGreenhorn.github.io 
- **baseurl**: The repo name, preceded by a /, to be appended to the url to create the full site address.
 
  For example, `/Hit-the-Mark-doc`
- **aux_links**: Any additional links to display on the page header, each specified as `Name:URL` pairs

### Add the edit link
1. Edit the **_config.yml** file.
2. At the bottom of the file, add the following:
`gh_edit_link: true # show or hide edit this page link`
`gh_edit_link_text: "Text to display"`
`gh_edit_repository: "url-of-your-repo" # the github URL for your repo`
`gh_edit_branch: "main" # the branch that your docs are served from`
`gh_edit_view_mode: "edit" # "tree" or "edit" if you want the user to jump into the editor immediately`

## Set up publishing
By default, sites publish to Github Pages and are available from the link you create in the _config.yml file. To publish the page, a Gihub action is required. This action automatically builds and publishes the page, and runs every time you update a file in the repo. 

Only the repo owner can configure this. 

### Configure the publish action
1. In your repo, click the **Settings** tab.
2. In the sidebar, under **Code and automation**, click **Pages**.
3. Under **Build and deployment**, select **Github Actions**
3. This automatically configures the **Deploy Jekyll site to Pages** workflow defined in the template.

If you want to use a different publishing workflow, you can create a custom workflow as a Github Action. 

## Adding content to the site
By default, the template includes an index.md file that is used as the home page for the site. Any additional content you define should be in markdown files and can use any folder structure you feel is appropriate. 

For example, you can creates a docs folder that stores all your content, and to create nested pages, you can use subfolders under the docs folder to define the level for each page.

Navigation for the pages can be set by including a YAML frontmatter in the files, which Jekyll uses to define the order of pages to list in the sidebar and the relationship between files.

### Create folders
Folders in Github must contain at least one file, so this procedure focuses on creating folders that can be populated by dragging and dropping files or by creating additional files in using the Github editor.

1. In the Github repo, click the **Code** tab.
2. Click **Add file**, and then click **Create new file**.
3. In the **Name your file** box, type the name for your folder, and then type **/**
4. The name you specified is automatically put into the path.
5. In the **Name your file** box, specify a name for the file. If you are creating markdown files, ensure your file name includes the **.md** extension.
6. Optionally, add some content to the file.
7. Click **Commit new file**.

### Upload files
You can upload files by dragging them from your local computer into the github interface, by pushing from a local Git repo, or by using the Upload file from the add a file button.

If you upload files in folders, the folder structure is maintained.

### Add links and images
If you want to include images in your pages, a single images folder is recommended. When you include the image in the page, you must consider the level of the image folder and the content folder the page is in. Jekyll assumes the path to the image is defined relative to the page's folder, so it might be necessary to go up levels to reach the images folder.

To specify higher levels in the path, add .. for each level. 

For example `../image/whatever.png` goes up one level to reach the images folder.

If you have a deeply nested page, you can add as many repetitions of the ../ to go up the number of levels you require to reach the images folder.
```
docs
	images
	content
		info
			file.md
```
For example, if you are adding an image to the file.md shown in the example folder structure above, the path to the image would be `../../images/image.png`

If you are linking to other pages within the site, you must consider how the Jekyll site is generated. Alkthough all the source files are markdown (.md files), the Jekyll site generates all pages as html.

Therefore, any links must define the path to the page (similar to images), and use the .html extension.

Links generated by Jekyll, such as the sidebar content, are automatically generated as html links.

### Define navigation
Each page you want to process must have a YAML frontmatter in the markdown file. This is the first thing in the file, and is a block defined using a triple dash at the beginning and end. This block can be blank, but shouldn't be.

An example of a YAML frontmatter is shown in the following:
```
---
layout: default
title: Meeting the Humans
nav_order: 2
---
```

This example defines a layout, which can be used to create types of pages, a title for the page, which is displayed in the sidebar, and a navigation sequence, which defines the order of links in the sidebar.

In this example, the 'Meeting the Humans' page is the second one displayed in the sidebar.

#### Nesting pages
If a page has pages under it, you can define a parent-child relationship between the pages in the YAML frontmatter. This creates a expanding droplist in the sidebar, which displays each child page under the parent. 

A nested page structure uses a separate nav order for the child pages, independent of the nav order for the higher-level pages. 

The parent page must contain the following in its YAML frontmatter:
`has_children: true`

The child page must contain the following:
`parent: parent_topic_title`

For example, assume you have a page titled Preparation that has a child page named Appearance. To define the Preparation page as a parent, its YAML frontmatter would be:

```
---
layout: default
title: Preparation
nav_order: 3
has_children: true
permalink: /docs/preparation
---
```

The Appearance page would have the following:
```
---
layout: default
title: Appearance
parent: Preparation
nav_order: 1
---
```
This makes the Appearance page the first page under the Preparation page when it is expanded in the sidebar.

The permalink item in the frontmatter is optional, and defines the output URL for the page. You can use this to hide the file names and paths if desired.