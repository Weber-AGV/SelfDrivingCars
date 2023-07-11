# RUN Docs Template

## Deploy Site
- Github Settings
- Pages
- Enable Github Actions
- Go to .github/workflows
- Enable jekyll.yml
- Change in jekyll.yml ```run: bundle exec jekyll build --baseurl "/RunDocsTemplate"``` to new repo url
- Change in layouts/defaults.liquid ```<link rel="stylesheet" href="/RunDocsTemplate/assets/css/tab.css">```

Site should deploy

