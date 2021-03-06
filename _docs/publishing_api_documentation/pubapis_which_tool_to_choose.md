---
title: "Which tool to choose for API docs &mdash; my recommendations"
permalink: /pubapis_which_tool_to_choose.html
course: "Documenting REST APIs"
sidebar: docapis
weight: 7.6
section: publishingapis
path1: /publishingapis.html
redirect_from:
- /learnapidoc/pubapis_tools_vs_content.html
---

I described a smattering of tools in [Docs-as-code tool options for developer docs](pubapis_docs_as_code_tool_options.html). Which solution should you choose? It's a complicated decision that will invariably involve tradeoffs. As I said earlier, the decision depends on your skillset, product, environment, and requirements. But here's my general recommendation. First, identify what authoring requirements you have. Then decide on a static site generator, and then consider a hosting and deployment platform.

Also, note that I don't have total familiarity with all of these tools and solutions. My core experience with docs-as-code tools involves Jekyll, GitHub Pages, and internally developed publishing pipelines. I have only dabbled or experimented with a lot of these other tools and platforms, so I can't speak authoritatively about them.

* TOC
{:toc}

## Define your requirements

The first step to selecting a tool is to define your authoring requirements. Start by answering the following questions:

* Will engineers be heavily authoring and collaborating on the content?
* Does your security group restrict you from using third-party platforms to host documentation, such as GitHub?
* Do you have existing internal infrastructure that you want to hook into for storing and automatically building your site?
* Do you have engineering resources available to implement your own continuous delivery publishing workflow?
* Do you have a strong familiarity with a particular programming language?
* Approximately how many documentation pages do you have in your project?
* Do you have some web development skills (or access to UX resources) to design or modify your theme?
* Do you have an available budget to pay for a 3rd-party hosting and deployment option?
* How many authors will be authoring directly as contributors in the system?
* Do you have a need to authenticate documentation for specific users? Is there an existing authentication system already in place at your company?
* Do you need to integrate your docs directly into your larger company site, with the same branding and appearance?
* Do you need to localize the content? How many other languages? Are there formatting requirements imposed by your translation vendor and system?
* Do you need to create PDF deliverables for the content (in addition to web output)? How will you review the content with SMEs?
* Do you want a lot of control and flexibility to extend or customize the solution with your specific doc's needs, which might involve custom scripting or integration with another system?
* Can you use an external search service such as Swiftype, Algolia, or Google Custom Search?
* To what extent do you need to re-use the same content in multiple instances or outputs?
* Do you have to version your content with each new release?

Now that you've gathered some data about requirements, understand that you're probably not going to find a single system that does all of what you need. There are tradeoffs with every tool choice. The question is which features you want to *prioritize*.

Maybe it's more important to minimize the custom coding of a theme than it is to have complete control and flexibility over the solution. Or perhaps a modern web output is more important than the ability to build PDFs. Or perhaps you must have authentication for your docs, but you also don't have a budget. There are going to be some hard decisions to make.

## 1. Select a static site generator

