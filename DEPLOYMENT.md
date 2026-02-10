# Deployment Guide

This guide will walk you through deploying the AI Truth Seeker case study website to GitHub Pages.

## Prerequisites

- GitHub account
- Git installed on your computer
- Basic familiarity with command line

## Quick Deployment to GitHub Pages

### Method 1: GitHub Web Interface (Easiest)

1. **Create a new repository**
   - Go to https://github.com/new
   - Repository name: `ai-truth-seeker` (or your preferred name)
   - Description: "AI Truth Seeker - Enterprise AI Case Study"
   - Set to **Public**
   - ✅ Initialize with README (you can replace it later)
   - Click "Create repository"

2. **Upload files**
   - Click "Add file" → "Upload files"
   - Drag and drop all files from this project
   - Commit message: "Initial commit"
   - Click "Commit changes"

3. **Enable GitHub Pages**
   - Go to repository Settings
   - Scroll to "Pages" in the left sidebar
   - Under "Source", select:
     - Branch: `main`
     - Folder: `/ (root)`
   - Click "Save"

4. **Access your site**
   - Wait 1-2 minutes for deployment
   - Visit: `https://yourusername.github.io/ai-truth-seeker`
   - If using custom name: `https://yourusername.github.io/repository-name`

### Method 2: Command Line (Recommended)

```bash
# 1. Navigate to the project directory
cd path/to/ai-truth-seeker

# 2. Initialize git repository
git init

# 3. Add all files
git add .

# 4. Commit files
git commit -m "Initial commit: AI Truth Seeker case study"

# 5. Create repository on GitHub (via web interface or gh CLI)
# Then connect it:
git remote add origin https://github.com/yourusername/ai-truth-seeker.git

# 6. Push to GitHub
git branch -M main
git push -u origin main

# 7. Enable GitHub Pages via Settings → Pages (see Method 1, step 3)
```

### Method 3: GitHub CLI (For Advanced Users)

```bash
# 1. Install GitHub CLI if not already installed
# macOS: brew install gh
# Windows: winget install GitHub.cli
# Linux: See https://github.com/cli/cli#installation

# 2. Login to GitHub
gh auth login

# 3. Create repository and push
gh repo create ai-truth-seeker --public --source=. --remote=origin --push

# 4. Enable GitHub Pages
gh repo edit --enable-pages --pages-branch main

# 5. View your site
gh browse
```

## Custom Domain Setup (Optional)

### Using a Custom Domain

1. **Purchase a domain** (from Namecheap, GoDaddy, Google Domains, etc.)

2. **Configure DNS records**
   
   Add these DNS records at your domain provider:
   
   ```
   Type: A
   Name: @
   Value: 185.199.108.153
   
   Type: A
   Name: @
   Value: 185.199.109.153
   
   Type: A
   Name: @
   Value: 185.199.110.153
   
   Type: A
   Name: @
   Value: 185.199.111.153
   
   Type: CNAME
   Name: www
   Value: yourusername.github.io
   ```

3. **Configure GitHub Pages**
   - Go to repository Settings → Pages
   - Under "Custom domain", enter: `yourdomain.com`
   - ✅ Enforce HTTPS (wait for SSL certificate to be issued)

4. **Add CNAME file**
   
   Create a file named `CNAME` in your repository root:
   ```
   yourdomain.com
   ```

5. **Wait for DNS propagation** (can take 24-48 hours)

### Subdomain Setup

For a subdomain like `case-study.yourdomain.com`:

```
Type: CNAME
Name: case-study
Value: yourusername.github.io
```

Then update GitHub Pages settings with `case-study.yourdomain.com`

## Deployment Checklist

Before deploying, ensure:

- [ ] All links work correctly
- [ ] Images load properly
- [ ] Search functionality works
- [ ] Responsive design tested
- [ ] No console errors
- [ ] Lighthouse scores are good
- [ ] Contact information is updated
- [ ] Social media links are correct

## Post-Deployment

### Verify Deployment

1. **Check the live site**
   - Visit your GitHub Pages URL
   - Test all navigation links
   - Test interactive features
   - Check mobile responsiveness

2. **Test from different devices**
   - Desktop (various browsers)
   - Mobile (iOS and Android)
   - Tablet

3. **Check SEO**
   - Run Lighthouse audit
   - Verify meta tags
   - Test social media previews

### Monitor and Update

