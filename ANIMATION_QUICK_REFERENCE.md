# PGDOST Animation & Transition Quick Reference

## Animation Classes (Use in HTML)

### Entrance Animations
```html
<!-- Fade and slide up simultaneously -->
<div class="animate-fade-up">Content</div>

<!-- Fade in only -->
<div class="animate-fade-in">Content</div>

<!-- Scale in with spring easing -->
<div class="animate-scale-in">Content</div>

<!-- Slide from left -->
<div class="animate-slide-left">Content</div>

<!-- Slide from right -->
<div class="animate-slide-right">Content</div>

<!-- Slide from top -->
<div class="animate-slide-down">Content</div>

<!-- Slide from bottom -->
<div class="animate-slide-up">Content</div>

<!-- Bouncy entrance -->
<div class="animate-bounce-in">Content</div>

<!-- Scale up without slide -->
<div class="animate-scale-up">Content</div>

<!-- Floating animation (infinite) -->
<div class="animate-float">Content</div>

<!-- Pulsing glow (infinite) -->
<div class="animate-pulse-glow">Content</div>

<!-- Shimmer effect (infinite) -->
<div class="animate-shimmer">Content</div>

<!-- Spinning loader -->
<div class="animate-spin">Content</div>
```

---

## Transition Classes (Smooth state changes)

```html
<!-- Standard transition (250ms) -->
<button class="transition-smooth">Hover me</button>

<!-- Fast transitions for hover effects (150ms) -->
<button class="transition-fast">Quick feedback</button>

<!-- Slow transitions for major changes (400ms) -->
<div class="transition-slow">Modal</div>

<!-- Spring easing (bouncy feel) -->
<button class="transition-spring">Bouncy</button>
```

---

## Staggered Animations (Multiple items)

```html
<!-- Auto-staggered list items with 60ms delays -->
<div class="animate-stagger">
  <div>First item - 0ms delay</div>      <!-- animates at 0ms -->
  <div>Second item - 60ms delay</div>    <!-- animates at 60ms -->
  <div>Third item - 120ms delay</div>    <!-- animates at 120ms -->
  <div>Fourth item - 180ms delay</div>   <!-- animates at 180ms -->
  <div>Fifth item - 240ms delay</div>    <!-- animates at 240ms -->
  <div>Sixth item - 300ms delay</div>    <!-- animates at 300ms -->
  <div>Seventh+ items - 360ms delay</div><!-- animates at 360ms+ -->
</div>
```

---

## Loading States

### Loading Spinner
```html
<!-- Spinning loader animation -->
<div class="loading-spinner"></div>

<!-- Usage: Show during API calls -->
<button id="submit-btn" type="submit">
  <span id="btn-text">Submit</span>
</button>

<script>
  // Show spinner on submit
  document.getElementById('submit-btn').innerHTML = 
    '<span class="loading-spinner"></span> Loading…';
</script>
```

### Loading Dots
```html
<!-- Blinking dot animation -->
<div style="display: flex; gap: 4px;">
  <div class="loading-dot"></div>
  <div class="loading-dot"></div>
  <div class="loading-dot"></div>
</div>
```

### Skeleton Screen
```html
<!-- Shimmer skeleton for loading states -->
<div class="skeleton" style="height: 20px; margin: 10px 0;"></div>
```

---

## Interactive Element Classes

### Hover Effects
```html
<!-- Lift on hover with shadow -->
<div class="hover-lift">Hover to lift</div>

<!-- Glow effect on hover -->
<div class="hover-glow">Hover for glow</div>

<!-- Scale up on hover -->
<div class="hover-scale">Hover to scale</div>
```

### Focus & Accessibility
```html
<!-- Visible focus ring (accessibility) -->
<button class="focus-ring">Click me</button>

<!-- Form input with focus ring -->
<input class="form-input focus-ring" type="text" />
```

---

## Tab Animations

```html
<div class="tab-content active">
  <!-- Content for active tab animates in -->
  Active tab content
</div>

<div class="tab-content">
  <!-- Other tab content remains hidden -->
  Other content
</div>

<script>
  // When switching tabs, update active class
  tabElement.classList.add('active');
  // Animation plays automatically
</script>
```

---

## Modal Animations

```html
<!-- Modal overlay animates with fade-in -->
<div id="modal" class="modal-overlay">
  <!-- Content scales in with bounce -->
  <div class="modal-content">
    <h2>Modal Title</h2>
    <p>Content</p>
  </div>
</div>

<script>
  // Show modal
  document.getElementById('modal').classList.add('open');
  // Plays entrance animation automatically
  
  // Hide modal
  document.getElementById('modal').classList.remove('open');
  // Plays exit animation automatically
</script>
```

---

## Toast Notifications

```html
<div id="toast-container"></div>

<script>
  // Create toast that slides in
  const toast = document.createElement('div');
  toast.className = 'toast';
  toast.textContent = 'Success!';
  document.getElementById('toast-container').appendChild(toast);
  
  // Auto-remove after delay
  setTimeout(() => {
    toast.classList.add('exit');
    setTimeout(() => toast.remove(), 400);
  }, 3000);
</script>
```

---

## CSS Variables (Customize timing)

```css
:root {
  /* Animation timing */
  --dur-fast: 150ms;    /* Change for all fast animations */
  --dur-base: 250ms;    /* Default animation speed */
  --dur-slow: 400ms;    /* For modals and slow transitions */
  
  /* Easing functions */
  --ease: cubic-bezier(0.4, 0, 0.2, 1);        /* Smooth */
  --ease-spring: cubic-bezier(0.34, 1.56, 0.64, 1);  /* Bouncy */
}

/* Override for specific element */
.fast-button {
  --dur-base: 100ms;
  transition: all var(--dur-base) var(--ease);
}
```

