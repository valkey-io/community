# Valkey Blog Contribution Guidelines
 
This document describes the process for contributing a blog post to [valkey.io](https://valkey.io). The workflow is transparent, lightweight, and follows standard open source practices.
 
---
 
## Before You Start
 
All blog submissions begin with a GitHub issue. Do not draft content before your topic has been acknowledged by the maintainers. This prevents duplicate efforts and ensures alignment with the site roadmap.
 
Open an issue here: [blog_post_template.md](https://github.com/valkey-io/valkey-io.github.io/issues/new?template=blog_post_template.md)
 
---
 
## Blog Types
 
### Community Blogs
 
Tutorials, use cases, event recaps, and integration walkthroughs. [Here](https://docs.google.com/document/d/1yfQ7WA9EN3PVvV9SybLAXpL4ehiUGiGPL9ZivrBAs0U/edit?tab=t.0) is a general template to help you get started.
 
The preferred submission path is a GitHub pull request (see the full workflow below). If you are not familiar with Git or GitHub, you can draft your content in Google Docs or Word and submit it via the [Asana form](https://form.asana.com/?k=9zh9lhK3yWLavaOi6C0hgA&d=9283783873717) instead.
 
---

### Project Blogs
 
Official releases, deep technical milestones, and governance updates. These require a GitHub pull request and follow the full Zola workflow described below.
 
## Step-by-Step: Full Zola Workflow
 
### Step 0 — Environment Setup
 
Fork and clone the website repository before writing anything.
 
```
https://github.com/valkey-io/valkey-io.github.io
```
 
The README contains instructions for running the site locally with Zola. The general workflow is: write in a branch, verify locally, then submit as a pull request.
 
### Step 1 — Open a GitHub Issue
 
Share your topic idea with the maintainers before writing. Include a summary of the topic and a general outline. The maintainers will confirm whether the topic fits the site and does not overlap with existing content.
 
You may skip this step and submit a PR directly, but you risk doing work that does not translate into a publishable post.
 
### Step 2 — Write the Post
 
Write in Markdown. Stick to headings, paragraphs, links, and code blocks unless you have a specific reason to use other features.
 
**Content guidelines:**
 
- Target 500–1,200 words. Posts should be readable in one sitting.
- Cover your topic completely. If the post is growing too long, narrow the scope. Each post should stand alone and not depend on a series.
- Write for a range of skill levels. The best posts make complex topics approachable.
- Do not actively promote or sell a product or service. You may reference services and providers when directly relevant to operating Valkey (for example, lessons learned from running Valkey at scale). Do not frame the post as a comparison of products.
- Write about Valkey. Avoid comparisons with other projects unless directly necessary.
- End with a call to action. Tell readers what to do next: contribute, try sample code, attend an event, or read related content.
- Write in first person (I) or second person (you). Blog posts are attributed to a person, not the project. Avoid speaking on behalf of groups unless you have explicit authority to do so.
### Step 3 — Create an Author Profile
 
Each post requires at least one author. The author must be a person, not a collective or organization name.
 
Each author needs:
 
- A biography of 1–2 paragraphs explaining who you are and your connection to the Valkey community.
- An optional photo stored at `/static/assets/media/authors/`. Aim for a square image around 500x500px, no larger than 1000x1000px.
If you already have an author profile from a previous post, you do not need to create a new one.
 
Create your author file at:
 
```
/content/authors/YOUR-ID.md
```
 
Example author frontmatter:
 
```toml
+++
title= "Jacobim Mugatu"
[extra]
    photo= "/assets/media/authors/jacobim.jpg"
    github= "octocat"
+++
```
 
Follow the frontmatter with your biography in Markdown.
 
### Step 4 — Create the Post File
 
The site uses [Zola](https://www.getzola.org/) and requires TOML frontmatter at the top of every post file.
 
**File path format:**
 
```
/content/blog/yyyy-mm-dd-post-title-with-dashes-instead-of-spaces.md
```
 
The date prefix is for internal organization. The slug (`post-title-with-dashes-instead-of-spaces`) becomes the URL:
 
```
https://valkey.io/blog/post-title-with-dashes-instead-of-spaces/
```
 
**Example frontmatter:**
 
```toml
+++
title= "Using Valkey for Distributed Session Storage"
date= 2024-07-01 01:01:01
description= "A short, compelling summary of your post. Aim for two sentences that hook the reader."
authors= [ "your-id" ]
[extra]
    featured = true
    featured_image = "/assets/media/featured/random-01.webp"
+++
```
 
Available featured images:
 
```
/assets/media/featured/random-01.webp
/assets/media/featured/random-02.webp
/assets/media/featured/random-03.webp
/assets/media/featured/random-04.webp
/assets/media/featured/random-05.webp
/assets/media/featured/random-06.webp
/assets/media/featured/random-07.webp
```
 
The `authors` array must match the IDs of your author files in `/content/authors/`.
 
After combining the frontmatter and your post content into a single file, run `zola serve` to verify the output locally. Zola will display errors for any frontmatter syntax issues.
 
### Step 5 — Submit a Pull Request
 
Before pushing, verify your DCO sign-off:
 
```bash
git log
```
 
Every commit must include `Signed-off-by:` in the message. Use the `-s` flag when committing:
 
```bash
git commit -s -m "Add blog post: your post title"
```
 
Fix sign-off issues before pushing. After your branch is on your fork, open a pull request to the main repository and link it to your original GitHub issue. Describe your changes fully in the PR body.
 
### Step 6 — Review and Publishing
 
The maintainers will review your post and may request changes. Once the post is approved and merged into `main`, the maintainers will schedule and link the post before moving it to production. Publishing triggers a rebuild of [valkey.io](https://valkey.io).
 
---
 
## Checklist
 
Before submitting, confirm the following:
 
- [ ] GitHub issue opened and acknowledged before drafting
- [ ] Post is 500–1,200 words
- [ ] Post covers the topic completely and stands alone
- [ ] No active product promotion or cross-product comparisons
- [ ] Call to action included at the end
- [ ] Author profile created with biography
- [ ] Frontmatter is valid (tested with `zola serve`)
- [ ] File path follows the `yyyy-mm-dd-slug.md` format
- [ ] All commits are DCO signed (`Signed-off-by:` in each commit message)
- [ ] PR is linked to the original GitHub issue
---
 
## Community and Vendor Neutrality
 
All contributions must benefit the community as a whole. The site is not a commercial space. The maintainers reserve the right to decline content that promotes a specific vendor, product, or service over the broader Valkey ecosystem.
 
---
 
## Resources
 
- [Valkey Website Repository](https://github.com/valkey-io/valkey-io.github.io)
- [Submit via Form](https://form.asana.com/?k=9zh9lhK3yWLavaOi6C0hgA&d=9283783873717)
- [Open a Blog Issue](https://github.com/valkey-io/valkey-io.github.io/issues/new?template=blog_post_template.md)
- [Community Code of Conduct](https://valkey.io/code_of_conduct/)
- [Zola Documentation](https://www.getzola.org/documentation/)
