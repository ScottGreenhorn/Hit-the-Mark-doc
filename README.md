# Hit-the-Mark FAQ

### How did we come up with this idea?
Necessity is the mother of invention. While working on the Demand Sensing CPG project, we discovered that internal teams were having a hard time accessing accurate and timely information about configuration and deployment. We determined that Confluence wasn't a great tool for maintaining and delivering the configuration content. It was also difficult to extract content from Confluence to reuse it in other publishing tools. 

Our goal was to try to find a better way of creating, maintaining, and publishing configuration and deployment content. That's when we started investigating using Markdown files and GitHub Pages to create a better process. 

### Why GitHub and markdown?
Teams developing ML tools and processes already have markdown readme files for their work, and those of us without access to the repos cannot access that information. Because development happens at a quicker pace, the confluence pages get out of date quickly. Because downstream teams only have access to the confluence pages, things can get missed.

Markdown is a very simple text format with a well-defined set of formatting options, which makes it quick and easy to write. Because of the simplicity of the files, it is also highly reusable, and can be imported into most text editors or help authoring tools. In addition, GitHub provides the ability to convert markdown files into a static site, which can provide access tot he markdown content to many additional audiences. 

Because these tools are already in use, it just made sense to work with them.

### How is this process better than current tools for delivering configuration content?
We feel that this process is superior because you can:
+ Maintain one source of the "truth".
+ Publish only the required information. No more having to navigate through outdated or incomplete Confluence pages.
+ Copy a repository to create a new version.
+ Establish clear ownership of the content.
+ Collaborate or comment on the content.
+ Reuse Markdown content in other locations (e.g. Confluence).
+ People using the site can edit the page if they see something is out of date or incorrect.

### Can we use it for other types of content?
Yes, we think it could have other uses. For example, it could be a better way to deliver Help for our Applications (e.g. Demand Planning, Life Sciences template). Because customers often modify resources to reflect their processes, the Applications Help doesn't always reflect what the end users see. To resolve this issue, we could create Help content in Markdown that relfects the default state of the Application. However, you can provide a copy of the Help repository to a customer so they could modify the content themselves to reflect any changes that they made.

### What did the team actually do?
To demonstrate how to convert markdown into a site accessible by multiple audiences, we populated this repository with some markdown files and converted them into a site using GitHub Pages (built-in functionality from GitHub), the Jekyll static site generator (hosted by GitHub), and the Just the Docs Jekyll theme (free and configurable).

The repository started as a clone of the Just the Docs theme's template, which automatically included the Jekyll configuration required to generate the site. We then created the markdown files that contained the content we wanted to present. The repository is configured to use a GitHub Action to publish the static site to GitHub Pages, and the site is updated each time a markdown file is modified. This ensures changes are available with minimal delay and the information on the site is always current.

We configured the site's name, included search capability, and added GitHub edit links on each page through the site's configuration YAML file. In each markdown file, we defined navigation by configuring a YAML frontend in each file. This defines the parent-child relationship between nested pages, the order of topics displayed in the sidebar of the pages, and a name and permanent link for each page.

Though our example pages are not technical in nature, the same concepts can be applied to deployment and configuration content across the ML repositories, and we would like to generate a site using them.

### What tools did you use to create this Help system?
We used the following tools:
+ [GitHub Pages](https://pages.github.com/)
+ [Jekyll](https://jekyllrb.com/)
+ [Ruby](https://www.ruby-lang.org/en/)
+ [Just-the-docs Jekyll theme](https://just-the-docs.github.io/just-the-docs/)

### Where can I view a copy of the generated Help? 
You can view the generated help in the following location https://scottgreenhorn.github.io/Hit-the-Mark-doc/

### What else did you consider?
An initial idea for this project was to get markdown content out of Github and upload it to Confluence. This proved to be a bit unnecessary once we got the Jekyll site working and figured out how easy it was to add pages to it by including specific frontmatter content in the markdown files. While investigating the idea of moving data out of (and possibly back in to) Github, we discovered a plugin for Confluence on the [Atlassian marketplace](https://marketplace.atlassian.com/apps/1216106/github-links-for-confluence?hosting=cloud&tab=overview).

Because this is a Confluence plugin we obviously couldn't install and test it, but it might be an option to fulfill the idea of authoring the content in one place and making it available in multiple places that is the heart of this project.

We are also evaluating a free open source markdown authoring tool named [GhostWriter](https://github.com/KDE/ghostwriter/releases/tag/2.1.6). This is a lightweight and very simple markdown editor that provides all the markdown syntax in a side panel for quick reference. We did not perform a full evaluation as of this writing, but at least one team member was able to download it and create a page with headings, lists, and images within minutes. We feel it could be a strong candidate for people not familiar with markdown to write content.

Though it seems only local files are supported in Ghostwriter, a local clone of the repository for people to edit and push updates is a safe expectation for people who would be writing and updating these files.
