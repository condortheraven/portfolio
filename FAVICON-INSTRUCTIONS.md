# Adding a Custom Favicon

The site is configured to use a custom favicon, but you need to add the actual image files.

## What You Need

1. **Favicon file**: A `.ico` file (16x16 or 32x32 pixels)
2. **Optional logo**: A `.png` file for the site logo

## How to Add

### Step 1: Create Your Favicon

**Option A - Use a generator:**
- Go to https://favicon.io/favicon-generator/
- Create your favicon
- Download the generated files

**Option B - Convert an image:**
- Have a square image (PNG/JPG)
- Go to https://favicon.io/favicon-converter/
- Upload and convert

### Step 2: Add to Your Repository

1. Create `docs/assets/` folder if it doesn't exist
2. Upload your `favicon.ico` to `docs/assets/favicon.ico`
3. Optionally upload a logo as `docs/assets/logo.png`

### Step 3: Verify

The `mkdocs.yml` is already configured:
```yaml
theme:
  favicon: assets/favicon.ico
  logo: assets/logo.png
```

Once you upload the files, they'll automatically be used!

## Quick Temporary Fix

If you want to skip this for now:

1. Remove these lines from `mkdocs.yml`:
```yaml
favicon: assets/favicon.ico
logo: assets/logo.png
```

The site will use the default Material theme icon instead.

## Recommended Favicon Ideas

For a cybersecurity portfolio, consider:
- Shield icon
- Lock symbol
- Terminal/command prompt icon
- Binary code pattern
- Your initials (CE)
- Abstract geometric design
