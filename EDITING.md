# Editing Your Website: A Complete Guide

This guide shows you how to edit your website content and publish updates using GitHub Desktop.

## The Workflow

1. **Edit** files locally on your computer (in your favorite text editor)
2. **Preview** changes locally in your browser (optional but recommended)
3. **Commit** changes using GitHub Desktop
4. **Push** to GitHub → site updates automatically

---

## What You Can Edit

### Content Files (Easy - Just Edit Text)

All your main content is in markdown files (`.md`) in the website folder:

- **index.md** - Homepage
- **research.md** - Research page
- **people.md** - People/team page
- **publications.md** - Publications list
- **resources.md** - Resources page
- **contact.md** - Contact information

### Style Files (Advanced)

To change colors, fonts, or layout:

- **_sass/_colors.scss** - All color definitions
- **_sass/_variables.scss** - Fonts, spacing, sizes
- **_sass/main.scss** - Layout and styling

---

## Step-by-Step: Editing Content

### Example: Adding a New Publication

1. **Open the file** in your text editor:
   - TextEdit, VS Code, Sublime Text, or any editor
   - File: `publications.md`

2. **Find the right year section** (or create a new one):

   ```markdown
   ## 2026
   ```

3. **Add your publication** using this format:

   ```markdown
   <div class="publication">
   <div class="pub-title">Your Paper Title Here</div>
   <div class="pub-authors">Author1, A., Author2, B., & Author3, C.</div>
   <div class="pub-venue">Journal Name, Volume(Issue), Pages. <a href="URL">pdf</a></div>
   </div>
   ```

4. **Save the file** (Cmd+S)

5. Continue to "Publishing Changes" section below

### Example: Updating the People Page

1. **Open** `people.md`

2. **To add a new team member**, copy this template:

   ```markdown
   <div class="person-card">
     <a href="https://scholar.google.com/LINK">Name Here</a>
     <div class="title">Position/Title</div>
   </div>
   ```

3. **To add a photo** (optional):
   - Put the photo in `assets/images/people/`
   - Add before the name in the card:

   ```markdown
   <img src="/assets/images/people/name.jpg" alt="Name">
   ```

4. **Save the file**

### Example: Editing the Homepage

