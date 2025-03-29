# Personal Website

This is my personal website built with Jekyll and hosted on GitHub Pages.

## Local Development

To run the site locally:

```bash
bundle install
bundle exec jekyll serve
```

Then visit `http://localhost:4000` in your browser.

## Deployment

This site is automatically deployed to GitHub Pages when changes are pushed to the main branch.

## Custom Domain

This site uses the custom domain `jakovic.com`. The DNS settings should be configured with:

```
Type: A
Name: @
Value: 
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

And:
```
Type: CNAME
Name: www
Value: jakovic.github.io
``` 