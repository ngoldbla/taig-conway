# Conway's Game of Life - Ghost CMS Injectable Version

This is a fully self-contained, optimized version of Conway's Game of Life designed specifically for code injection into Ghost CMS blog posts or pages.

## Features

✨ **Self-contained** - All HTML, CSS, and JavaScript in one file
🎯 **Scoped styles** - Won't interfere with your Ghost theme
📱 **Responsive** - Works great on mobile and desktop
⚡ **Lightweight** - Optimized for fast loading
🔒 **Safe** - Uses IIFE to avoid global namespace pollution
🎨 **Beautiful** - Clean, modern design that fits most themes

## How to Use in Ghost CMS

### Method 1: Code Injection in a Post/Page (Recommended)

1. Open Ghost Admin panel
2. Create or edit a post/page
3. Click the **+** button to add a new card
4. Select **HTML** card
5. Copy the entire contents of `conway-ghost-inject.html`
6. Paste into the HTML card
7. Preview and publish!

### Method 2: Site-wide Code Injection

1. Go to **Settings** → **Code Injection** in Ghost Admin
2. Paste the code into the **Site Footer** section
3. The game will appear on all pages (you may want to wrap it in conditional logic)

### Method 3: Custom Theme Integration

1. Copy the code from `conway-ghost-inject.html`
2. Add it to your theme template where you want it to appear
3. Rebuild and upload your theme

## Customization

You can easily customize the game by editing these values in the script section:

```javascript
const CELL_SIZE = 6;        // Size of each cell in pixels
const GRID_WIDTH = 100;     // Number of cells horizontally
const GRID_HEIGHT = 60;     // Number of cells vertically
const ALIVE_COLOR = '#667eea';  // Color of alive cells
const DEAD_COLOR = '#ffffff';   // Color of dead cells
const GRID_COLOR = '#f3f4f6';   // Color of grid lines
```

### Color Schemes

To match your blog's color scheme, update the gradient colors in the CSS:

**Primary buttons** (Play, Step):
```css
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
```

**Secondary buttons** (Clear, Random):
```css
background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
```

## Performance Tips

- **Grid size**: Reduce `GRID_WIDTH` and `GRID_HEIGHT` for better performance on mobile
- **Cell size**: Increase `CELL_SIZE` for larger, more visible cells
- **Initial density**: Adjust `Math.random() < 0.25` in the `randomize()` function (lower = fewer cells)

## Responsive Behavior

The game automatically adjusts for smaller screens:
- Canvas is scrollable on mobile if needed
- Controls stack vertically on narrow screens
- Touch-friendly button sizes

## Browser Compatibility

Works in all modern browsers:
- ✅ Chrome/Edge (80+)
- ✅ Firefox (75+)
- ✅ Safari (13+)
- ✅ Mobile browsers

## Troubleshooting

**Game doesn't appear**
- Check browser console for errors
- Ensure JavaScript is enabled
- Verify the code was pasted completely

**Conflicts with theme styles**
- All styles are scoped with `conway-` prefix
- All IDs are unique with `conway-` prefix
- The game uses IIFE to avoid global variable conflicts

**Performance issues**
- Reduce grid size (GRID_WIDTH/GRID_HEIGHT)
- Increase CELL_SIZE
- Lower the initial random density

## What is Conway's Game of Life?

Conway's Game of Life is a cellular automaton created by mathematician John Conway in 1970. It's a zero-player game where the evolution is determined by its initial state.

### Rules

1. Any live cell with 2 or 3 neighbors survives
2. Any dead cell with exactly 3 neighbors becomes alive
3. All other cells die or stay dead

Despite these simple rules, the Game of Life can create incredibly complex patterns!

## License

Same as the parent project - see LICENSE file.

## Credits

Created as an optimized version for Ghost CMS code injection.
