# Contributing to AI Truth Seeker

First off, thank you for considering contributing to AI Truth Seeker! It's people like you that make this case study a valuable resource for the community.

## Code of Conduct

By participating in this project, you are expected to uphold our Code of Conduct:

- **Be respectful**: Treat everyone with respect and kindness
- **Be constructive**: Provide helpful feedback and suggestions
- **Be collaborative**: Work together to improve the project
- **Be inclusive**: Welcome newcomers and diverse perspectives

## How Can I Contribute?

### 🐛 Reporting Bugs

Before creating bug reports, please check existing issues to avoid duplicates. When you create a bug report, include as many details as possible:

**Bug Report Template:**
```markdown
**Describe the bug**
A clear description of what the bug is.

**To Reproduce**
Steps to reproduce the behavior:
1. Go to '...'
2. Click on '...'
3. Scroll down to '...'
4. See error

**Expected behavior**
What you expected to happen.

**Screenshots**
If applicable, add screenshots.

**Environment:**
 - OS: [e.g. iOS, Windows, Linux]
 - Browser: [e.g. Chrome, Safari, Firefox]
 - Version: [e.g. 22]

**Additional context**
Any other context about the problem.
```

### 💡 Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, include:

- **Clear title** describing the enhancement
- **Detailed description** of the proposed functionality
- **Use cases** explaining why this would be useful
- **Possible implementation** if you have ideas

**Enhancement Template:**
```markdown
**Is your feature request related to a problem?**
A clear description of the problem.

**Describe the solution you'd like**
What you want to happen.

**Describe alternatives you've considered**
Other solutions you've thought about.

**Additional context**
Screenshots, mockups, or examples.
```

### 📝 Content Contributions

We welcome improvements to the case study content:

- **Expand sections**: Add more detail to existing topics
- **Add examples**: Real-world implementation stories
- **Update data**: Keep cloud provider information current
- **Improve clarity**: Better explanations and analogies
- **Fix typos**: Grammar and spelling corrections

### 🎨 Design Contributions

- **UI/UX improvements**: Better layouts, interactions, animations
- **Accessibility**: ARIA labels, keyboard navigation, screen reader support
- **Responsive design**: Better mobile/tablet experiences
- **Performance**: Optimize loading times, reduce bundle size
- **Dark mode**: Add dark theme support

### 💻 Code Contributions

#### Getting Started

1. **Fork the repository**
   ```bash
   git clone https://github.com/yourusername/ai-truth-seeker.git
   cd ai-truth-seeker
   ```

2. **Create a branch**
   ```bash
   git checkout -b feature/your-feature-name
   # or
   git checkout -b fix/your-bug-fix
   ```

3. **Make your changes**
   - Follow the code style guidelines below
   - Test your changes thoroughly
   - Update documentation if needed

4. **Commit your changes**
   ```bash
   git add .
   git commit -m "Brief description of your changes"
   ```

5. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

6. **Open a Pull Request**
   - Go to the original repository
   - Click "New Pull Request"
   - Select your fork and branch
   - Fill out the PR template

#### Code Style Guidelines

**HTML**
- Use semantic HTML5 elements
- Maintain proper indentation (2 spaces)
- Include meaningful `id` and `class` names
- Add `alt` text to all images
- Use ARIA labels for accessibility

**CSS (Tailwind)**
- Use Tailwind utility classes
- Follow mobile-first responsive design
- Keep utility classes organized (layout → spacing → colors → typography)
- Extract common patterns into reusable components
- Add comments for complex utility combinations

**JavaScript**
- Use vanilla JavaScript (no dependencies)
- Write clear, self-documenting code
- Add comments for complex logic
- Use meaningful variable and function names
- Follow ES6+ standards (const/let, arrow functions, template literals)
- Handle errors gracefully

