# basic-dns-setup

This is based off the DevOps Roadmap Project [Basic DNS Setup](https://roadmap.sh/projects/basic-dns)

Purchase a custom domain and set up basic DNS records.  

This is number 7 of [DevOps Projects](https://roadmap.sh/devops/projects) as per roadmap.sh

## Description From Site 

The goal of this project is to learn and practice the basics of DNS. You are required to purchase a custom domain name and setup the basic DNS records.

## Requirements

You are required to have a custom domain name to complete this project. You can use the domain name you already own or purchase a new domain name from any provider such as Cloudflare, Namecheap, Godaddy etc. Once you have a domain name, you can proceed to the next step.

### Task 1 - Custom Domain for GitHub Pages

If you have not completed the [GitHub pages project](https://roadmap.sh/projects/github-actions-deployment-workflow), go ahead and complete that project first. Once you have a github pages site setup, set up your custom domain name to point to your github pages site.

### Task 2 - Custom Domain for DigitalOcean Droplet

If you have not completed the [Static Site Server project](https://roadmap.sh/projects/static-site-server), go ahead and complete that project first so you have a basic static site to serve. Once you have a digital ocean droplet setup serving a static site, set up your DNS records to point to your droplet.

## Submission Guidelines 

Output for this project is the steps you took to setup the custom domain name for both GitHub Pages and a DigitalOcean Droplet. You can write a simple markdown file in tutorial format, add screenshots and any other relevant information to help you remember the steps.

Once you have completed the project, you should have a basic understanding of how to setup a custom domain name for both GitHub Pages and a DigitalOcean Droplet.

# Instructions 

### Acquire a Custom Domain. 

If you don't already have one, purchase one from a reputable domain registrar such as: 
    - Cloudflare 
    - GoDaddy 
    - Namecheap

### GitHub Pages 

I could type it all out, but let's just [RTFM](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site) shall we ?

### DigitalOcean Droplet 

- Acess Domains DNS Settings
- Add an `A Record ` :
    - `Host` : Enter `@` to represent the root domain
    - `Value` or `Points To` etc: Droplets `Public IP Address` 
    - `TTL` : Set to `3600` seconds, or leave default 

- Add a CNAME Record (for the www subdomain) : 
    - `Host` : Enter `www` 
    - `Value` or `Points To` etc: `yourdomain.com`
    - `TTL` : Set to `3600` seconds, or leave default 

- Configure Server :
    - Ensure web server (Nginx, Apace, etc.) is set to respond to requests for `yourdomain.com` and `www.yourdomain.com``

Note DNS changes can take awhile to propogate. 