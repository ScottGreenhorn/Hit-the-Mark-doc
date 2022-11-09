# Hit-the-Mark FAQ

### How did we come up with this idea?
While working on the Demand Sensing CPG project, we discovered that internal teams were having a hard time accessing accurate and timely information about configuration and deployment. We determined that Confluence wasn't a great tool for maintaining and delivering the configuration content. It was also difficult to extract content from Confluence to resuse it in other publsihing tools. Our goal was to try to find a better way of creating, maintaining, and publishing configuration and deployment content. That's when we started investigating using Markdown files and GitHub to create a better process.

### How is this process better than Confluence for delivering configuration content?
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