---

## Common Patterns

### Smooth Button Transition
```html
<button class="btn btn-primary transition-smooth">
  Click me
</button>

<style>
  .btn {
    transition: all var(--dur-base) var(--ease);
  }
  .btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 8px 24px rgba(0,0,0,0.2);
  }
</style>
```

### Form Input Focus Animation
```html
<input class="form-input focus-ring transition-smooth" 
       type="text" 
       placeholder="Type here..."/>

<style>
  .form-input {
    transition: all var(--dur-base) var(--ease);
    border: 1px solid #ccc;
  }
  .form-input:focus {
    border-color: #5A8B4C;
    box-shadow: 0 0 0 3px rgba(90,139,76,0.2);
    transform: scale(1.01);
  }
</style>
```

### Card Hover Animation
```html
<div class="card hover-lift transition-smooth">
  <h3>Card Title</h3>
  <p>Card content</p>
</div>

<style>
  .card {
    background: #fff;
    border-radius: 12px;
    padding: 20px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  }
  .card.hover-lift:hover {
    transform: translateY(-6px);
    box-shadow: 0 12px 32px rgba(0,0,0,0.15);
  }
</style>
```

### List Item Stagger
```html
<ul class="animate-stagger">
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
  <li>Item 4</li>
  <li>Item 5</li>
</ul>

<style>
  .animate-stagger > * {
    animation: slideInUp var(--dur-base) var(--ease) forwards;
    opacity: 0;
  }
  /* Delays are automatically applied by CSS */
</style>
```

---

## Animation Timing Guide

### When to Use Each Duration
```
150ms (--dur-fast)
- Hover effects
- Quick feedback
- Icon rotations
- Brief feedback

250ms (--dur-base)
- Page loads
- Transitions between states
- Button clicks
- Most animations

400ms (--dur-slow)
- Modal open/close
- Large elements
- Page transitions
- Complex animations
```

---

## Accessibility Considerations

### Respect Motion Preferences
```css
/* Automatically handled by our CSS, but here's how: */
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```

### Focus Rings for Keyboard Users
```css
/* Use .focus-ring class for visible focus */
.focus-ring:focus {
  outline: 2px solid transparent;
  outline-offset: 2px;
  box-shadow: 0 0 0 3px rgba(90,139,76,0.2);
}
```

### Color Contrast
- All text: 4.5:1 minimum contrast
- Large text: 3:1 minimum contrast
- Never use color alone to indicate state

---

## Browser Support

### Supported Browsers
- Chrome 90+ (Full support)
- Firefox 88+ (Full support)
- Safari 14+ (Full support)
- Edge 90+ (Full support)
- Mobile browsers (iOS Safari 14+, Chrome Mobile)

### Fallbacks
- CSS `transform` and `opacity` supported universally
- `backdrop-filter` with `-webkit-` prefix included
- CSS variables with fallbacks provided

---

## Performance Tips

### Best Practices
1. **Use transform & opacity only** - Most performant animations
2. **Avoid animating width/height** - Causes layout recalculations
3. **Use will-change sparingly** - Can hurt performance if overused
4. **Test on real devices** - Desktop performance varies from mobile
5. **Reduce animations on mobile** - Consider performance impact

### Debug Performance
```javascript
// Check if animations are smooth
console.log("FPS Check: Should see 60 in most cases");
// Open DevTools > Performance > Record and check for frame drops
```

---

## Common Issues & Solutions

### Animation not playing?
```css
/* Check if element has animation class */
.animate-fade-up { animation: fadeSlideUp 0.6s var(--ease) forwards; }

/* Verify element isn't hidden */
.my-element { display: block; /* not none */ }
```

### Animation too fast/slow?
```css
/* Adjust timing */
.animate-fade-up {
  animation-duration: 800ms; /* was 600ms */
}
```

### Focus ring not visible?
```css
/* Ensure sufficient contrast */
.focus-ring:focus {
  box-shadow: 0 0 0 3px rgba(90,139,76,0.4); /* increased opacity */
}
```

### Stagger animation not working?
```html
<!-- Make sure parent has animate-stagger class -->
<div class="animate-stagger">
  <div>Item 1</div>
  <div>Item 2</div>
  <!-- Each child needs to be direct child -->
</div>
```

---

## Real-World Examples

### Login Form with Animations
```html
<form class="login-form">
  <div class="form-group animate-fade-up">
    <label>Username</label>
    <input class="form-input focus-ring" type="text" />
  </div>
  <div class="form-group animate-fade-up">
    <label>Password</label>
    <input class="form-input focus-ring" type="password" />
  </div>
  <button class="btn btn-primary animate-fade-up">
    Sign In
  </button>
</form>
```

### Dashboard Stats Cards
```html
<div class="ds-stats">
  <div class="ds-stat">
    <div class="stat-icon-box">📊</div>
    <div class="stat-info">
      <div class="stat-val">$12,500</div>
      <div class="stat-lbl">Total Revenue</div>
    </div>
  </div>
  <!-- Cards automatically stagger -->
</div>
```

### Data Table
```html
<table class="ds-table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Status</th>
      <th>Date</th>
    </tr>
  </thead>
  <tbody>
    <tr class="hover-highlight">
      <td>John Doe</td>
      <td><span class="badge-green">Active</span></td>
      <td>2024-05-08</td>
    </tr>
  </tbody>
</table>
```

---

## Need Help?

Refer to the complete documentation in:
- **UI_UX_IMPROVEMENTS.md** - Detailed implementation guide
- **IMPLEMENTATION_SUMMARY.md** - Project completion report
- **CSS files** - Comments explain each animation

---

**Last Updated:** May 8, 2026  
**Version:** 1.0 - Production Ready
