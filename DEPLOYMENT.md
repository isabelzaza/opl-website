# Deployment Guide: Making Your Site Live

This guide will walk you through publishing your new Object Perception Lab website and pointing your Vanderbilt URL to it.

## Quick Overview

You have two main options:
1. **GitHub Pages** (Recommended) - Free, automatic updates, modern workflow
2. **Traditional Upload** - Manual file upload to Vanderbilt servers

We recommend **GitHub Pages** since you're already comfortable with GitHub.

---

## Option 1: GitHub Pages (Recommended)

### Step 1: Create GitHub Repository

1. Go to [github.com](https://github.com) and sign in
2. Click the "+" in the top right, select "New repository"
3. Name it something like `opl-website` or `gauthier-lab`
4. **Important:** Make it **Public** (required for free GitHub Pages)
5. Do NOT initialize with README (you already have files)
6. Click "Create repository"

### Step 2: Push Your Site to GitHub

**If using GitHub Desktop:**

1. Open GitHub Desktop
2. File → Add Local Repository
3. Browse to `/Users/gauthii/Dropbox/_WORKING ON THESE/NewWebSite`
4. Click "Add Repository"
5. GitHub Desktop will see it's not tracked yet
6. Click "Create a repository"
7. Uncheck "Initialize with README" and "Initialize with .gitignore" (you have these)
8. Click "Create Repository"
9. Click "Publish repository" button
10. Make sure "Keep this code private" is **UNCHECKED**
11. Click "Publish Repository"

**If using command line:**

```bash
cd "/Users/gauthii/Dropbox/_WORKING ON THESE/NewWebSite"

# Initialize git (if not already done)
git init

# Add all files
git add .

# Create first commit
git commit -m "Initial commit: OPL website"

# Add your GitHub repository (replace YOUR-USERNAME and REPO-NAME)
git remote add origin https://github.com/YOUR-USERNAME/REPO-NAME.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click "Settings" (top navigation)
3. Click "Pages" in the left sidebar
4. Under "Source":
   - Select branch: **main**
   - Select folder: **/ (root)**
5. Click "Save"
6. Wait 1-2 minutes
7. Refresh the page - you'll see: "Your site is live at https://username.github.io/repo-name/"

**Your site is now live!** Visit the URL to see it.

### Step 4: Point Your Vanderbilt URL (Optional but Recommended)

To make `gauthier.psy.vanderbilt.edu` point to your new GitHub Pages site:

#### A. Configure GitHub Pages for Custom Domain

1. In your repository on GitHub
2. Go to Settings → Pages
3. Under "Custom domain", enter: `gauthier.psy.vanderbilt.edu`
4. Click "Save"
5. Wait for DNS check (may show error initially - that's ok)

#### B. Create a CNAME File

In your website folder, create a file named `CNAME` (no extension) with this content:

```
gauthier.psy.vanderbilt.edu
```

Then commit and push:

```bash
git add CNAME
git commit -m "Add custom domain"
git push
```

#### C. Contact Vanderbilt IT

Send an email to your department's IT support (or whoever manages your web hosting):

```
Subject: DNS Update Request for gauthier.psy.vanderbilt.edu

Hi,

I'd like to update the DNS settings for gauthier.psy.vanderbilt.edu
to point to my new GitHub Pages site.

Please add the following DNS records:

Type: CNAME
Host: gauthier (or @)
Points to: YOUR-USERNAME.github.io

If you need the GitHub Pages IP addresses instead:
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153

Once this propagates, my site will be live at the Vanderbilt URL.

Thanks!
```

#### D. Enable HTTPS (Recommended)

After DNS propagates (24-48 hours):
1. Go back to Settings → Pages on GitHub
2. Check the box "Enforce HTTPS"
3. Your site will now be secure with https://

---

## Option 2: Traditional File Upload to Vanderbilt Servers

If you prefer to upload files directly to Vanderbilt's web server:

### Step 1: Build the Static Site

```bash
cd "/Users/gauthii/Dropbox/_WORKING ON THESE/NewWebSite"
bundle exec jekyll build
```

This creates a `_site` folder with all HTML/CSS files.

### Step 2: Find Your Current Upload Method

Your current site files are likely accessed via:
- **SFTP** (Secure File Transfer Protocol)
- **WebDAV**
- **Vanderbilt's web file manager**

Contact your department IT to ask:
- "How do I upload files to gauthier.psy.vanderbilt.edu?"
- "What are the SFTP/FTP credentials?"
- "What directory should files go in?"

### Step 3: Upload Files

Common tools:
- **FileZilla** (free SFTP client): https://filezilla-project.org/
- **Cyberduck** (Mac-friendly): https://cyberduck.io/
- **macOS Finder**: Go → Connect to Server

Upload everything inside the `_site` folder to your web directory.

### Step 4: Test

Visit `gauthier.psy.vanderbilt.edu` to see your new site.

### Future Updates

Every time you make changes:
1. Edit your markdown files
2. Run `bundle exec jekyll build`
3. Upload the new `_site` folder contents

---

## Troubleshooting

### GitHub Pages Shows 404

- Wait a few minutes after enabling Pages
- Check that you selected the `main` branch
- Make sure the repository is **Public**

### Custom Domain Not Working

- DNS changes take 24-48 hours to propagate
- Make sure IT created the CNAME record correctly
- Check that the `CNAME` file is in your repository root

### Site Looks Wrong

- Check browser console for errors (View → Developer → JavaScript Console)
- Verify all files were uploaded/pushed
- Clear browser cache (Cmd+Shift+R)

### Need to Preview Changes Before Publishing

See `EDITING.md` for instructions on running the site locally.

---

## Summary Checklist

For GitHub Pages deployment:

- [ ] Create GitHub repository (public)
- [ ] Push website code to GitHub
- [ ] Enable GitHub Pages in repository settings
- [ ] Test site at github.io URL
- [ ] (Optional) Add CNAME file for custom domain
- [ ] (Optional) Contact Vanderbilt IT for DNS update
- [ ] (Optional) Enable HTTPS after DNS propagates

---

## Getting Help

- **GitHub Pages Documentation**: https://docs.github.com/en/pages
- **Jekyll Documentation**: https://jekyllrb.com/docs/
- **Your department IT**: For Vanderbilt DNS/server questions
- **GitHub Support**: For GitHub-specific issues

Your site is built with Jekyll, hosted for free on GitHub Pages, and can be updated by simply pushing to GitHub!
