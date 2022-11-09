# Hit-the-Mark FAQ

### How did we come up with this idea?
Necessity is the mother of invention. While working on the Demand Sensing CPG project, we discovered that internal teams were having a hard time accessing accurate and timely information about configuration and deployment. We determined that Confluence wasn't a great tool for maintaining and delivering the configuration content. It was also difficult to extract content from Confluence to resuse it in other publsihing tools. Our goal was to try to find a better way of creating, maintaining, and publishing configuration and deployment content. That's when we started investigating using Markdown files and GitHub Page to create a better process.

### How is this process better than current tools for delivering configuration content?
We feel that this process is superior because you can:
+ Maintain one source of the "truth".
+ Publish only the required information. No more having to navigate through outdated or incomplete Confluence pages.
+ Copy a repository to create a new version.
+ Establish clear ownership of the content.
+ Collaborate or comment on the content.
+ Reuse Markdown content in other locations (e.g. Confluence).

### Can we use it for other types of content?
Yes, we think it could have other uses. For example, it could be a better way to deliver Help for our Applications (e.g. Demand Planning, Life Sciences template). Because customers often modify resources to reflect their processes, the Applications Help doesn't always reflect what the end users see. To resolve this issue, we could create Help content in Markdown that relfects the default state of the Application. However, you can provide a copy of the Help repository to a customer so they could modify the content themselves to reflect any changes that they made.

### What tools did you use to create this Help system?
We used the following tools:
+ [GitHub Pages](https://pages.github.com/)
+ [Jekyll](https://jekyllrb.com/)
+ [Ruby](https://www.ruby-lang.org/en/)
+ [Just-the-docs Jekyll theme](https://just-the-docs.github.io/just-the-docs/)

### Where can I view a copy of the generated Help? 
You can view the generated help in the following location https://scottgreenhorn.github.io/Hit-the-Mark-doc/

### What else did we consider?
An initial idea for this project was to get markdown content out of Github and upload it to Confluence. This proved to be a bit unnecessary once we got the Jekyll site working and figured out how easy it was to add pages to it by including specific frontmatter content in the markdown files. While investigating the idea of moving data out of (and possibly back in to) Github, we discovered a plugin for Confluence on the [Atlassian marketplace](https://marketplace.atlassian.com/apps/1216106/github-links-for-confluence?hosting=cloud&tab=overview)
Because this is a Confluence plugin we obviously couldn't install and test it, but it might be an option to fulfill the idea of authoring the content in one place and making it available in multiple places that is the heart of this project.
We are also evaluating a free open source markdown authoring tool named [GhostWriter](https://github.com/KDE/ghostwriter/releases/tag/2.1.6). This is a lightweight and very simple markdown editor that provides all the markdown syntax in a side panel for quick reference. We did not perform a full evaluation as of this writing, but at least one team member was able to download it and create a page with headings, lists, and images within minutes. We feel it could be a strong candidate for people not familiar with markdown to write content.
Though it seems only local files are supported in Ghostwriter, a local clone of the repository for people to edit and push updates is a safe expectation for people who would be writing and updating these files.
