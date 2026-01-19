# Object Perception Lab Website

A clean, modern academic website for Dr. Isabel Gauthier's research group at Vanderbilt University, featuring a whimsical design inspired by Matt Crump's painting "Where the magic bears live."

## Features

- Clean, professional design with playful color palette
- Fully responsive (mobile-friendly)
- Easy to update via markdown files
- Fast static site built with Jekyll
- Hosted for free on GitHub Pages

## Design

The site features a custom color palette extracted from the painting:
- Sky blue (#7CB9E8)
- Warm pink (#FFB3D9)
- Gentle yellow (#FFE66D)
- Soft green (#A8E6A3)
- Lavender (#D4BBFF)

## Local Development

### Prerequisites

You need Ruby and Jekyll installed on your Mac.

1. Install Ruby (if not already installed):
   ```bash
   brew install ruby
   ```

2. Add Ruby to your PATH (add to ~/.zshrc or ~/.bash_profile):
   ```bash
   export PATH="/usr/local/opt/ruby/bin:$PATH"
   ```

3. Install Jekyll and Bundler:
   ```bash
   gem install jekyll bundler
   ```

### Running the Site Locally

1. Navigate to the project directory:
   ```bash
   cd "/Users/gauthii/Dropbox/_WORKING ON THESE/NewWebSite"
   ```

2. Install dependencies:
   ```bash
   bundle install
   ```

3. Serve the site:
   ```bash
   bundle exec jekyll serve
   ```

4. Open your browser to `http://localhost:4000`

The site will automatically rebuild when you make changes to files.

## Updating Content

### Homepage
Edit `index.md`

### Research Page
Edit `research.md`

### People Page
Edit `people.md`

### Publications
Edit `publications.md` - Add new publications to the appropriate year section using the format:

```markdown
<div class="publication">
<div class="pub-title">Your Paper Title</div>
<div class="pub-authors">Author1, Author2, & Author3</div>
<div class="pub-venue">Journal Name, Volume, Pages. <a href="link">pdf</a></div>
</div>
```

### Resources
Edit `resources.md`

### Contact
Edit `contact.md`

### Changing Colors
Edit `_sass/_colors.scss` to adjust the color palette

### Changing Fonts and Spacing
Edit `_sass/_variables.scss`

### Modifying Styles
Edit `_sass/main.scss`

## Deploying to GitHub Pages

### Initial Setup

1. Create a new GitHub repository (e.g., "opl-website")

2. Initialize git in your project (if not already):
   ```bash
   git init
   git add .
   git commit -m "Initial commit: new OPL website"
   ```

3. Add your GitHub repository as remote:
   ```bash
   git remote add origin https://github.com/yourusername/opl-website.git
   git branch -M main
   git push -u origin main
   ```

4. Enable GitHub Pages:
   - Go to your repository on GitHub
   - Click "Settings"
   - Scroll to "Pages" in the left sidebar
   - Under "Source", select "main" branch
   - Click "Save"

5. Your site will be live at `https://yourusername.github.io/opl-website/` in a few minutes

### For Vanderbilt Domain

If you want to keep using `gauthier.psy.vanderbilt.edu`:

**Option 1: Host on Vanderbilt servers**
- Build the site locally: `bundle exec jekyll build`
- Upload the contents of the `_site` folder to your Vanderbilt web directory

**Option 2: Custom domain with GitHub Pages**
- In GitHub repository settings > Pages, add custom domain
- Contact Vanderbilt IT to update DNS settings to point to GitHub Pages
- See [GitHub's custom domain guide](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)

### Updating the Live Site

After making changes locally:

```bash
git add .
git commit -m "Description of changes"
git push
```

GitHub Pages will automatically rebuild and deploy your site.

## File Structure

```
.
├── _config.yml           # Site configuration
├── _layouts/             # Page templates
│   └── default.html
├── _includes/            # Reusable components
│   ├── header.html
│   └── footer.html
├── _sass/                # Stylesheets (SCSS)
│   ├── _colors.scss
│   ├── _variables.scss
│   └── main.scss
├── assets/
│   ├── css/
│   │   └── main.scss
│   └── images/
│       └── painting-texture.jpg
├── index.md              # Homepage
├── research.md           # Research page
├── people.md             # People page
├── publications.md       # Publications page
├── resources.md          # Resources page
├── contact.md            # Contact page
└── README.md             # This file
```

## Customization Tips

### Adding a New Page

1. Create a new markdown file (e.g., `teaching.md`)
2. Add front matter at the top:
   ```markdown
   ---
   layout: default
   title: Teaching
   ---

   # Teaching

   Your content here...
   ```
3. Add a link to the navigation in `_includes/header.html`

### Adding Team Member Photos

1. Add photos to `assets/images/people/`
2. Update `people.md` to include the image:
   ```html
   <img src="/assets/images/people/name.jpg" alt="Name">
   ```

### Changing the Header Background

The header uses a gradient overlay on the painting. To adjust:
- Edit `_sass/main.scss` in the `.site-header` section
- Modify the gradient or opacity values

## Support

For Jekyll documentation: https://jekyllrb.com/docs/
For GitHub Pages help: https://docs.github.com/en/pages

## Credits

- Design & Development: Built with Jekyll
- Header Artwork: "Where the magic bears live" by Matt Crump (https://www.crumplab.com/)
- Color palette inspired by the painting
