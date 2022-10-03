Automatic Build of Hugo website using hugo-resume theme with Github Actions Pipeline and Deploy to Github pages..

To create your own free website at "{yourgituser}.github.io":
1. Fork this repo and rename it while being forked
2. Rename the repository to {yourgituser}.github.io
3. IMPORTANT: While at your new repo, Go to Settings > Go to Pages > At "Build and deployment - Source" select "Github Actions" from the dropdown!
4. IMPORTANT: While at your new repo, Go to Settings > Go to Action > Click Enable Actions
5. Do a manual change in one of the files to force a commit and start the pipeline. Just change something in config.toml
6. Go to {yourgituser}.github.io <br><br>
<B>(optional for netlify)</B><br><br>
6. Register and create a new site at Netlify. Edit --baseURL in netlify.toml to match your newly created site in netlify.<br>
7. To refresh pages in GithubPages we need to recompile our theme inside themes/ folder each time we run the pipeline<br> https://github.com/cryptozealot/cryptozealot.github.io/blob/master/.github/workflows/pages.yml#L48
Netlify needs that created in the repo prior to the deploy(maybe there is a fix for this - TODO)
So before we run Netlify Deployment, we clone our repo locally and cd into it, then we run:

```git submodule add https://github.com/cryptozealot/cryptozealot.github.io.git /themes/hugo-resume/```

Changes made to original repo:
1. Added .github/workflows/ "Github Actions" workflow to build and deploy on Github Pages.
2. Added netlify.toml - for Netlify deployment and admin panel
3. Created theme file, moved folders from exampleSite, cleanup

Resources:
<br>https://02dev.com/post/learn/61d8edb69c67d2983d96fae8
<br>https://www.netlifycms.org/docs/github-backend/
<br>https://www.netlifycms.org/docs/git-gateway-backend/
<br>https://preview-auth-doc--netlify-cms-www.netlify.app/docs/authentication-backends/#github-backend
<br>https://docs.netlify.com/visitor-access/oauth-provider-tokens/#using-an-authentication-provider
<br>https://docs.netlify.com/visitor-access/oauth-provider-tokens/#netlify-ui-settings
<br>https://cloud.gov/pages/documentation/getting-started-with-netlify-cms/
