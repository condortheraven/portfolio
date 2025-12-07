# Quasarcat Portfolio - Deployment Instructions

This is your professional cybersecurity portfolio built with MkDocs and the Material theme.

## Prerequisites

- A GitHub account
- Git installed on your computer (or use GitHub Desktop)
- Your domain: quasarcat.co.za

## Step 1: Set Up GitHub Repository

1. **Create a GitHub account** if you don't have one: https://github.com/join

2. **Create a new repository**:
   - Go to https://github.com/new
   - Repository name: `portfolio` (or any name you like)
   - Make it **Public**
   - Don't initialize with README (we already have files)
   - Click "Create repository"

## Step 2: Upload Your Site Files

### Option A: Using Git (Command Line)

```bash
# Navigate to the portfolio directory
cd /path/to/quasarcat-portfolio

# Initialize git
git init

# Add all files
git add .

# Commit
git commit -m "Initial portfolio commit"

# Add your GitHub repository as remote (replace USERNAME with your GitHub username)
git remote add origin https://github.com/USERNAME/portfolio.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Option B: Using GitHub Web Interface (Easier)

1. On your computer, zip the entire `quasarcat-portfolio` folder
2. Go to your new GitHub repository
3. Click "uploading an existing file"
4. Drag and drop all the files from the folder
5. Commit the changes

## Step 3: Enable GitHub Pages

1. In your GitHub repository, go to **Settings** → **Pages**
2. Under "Build and deployment":
   - Source: Select "**GitHub Actions**"
3. GitHub will automatically detect MkDocs and set up deployment

## Step 4: Create GitHub Actions Workflow

Create a file `.github/workflows/deploy.yml` in your repository:

```yaml
name: Deploy MkDocs
on:
  push:
    branches:
      - main
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: actions/setup-python@v4
        with:
          python-version: 3.x
      - run: pip install mkdocs-material
      - run: mkdocs gh-deploy --force
```

This will automatically build and deploy your site whenever you push changes.

## Step 5: Configure Your Custom Domain

### On GitHub:

1. In your repository, go to **Settings** → **Pages**
2. Under "Custom domain", enter: `quasarcat.co.za`
3. Click **Save**
4. Wait for DNS check (may take a few minutes)
5. Once verified, enable "**Enforce HTTPS**"

### On Your Domain Registrar:

You need to add DNS records for `quasarcat.co.za`. Log in to wherever you registered the domain and add these records:

**A Records** (point to GitHub Pages):
```
@  A  185.199.108.153
@  A  185.199.109.153
@  A  185.199.110.153
@  A  185.199.111.153
```

**CNAME Record** (optional, for www):
```
www  CNAME  USERNAME.github.io
```

**Note**: DNS changes can take 24-48 hours to propagate, but usually work within an hour.

## Step 6: Add CNAME File

Create a file called `CNAME` (no extension) in the `docs` folder with just this content:
```
quasarcat.co.za
```

This tells GitHub Pages to use your custom domain.

## Step 7: Test Your Site

After DNS propagates:
- Visit https://quasarcat.co.za
- Your portfolio should be live!

## Making Updates

### Option 1: Edit on GitHub (Easy)
1. Go to your repository on GitHub
2. Click on any file in the `docs` folder
3. Click the pencil icon to edit
4. Make changes
5. Commit - site will automatically rebuild

### Option 2: Edit Locally (Recommended)
```bash
# Make changes to files in docs/ folder
# Preview locally:
mkdocs serve
# Opens at http://127.0.0.1:8000

# Commit and push changes
git add .
git commit -m "Updated content"
git push
```

## Site Structure

```
quasarcat-portfolio/
├── mkdocs.yml              # Main configuration
├── docs/
│   ├── index.md            # Homepage
│   ├── about.md            # About page
│   ├── contact.md          # Contact info
│   ├── research/           # Research projects
│   ├── experience/         # Work experience
│   └── academic/           # Academic work
└── .github/
    └── workflows/
        └── deploy.yml      # Auto-deployment
```

## Customization Tips

### Update Your Information

1. **Edit contact.md**: Add your actual GitHub, LinkedIn, email
2. **Edit about.md**: Personalize your bio
3. **Add profile photo**: Save as `docs/assets/profile.jpg` and reference in pages

### Change Colors

In `mkdocs.yml`, modify the theme colors:
```yaml
theme:
  palette:
    primary: blue  # Change this
    accent: amber  # And this
```

Available colors: red, pink, purple, deep purple, indigo, blue, light blue, cyan, teal, green, light green, lime, yellow, amber, orange, deep orange

### Add New Pages

1. Create a new `.md` file in appropriate `docs/` subfolder
2. Add it to navigation in `mkdocs.yml` under `nav:`

## Troubleshooting

### Site not deploying?
- Check the "Actions" tab in GitHub for build errors
- Make sure `mkdocs.yml` is in the repository root
- Verify all file paths are correct

### Custom domain not working?
- Wait 24-48 hours for DNS to propagate
- Check DNS records are correct at your registrar
- Verify CNAME file exists in `docs/` folder

### Build errors?
- Check Python packages are installed: `pip install mkdocs-material`
- Validate `mkdocs.yml` syntax
- Check for broken links in navigation

## Need Help?

- MkDocs documentation: https://www.mkdocs.org
- Material theme docs: https://squidfunk.github.io/mkdocs-material/
- GitHub Pages docs: https://docs.github.com/en/pages

---

**Your portfolio is ready to go live! 🚀**

Once deployed, this will showcase:
- Your CVE discovery
- Professional experience at Rootshell and Reversec
- Academic research and dissertation
- Technical skills and projects
- All presented in a clean, professional format

Good luck with your job search and graduation!