If you want power and control to create the complex features you need (maybe you want to build a custom theme or build your doc site with unique branding), then use a static site generator such as [Hugo](pubapis_docs_as_code_tool_options.html#hugo), [Sphinx](pubapis_docs_as_code_tool_options.html#sphinx), or [Jekyll](#pubapis_docs_as_code_tool_options.html). If you have serious doc needs (or maybe you migrated from the world of DITA and are used to more robust tooling?), you're going to want a platform that can go as deep as you want to take it. Jekyll, Sphinx, and Hugo offer this depth in the platform.

Granted, this power and control will require a more complex platform and learning curve, but you can start out easy with a ready-made theme and later work your way into custom development as desired.

If you don't have web development skills and don't want to tinker with theme or other code development, choose a solution such as [Readme.io](pubapis_docs_as_code_tool_options.html#readme) or [Netlify CMS](pubapis_docs_as_code_tool_options.html#netlifycms) (though, with Netlify CMS, you'd still have to select a theme). Readme provides a ready-made design for your API doc site, removing the need for both designing a theme and figuring out hosting/deployment. That can save you a lot of time and effort.

Realize that when implementing a solution, you might spend **a quarter of your time** over a period of months customizing your theme and working on other doc tooling needs. If you don't want to devote that much time to your tooling, Readme is a good option. However, I personally want more control and flexibility over the information design and theme. I like to experiment, and I want the power to code whatever feature I want, such as an embedded navigation map, a special TOC for series items, or whatever. I think many tech writers and developers want similar flexibility and control. What is important to you? Is flexibility and control so important that you're willing to sink weeks/months of time into the solution?

Additionally, if you have a large number of contributing authors who will need direct access to the system, consider whether you have the budget for a hosted solution like Readme that charges per author.

If you want to use a static site generator, which should you choose &mdash; Jekyll, Hugo, Sphinx, or some other? Sphinx has the most documentation-oriented features, such as search, PDF, cross-reference linking, and semantic markup. If those features are important, consider Sphinx.

However, choosing Jekyll or Hugo rather than Sphinx does have rationale because their communities extend beyond documentation groups. Sphinx was designed as a documentation platform, so its audience tends to be more niche. Documentation tools almost never have the community size that more general web development tools have. So the tradeoff with Jekyll or Hugo is that although they lack some better documentation features (cross-references, search, PDF, semantic markup), they might have more community and momentum in the long-term. Still, this may leave you in a tight spot if you have to figure out a solution for search, PDF, and translation. There are not easy workarounds for these features that you can simply hack in during a lazy afternoon.

Markup is also a consideration. If you've narrowed the choice down to Sphinx with reStructuredText or Jekyll/Hugo with Markdown, then one question to ask is whether engineers at your company will write in reStructuredText (assuming engineers will write at all). If they'll write in reStructuredText, great, Sphinx is probably superior for documentation projects due to the [semantic advantages of reStructuredText](pubapis_markdown.html#rst_and_asciidoc). But if engineers insist on Markdown, then maybe Jekyll or Hugo will be a better choice. You can use also Markdown with Sphinx, but when you do, some other Sphinx features become limited.

If deciding between Jekyll and Hugo, consider your project size. Do you have thousands of pages, all in the same project? Will each author be building the project locally? If so, how much does speed (how fast the project compiles the output) matter? If speed is an important consideration, Hugo will probably be better. But if you prefer a community and a platform that integrates tightly with GitHub, then Jekyll might be better.

## Select a hosting and deployment platform

After you've narrowed down which static site generator you want to use, next think about hosting and deployment options (which offer continuous delivery). If you've decided on Sphinx, consider using [Read the Docs](pubapis_docs_as_code_tool_options.html#readthedocs). If you've decided on Jekyll, then explore [GitHub Pages](#pubapis_docs_as_code_tool_options.html#github_pages),  [CloudCannon](pubapis_docs_as_code_tool_options.html#cloudcannon), [Netlify](pubapis_docs_as_code_tool_options.html#netlify), or [Aerobatic](pubapis_docs_as_code_tool_options.html#aerobatic). If you've decided on Hugo, then explore [Netlify](pubapis_docs_as_code_tool_options.html#netlify) or [Aerobatic](pubapis_docs_as_code_tool_options.html#aerobatic).

By using one of these platforms, you offload a tremendous burden in maintaining a server and deploying your site. Usually, within a company, engineering groups manage and control the server infrastructure. Setting up and maintaining your own server for documentation using internal resources only can be a huge expense and headache. It can take months (if not years) to get engineering to give you space on a server, and even if they do, it likely will not provide half of the features you need (like continuous delivery and a CLI). That's why I recommend these third-party hosting and deployment options if at all possible.

Maintaining your own server is not the business you want to be in, and these third-party platforms enable you to be much more efficient. Removing the hassle of publishing through continuous delivery from the server will simplify your life unimaginable ways.

If you don't have budget for a third-party host and deployment option, nor do you have internal engineering resources, consider deploying to an [AWS S3 bucket](https://aws.amazon.com/s3/). Jekyll has a plugin called [S3_website](https://github.com/laurilehmijoki/s3_website) that easily deploys to S3. It's not a continuous delivery model, but neither does it involve uploading your entire site output every time you want to publish. The S3_website plugin looks at what changed in your output and synchronizes those changes with the files on S3. Even so, after you get used to continuous delivery publishing by simply committing to your repo, it's hard to consider publishing any other way.

If your company prefers to build its own publishing pipeline, before you go down this road, find out what features the internal solution will provide. Explore some of the benefits of these third-party host and deployment options and examine whether the internal solution will have enough parity and long-term support. If you have strong engineering backing, then great, you're probably in a good spot. But if engineers will barely give you the time of day, consider a third-party solution. See [Case study: Switching tools to docs-as-code](pubapis_switching_to_docs_as_code.html) for my experience going down this route.

{% include random_ad.html %}

### Parsing the OpenAPI specification

At this point in the course, I haven't yet explored the [OpenAPI specification](pubapis_swagger_intro.html), but it could be an important factor in your consideration of tools. How will you display all the [endpoint reference documentation](docendpoints.html)? Rather than [creating your own template](pubapis_design_patterns.html#structure_and_templates) or manually defining these reference sections, I recommend using a tool that can read and parse the OpenAPI for your reference documentation. Not many standalone doc tools easily [incorporate and display the OpenAPI specification](pubapis_combine_swagger_and_guide.html) (yet), so perhaps the best alternative might be to [embed Swagger UI](pubapis_swagger.html) (assuming more deep integration isn't possible) into your doc platform.

I've seen some deeper integrations of Swagger UI into existing websites, and some day I hope to do this with a Jekyll theme, but I haven't yet. You could also create a theme using the Swagger UI theme itself. Static site generators can convert any HTML website into a theme where content is powered by the static site generator &mdash; see my tutorial [Convert an HTML site to Jekyll](https://jekyllrb.com/tutorials/convert-site-to-jekyll/).

## Tools versus content

Although this section has focused heavily on tools, I want to emphasize that content always trumps tooling. The content should be your primary focus, not the tools you use to publish the content. After you get the tooling infrastructure in place, it should mostly take a back seat to the daily tasks of content development.

{: .tip}
For a great article on the importance of content over tools, see [Good API Documentation Is Not About Choosing the Right Tool](https://blog.algolia.com/api-documentation-choosing-right-tool/) from the Algolia blog. The author explains that "a quality README.md stored on GitHub can be far more efficient than over-engineered documentation that is well displayed but has issues with content."

In some ways, tools are the basketball player's shoes. They matter, for sure. But Michael Jordan wasn't a great basketball player because he wore Nikes, nor was Kobe Bryant great due to his Adidas shoes. You can probably write incredible documentation despite your tooling and platform. Don't let tooling derail your focus on what really matters in your role: the content.

I've changed my doc platforms numerous times, and rarely does anyone seem to care or notice. As long as it looks decent, most project managers and users will focus on the content much more than the design or platform. In some ways, the design should be invisible and unobtrusive, not foregrounding the focus on the content. The user shouldn't be distracted by the tooling.

Also, users and reviewers won't even notice all the effort behind the tools. Even when you've managed to single source content, loop through a custom collection to generate out a special display, incorporate language switchers to jump from platform to platform, etc., the feedback you'll get is "There's a typo here."

On the other hand, the tools you choose do make a huge difference in your productivity, capabilities, and general happiness as a technical writer. Choosing the wrong tool can set back your ability to deliver documentation that your users need.
