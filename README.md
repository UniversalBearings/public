# Professional SSL for Internal Tools

## The Problem

Many hospitals and research institutes rely on internal web tools for critical research and operations. Without proper SSL certificates, users are forced to bypass browser security warnings—telling researchers to type "thisisunsafe" or click through certificate errors. This undermines security training, looks unprofessional, and creates confusion for users who should be trusting these tools.

## The Solution

This repository provides a simple, free solution using **Let's Encrypt wildcard certificates** and **GitHub Pages** to serve valid SSL certificates for internal tools. No more security warnings, no more embarrassment—just professional, properly secured internal services.

### How It Works

1. **Public DNS** points to GitHub Pages (serving a 404 page for external visitors)
2. **Internal DNS** points to your actual internal resources
3. **Let's Encrypt wildcard certificate** covers `*.yourdomain.com` for all your internal tools
4. Users get valid SSL certificates with no warnings

This approach is particularly valuable for organizations with many internal tools that aren't accessible from the public internet.

## Setup

You'll need DNS control to add TXT records during certificate setup. Here's a quick example:

```bash
sudo certbot certonly --manual --preferred-challenges=dns --email $YOUR_EMAIL_HERE -d $YOUR_URL_HERE -d *.$YOUR_URL_HERE
```

For detailed instructions, see this [Let's Encrypt wildcard certificate tutorial](https://www.digitalocean.com/community/tutorials/how-to-create-let-s-encrypt-wildcard-certificates-with-certbot).

For GitHub Pages custom domain configuration, see the [official documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).

## Why This Matters

- **Professional appearance**: No more security warnings that confuse users
- **Security compliance**: Proper SSL certificates align with security best practices
- **User trust**: Researchers and staff can trust that internal tools are properly secured
- **Zero cost**: Let's Encrypt certificates are free and auto-renewable