1. **Open** `index.md`
2. **Edit the text** between the `---` markers (that's your content)
3. **Save**

Simple as that!

---

## Previewing Changes Locally (Before Publishing)

**Highly recommended** - see exactly how changes will look before publishing.

### One-Time Setup

If you haven't already:

```bash
cd "/Users/gauthii/Dropbox/_WORKING ON THESE/NewWebSite"
bundle install
```

### Start the Preview Server

```bash
cd "/Users/gauthii/Dropbox/_WORKING ON THESE/NewWebSite"
bundle exec jekyll serve
```

You'll see:
```
Server address: http://127.0.0.1:4000
Server running... press ctrl-c to stop.
```

### View Your Site

1. Open browser to: `http://localhost:4000`
2. Your site appears exactly as it will online
3. Make changes to files
4. Refresh browser - changes appear automatically!
5. When done, press **Ctrl+C** in Terminal to stop the server

---

## Publishing Changes with GitHub Desktop

Once you're happy with your edits:

### Step 1: Open GitHub Desktop

1. Launch GitHub Desktop
2. Your repository should appear in the left sidebar
3. If not, click "Add" → "Add Existing Repository"

### Step 2: Review Your Changes

GitHub Desktop shows you:
- Which files you changed (left panel)
- Exactly what changed (right panel with green/red highlighting)

### Step 3: Write a Commit Message

In the bottom left:
- **Summary** (required): Brief description
  - Examples: "Added 2026 publications", "Updated team photos", "Fixed typo on homepage"
- **Description** (optional): More details if needed

### Step 4: Commit

1. Click **"Commit to main"** button
2. Your changes are saved locally

### Step 5: Push to GitHub

1. Click **"Push origin"** button (top right)
2. GitHub Desktop uploads your changes to GitHub
3. GitHub Pages automatically rebuilds your site
4. **Your site updates in ~30 seconds!**

### Step 6: Verify

1. Wait about 30-60 seconds
2. Visit your site URL
3. Refresh the page (Cmd+Shift+R for hard refresh)
4. Your changes should be live!

---

## Tips & Best Practices

### Making Multiple Changes

Feel free to:
- Edit multiple files
- Make several changes at once
- Preview everything locally first
- Commit and push them all together

### Commit Message Tips

Good commit messages help you track changes:

✅ Good:
- "Added 5 new publications from 2025"
- "Updated Melina's bio and photo"
- "Fixed broken link in resources"

❌ Too vague:
- "Updates"
- "Changes"
- "Fixed stuff"

### If You Make a Mistake

Don't panic! Git tracks everything.

**To undo changes before committing:**
- In GitHub Desktop, right-click the file → "Discard changes"

**To undo a commit you already pushed:**
- Contact someone familiar with Git, or
- Just make a new commit fixing the mistake

### Markdown Formatting Quick Reference

```markdown
# Heading 1
## Heading 2
### Heading 3

**bold text**
*italic text*

[Link text](http://url.com)

- Bullet point
- Another bullet

1. Numbered list
2. Another item
```

---

## Common Editing Tasks

### Add a Lab Photo

1. Put photo in `assets/images/`
2. In your markdown file:
   ```markdown
   ![Description](assets/images/photo.jpg)
   ```

### Change Colors

1. Open `_sass/_colors.scss`
2. Find the color variable (e.g., `$sky-blue`)
3. Change the hex code (e.g., `#7CB9E8` to `#4A90D9`)
4. Save and preview

### Update Navigation

1. Open `_includes/header.html`
2. Find the `<nav>` section
3. Add a new link:
   ```html
   <li><a href="/newpage.html">New Page</a></li>
   ```
4. Create `newpage.md` with content

### Add a News Section

1. Create `news.md`:
   ```markdown
   ---
   layout: default
   title: News
   ---

   # Lab News

   ## January 2026
   - News item here
   - Another update
   ```

2. Add to navigation in `_includes/header.html`

---

## File Organization

```
NewWebSite/
├── index.md              ← Homepage content
├── research.md           ← Research page
├── people.md             ← People page
├── publications.md       ← Publications
├── resources.md          ← Resources
├── contact.md            ← Contact info
├── _config.yml           ← Site settings (rarely edit)
├── _layouts/             ← Page templates (rarely edit)
├── _includes/            ← Header/footer (rarely edit)
├── _sass/                ← Styles and colors
│   ├── _colors.scss      ← Color palette
│   ├── _variables.scss   ← Fonts, spacing
│   └── main.scss         ← Main styles
├── assets/
│   ├── css/              ← Compiled styles (don't edit)
│   └── images/           ← Your images
│       ├── painting-texture.jpg
│       └── people/       ← Team photos
└── _site/                ← Generated site (don't edit, auto-created)
```

**Don't edit:**
- Anything in `_site/` (auto-generated)
- `assets/css/main.css` (auto-generated from SCSS)

---

## Troubleshooting

### Preview server won't start

```bash
# Make sure you're in the right directory
cd "/Users/gauthii/Dropbox/_WORKING ON THESE/NewWebSite"

# Reinstall dependencies
bundle install

# Try again
bundle exec jekyll serve
```

### Changes don't appear locally

- Save your files (Cmd+S)
- Refresh browser (Cmd+R)
- Check Terminal for error messages

### Changes don't appear on live site

- Wait 30-60 seconds after pushing
- Check GitHub repository - do you see your changes?
- Hard refresh browser (Cmd+Shift+R)
- Check GitHub Actions tab for build errors

### GitHub Desktop doesn't see changes

- Make sure you saved the file
- Check that you're in the right repository
- Try closing and reopening GitHub Desktop

---

## Advanced: Adding New Pages

1. **Create new markdown file**: `teaching.md`

2. **Add front matter and content**:
   ```markdown
   ---
   layout: default
   title: Teaching
   ---

   # Teaching

   Your content here...
   ```

3. **Add to navigation** in `_includes/header.html`:
   ```html
   <li><a href="/teaching.html">Teaching</a></li>
   ```

4. **Commit and push**

---

## Quick Reference Card

**To make changes:**
1. Edit `.md` files in text editor
2. Save files
3. (Optional) Preview: `bundle exec jekyll serve`
4. Open GitHub Desktop
5. Review changes
6. Write commit message
7. Click "Commit to main"
8. Click "Push origin"
9. Wait ~30 seconds
10. Refresh your website!

**Most commonly edited files:**
- `publications.md` - Add papers
- `people.md` - Update team
- `index.md` - Homepage updates
- `_sass/_colors.scss` - Color changes

---

## Getting Help

- **Markdown Guide**: https://www.markdownguide.org/
- **Jekyll Documentation**: https://jekyllrb.com/docs/
- **GitHub Desktop Help**: https://docs.github.com/en/desktop
- **Color Picker**: https://htmlcolorcodes.com/

Remember: You can't break anything permanently. Git tracks all changes, and you can always go back!
