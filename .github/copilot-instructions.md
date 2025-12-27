# Copilot Instructions for Greg's Golden Hoe

This document provides guidance for GitHub Copilot Coding Agent when working on this repository.

## Project Overview

**Greg's Golden Hoe** is a retro 8-bit arcade browser game featuring Greg the friendly brown recluse spider. The game is a pure HTML5/CSS3/JavaScript application with zero dependencies and no build process.

### Key Characteristics
- **Single-file application**: The entire game is contained in `index.html` (~2000 lines)
- **Zero dependencies**: No external libraries, frameworks, or build tools
- **Pure web technologies**: HTML5, CSS3, and ES6+ JavaScript only
- **Browser-based**: Runs directly in any modern browser without installation

## Project Structure

```
gregs-golden-hoe/
├── index.html                         # Complete game (HTML + CSS + JavaScript)
├── README.md                          # Comprehensive documentation
├── LICENSE                           # Project license
├── .gitignore                        # Git ignore rules
└── .github/
    ├── copilot-instructions.md       # This file
    └── workflows/
        └── static.yml                # GitHub Pages deployment
```

## Architecture

### Game Structure
The game follows a modular, component-based architecture within the single HTML file:

1. **HTML Section** (Lines 1-1001)
   - Semantic HTML structure
   - Game grid container
   - UI overlays (celebration, win screen, item found)
   - Mobile D-pad controls

2. **CSS Section** (Lines 57-913)
   - CSS custom properties (variables) for theming
   - Retro 8-bit aesthetic with pixel art styling
   - Responsive design with mobile breakpoints
   - CSS animations and transitions

3. **JavaScript Section** (Lines 1002-1994)
   - Constants-driven configuration
   - Centralized state management (`GameState` object)
   - Event-driven input handling
   - requestAnimationFrame-based game loop
   - SVG sprite definitions
   - Modular function organization

### Key Constants
Located at the top of JavaScript section (Lines 1019-1077):
```javascript
const GRID_SIZE = 8;                  // 8x8 grid
const GOLDEN_HOE_CHANCE = 0.10;       // 10% per dig
const CELEBRATION_DURATION = 15000;   // 15 seconds
const ITEM_DISPLAY_DURATION = 3000;   // Item overlay time
const ITEM_FLY_DURATION = 800;        // Fly animation time
```

### State Management
- Centralized `GameState` object manages all game data
- Game states: `PLAYING`, `SHOWING_ITEM`, `CELEBRATING`, `WON`
- All state mutations go through dedicated functions

## Development Workflow

### Testing
Since this is a browser-based game with no build process:
- **Manual testing only**: Open `index.html` in a browser
- **Test on multiple browsers**: Chrome, Firefox, Safari, Edge
- **Test on mobile**: Use browser dev tools or actual mobile devices
- **No automated tests exist**: Focus on manual validation

### How to Test Changes
```bash
# Open directly in browser
open index.html  # macOS
start index.html  # Windows
xdg-open index.html  # Linux

# Or use Python's HTTP server for local testing
python3 -m http.server 8000
# Then visit http://localhost:8000
```

### Deployment
- **Platform**: GitHub Pages (automatic deployment)
- **Workflow**: `.github/workflows/static.yml`
- **Special handling**: Google Analytics ID injection during deployment
  - Placeholder `__GA_MEASUREMENT_ID__` is replaced with secret value
  - If secret not set, analytics are disabled (site still works)

## Code Style and Conventions

### General Principles
- **No magic numbers**: Use named constants for all configuration values
- **Descriptive names**: Functions and variables clearly express their purpose
- **Comments for sections**: Major sections have clear comment headers
- **Consistent formatting**: 2-space indentation, ES6+ syntax

### JavaScript Conventions
- **Function documentation**: JSDoc-style comments for complex functions
- **Modular organization**: Functions grouped by purpose (initialization, input, actions, UI)
- **Event-driven**: All user input handled through event listeners
- **Pure functions where possible**: Minimize side effects

### CSS Conventions
- **CSS Variables**: All colors and dimensions use CSS custom properties (`:root`)
- **BEM-like naming**: Descriptive class names (e.g., `.game-container`, `.grid-cell`, `.greg-sprite`)
- **Mobile-first responsive**: Base styles with `@media` queries for larger screens
- **Animations**: Use CSS animations and transitions for smooth effects