```bash
# Make changes to your local files
# Then commit and push:

git add .
git commit -m "Description of changes"
git push origin main

# Changes will be live in 1-2 minutes
```

## Troubleshooting

### Common Issues

**Issue: 404 Page Not Found**
```
Solution:
- Ensure index.html is in the root directory
- Check GitHub Pages is enabled
- Verify branch is set to 'main'
- Wait a few minutes for deployment
```

**Issue: CSS/JS Not Loading**
```
Solution:
- Check file paths are relative, not absolute
- Ensure Tailwind CDN link is correct
- Check browser console for errors
- Clear browser cache
```

**Issue: Custom Domain Not Working**
```
Solution:
- Verify DNS records are correct
- Wait 24-48 hours for DNS propagation
- Check CNAME file exists
- Ensure HTTPS is enabled
```

**Issue: Changes Not Showing**
```
Solution:
- Clear browser cache (Ctrl+Shift+R / Cmd+Shift+R)
- Check commit was pushed (git status)
- Wait 1-2 minutes for GitHub Pages rebuild
- Check GitHub Actions tab for build status
```

## Performance Optimization

### Current Setup
- ✅ Tailwind CSS via CDN (lightweight, cached)
- ✅ Font Awesome via CDN (cached)
- ✅ Google Fonts optimized
- ✅ No JavaScript dependencies
- ✅ Minimal inline scripts

### Future Optimizations
- [ ] Add service worker for offline support
- [ ] Implement lazy loading for images
- [ ] Add resource hints (preconnect, prefetch)
- [ ] Minify HTML/CSS/JS for production
- [ ] Implement critical CSS inlining

## Security

### Current Security Features
- ✅ HTTPS enforced (via GitHub Pages)
- ✅ No external form submissions
- ✅ No sensitive data in client-side code
- ✅ No third-party tracking scripts

### Security Best Practices
- Keep dependencies updated
- Don't commit sensitive information
- Use HTTPS for all external resources
- Implement Content Security Policy (optional)

## Analytics (Optional)

### Privacy-Friendly Options

**1. Simple Analytics**
```html
<!-- Add to <head> -->
<script async defer src="https://scripts.simpleanalyticscdn.com/latest.js"></script>
```

**2. Plausible Analytics**
```html
<!-- Add to <head> -->
<script defer data-domain="yourdomain.com" src="https://plausible.io/js/script.js"></script>
```

**3. GitHub's Built-in Insights**
- Go to repository Insights tab
- View traffic, popular pages, and referrals

## Maintenance

### Regular Updates

**Monthly:**
- [ ] Update cloud provider information
- [ ] Check all external links
- [ ] Review analytics (if enabled)
- [ ] Test on latest browsers

**Quarterly:**
- [ ] Update case study content
- [ ] Add new cloud services
- [ ] Review and update documentation
- [ ] Security audit

**Annually:**
- [ ] Major content refresh
- [ ] Design updates
- [ ] Performance optimization
- [ ] SEO audit

## Backup

### Backup Strategy

```bash
# 1. Clone your repository to multiple locations
git clone https://github.com/yourusername/ai-truth-seeker.git backup/

# 2. Export repository settings (manual)
# Settings → Options → Export

# 3. Archive releases
# Create releases at major milestones:
git tag -a v1.0 -m "Initial release"
git push origin v1.0
```

## Rollback Procedure

If something breaks:

```bash
# View commit history
git log --oneline

# Revert to previous commit
git revert HEAD

# Or reset to specific commit
git reset --hard <commit-hash>
git push origin main --force
```

## Support

### Getting Help

- **GitHub Issues**: Report bugs or request features
- **GitHub Discussions**: Ask questions
- **Documentation**: Check README.md and CONTRIBUTING.md
- **Community**: Connect with other users

### Useful Resources

- [GitHub Pages Docs](https://docs.github.com/en/pages)
- [Tailwind CSS Docs](https://tailwindcss.com/docs)
- [Web.dev](https://web.dev/) - Performance best practices
- [MDN Web Docs](https://developer.mozilla.org/) - Web standards

---

## Next Steps

After successful deployment:

1. ✅ Share your site on social media
2. ✅ Add to your portfolio
3. ✅ Submit to relevant directories
4. ✅ Gather feedback from users
5. ✅ Iterate and improve

**Congratulations on deploying AI Truth Seeker!** 🎉

Your case study is now live and accessible to the world.