**Example:**
```javascript
// Good
function filterProviders() {
  const input = document.getElementById('providerSearch').value.toLowerCase();
  const cards = document.querySelectorAll('.provider-card');
  
  cards.forEach(card => {
    const keywords = card.getAttribute('data-keywords').toLowerCase();
    card.style.display = keywords.includes(input) ? 'block' : 'none';
  });
}

// Avoid
function fP() {
  var i = document.getElementById('providerSearch').value.toLowerCase();
  var c = document.querySelectorAll('.provider-card');
  for(var x=0;x<c.length;x++){
    var k=c[x].getAttribute('data-keywords').toLowerCase();
    if(k.includes(i)){c[x].style.display='block';}else{c[x].style.display='none';}
  }
}
```

#### Pull Request Guidelines

**PR Title Format:**
- `feat: Add new cloud provider comparison feature`
- `fix: Resolve mobile navigation bug`
- `docs: Update installation instructions`
- `style: Improve card hover animations`
- `refactor: Simplify search filtering logic`

**PR Description Template:**
```markdown
## Description
Brief description of what this PR does.

## Type of Change
- [ ] Bug fix (non-breaking change which fixes an issue)
- [ ] New feature (non-breaking change which adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] Documentation update

## Testing
Describe the tests you ran and how to reproduce them.

## Screenshots (if applicable)
Add before/after screenshots for UI changes.

## Checklist
- [ ] My code follows the style guidelines
- [ ] I have performed a self-review
- [ ] I have commented my code where necessary
- [ ] I have updated the documentation
- [ ] My changes generate no new warnings
- [ ] I have tested on multiple browsers
- [ ] I have tested on mobile devices
```

## Project Structure

```
ai-truth-seeker/
├── index.html          # Main HTML file
├── README.md           # Project documentation
├── LICENSE             # MIT License
├── CONTRIBUTING.md     # This file
├── .gitignore          # Git ignore rules
└── assets/             # (Future) Images, icons, etc.
```

## Development Workflow

### Local Testing

1. **Open the HTML file**
   ```bash
   # macOS
   open index.html
   
   # Windows
   start index.html
   
   # Linux
   xdg-open index.html
   ```

2. **Or use a local server**
   ```bash
   # Python 3
   python -m http.server 8000
   
   # Python 2
   python -m SimpleHTTPServer 8000
   
   # Node.js
   npx http-server
   
   # PHP
   php -S localhost:8000
   ```

3. **Access in browser**
   ```
   http://localhost:8000
   ```

### Browser Testing

Test your changes in:
- ✅ Chrome (latest)
- ✅ Firefox (latest)
- ✅ Safari (latest)
- ✅ Edge (latest)
- ✅ Mobile Safari (iOS)
- ✅ Chrome Mobile (Android)

### Performance Testing

- Use Lighthouse in Chrome DevTools
- Target scores: Performance 90+, Accessibility 100, Best Practices 100, SEO 100
- Check mobile performance separately

## Areas Needing Help

### High Priority
- 🔴 **Accessibility audit**: Improve screen reader support
- 🔴 **Mobile optimization**: Better touch interactions
- 🔴 **Content updates**: Keep cloud provider info current

### Medium Priority
- 🟡 **New features**: Interactive diagrams, ROI calculator
- 🟡 **Internationalization**: Multi-language support
- 🟡 **Analytics**: Add privacy-friendly usage tracking

### Nice to Have
- 🟢 **Dark mode**: Full dark theme support
- 🟢 **Print styles**: Optimized print layouts
- 🟢 **Offline support**: Progressive Web App features

## Community

### Getting Help

- **Documentation**: Read the [README](README.md)
- **Issues**: Search existing issues or create a new one
- **Discussions**: Use GitHub Discussions for questions

### Recognition

Contributors will be:
- Added to the README contributors section
- Mentioned in release notes
- Given credit in commit messages

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

**Thank you for contributing to AI Truth Seeker!** 🎉

Your time and expertise help make this resource better for everyone in the enterprise AI community.