### HTML Conventions
- **Semantic markup**: Use appropriate HTML5 elements
- **Accessibility**: Include `aria-*` attributes where appropriate
- **Clean structure**: Logical grouping and indentation

## Working with This Repository

### Making Changes

#### When modifying game mechanics:
1. Update constants if applicable (Lines 1019-1077)
2. Test thoroughly in multiple browsers
3. Ensure mobile compatibility (touch controls work)
4. Verify game states transition correctly

#### When modifying styles:
1. Use existing CSS variables in `:root` (Lines 61-84)
2. Maintain retro 8-bit aesthetic
3. Test responsive breakpoints (650px and 400px)
4. Ensure mobile D-pad remains functional

#### When adding features:
1. Follow existing code organization patterns
2. Add new constants at the top of relevant sections
3. Update JSDoc comments for complex logic
4. Consider mobile/touch device implications

#### When fixing bugs:
1. Identify the section (HTML/CSS/JavaScript)
2. Make minimal, surgical changes
3. Test the specific functionality thoroughly
4. Verify no regression in other features

### What NOT to Change
- **File structure**: Keep everything in `index.html`
- **Zero dependencies**: Do not add external libraries
- **No build process**: Do not introduce bundlers or preprocessors
- **Analytics placeholder**: Keep `__GA_MEASUREMENT_ID__` placeholder format

## Common Tasks

### Adding New Items
1. Add item type to `ITEM_TYPES` enum (Lines 1035-1048)
2. Add item to `PREPLACED_ITEMS` array (Lines 1051-1062)
3. Add item name to `ITEM_NAMES` object (Lines 1065-1077)
4. Create SVG sprite in `SPRITES` object (Lines 1087-1218)

### Adjusting Game Difficulty
- Modify `GOLDEN_HOE_CHANCE` (Line 1020) - default is 0.10 (10%)
- Change `GRID_SIZE` (Line 1019) - default is 8x8

### Updating Celebration Duration
- Modify `CELEBRATION_DURATION` (Line 1021) - default is 15000ms (15 seconds)

### Changing Visual Theme
- Update CSS variables in `:root` (Lines 61-84)
- Maintain limited color palette for retro aesthetic

## Browser Compatibility

**Target browsers**: Modern browsers with ES6+ support
- ✅ Chrome (recommended)
- ✅ Firefox
- ✅ Safari
- ✅ Edge
- ✅ Opera

**Required features**:
- ES6+ JavaScript (arrow functions, const/let, template literals)
- CSS Grid and Flexbox
- CSS Custom Properties
- requestAnimationFrame
- Touch events (for mobile)

## Git Workflow

### Branches
- `main`: Production branch (auto-deploys to GitHub Pages)
- Feature branches: Use descriptive names

### Commits
- Make focused, atomic commits
- Write clear commit messages
- Test before committing

### Pull Requests
- Provide clear description of changes
- Include testing steps
- Consider mobile implications

## Special Notes for AI Agents

### What This Project Is
- A complete, self-contained game in a single HTML file
- No external dependencies or build process required
- Designed for simplicity and accessibility

### What Makes Changes Successful
- **Preserve simplicity**: Don't add complexity
- **Test manually**: Always verify in an actual browser
- **Think mobile**: Consider touch screen users
- **Maintain aesthetic**: Keep the retro 8-bit style consistent

### Common Pitfalls to Avoid
- ❌ Don't split the file into multiple files
- ❌ Don't add npm packages or dependencies
- ❌ Don't introduce build tools
- ❌ Don't break mobile touch controls
- ❌ Don't modify the GA placeholder format

### Best Practices for This Repo
- ✅ Make minimal, focused changes
- ✅ Use existing patterns and conventions
- ✅ Test in browser after any change
- ✅ Keep mobile experience in mind
- ✅ Maintain retro aesthetic and simplicity
- ✅ Update constants rather than hardcoding values
- ✅ Follow the existing code organization

## Getting Help

- **README.md**: Comprehensive game documentation
- **Code comments**: Inline documentation throughout
- **Constants section**: Configuration and tunable values
- **GitHub Issues**: For questions and discussions
