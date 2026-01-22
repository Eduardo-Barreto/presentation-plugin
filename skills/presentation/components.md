# Presentation Components

Reusable HTML/CSS patterns for slides.

## Cards

### Basic Card
```html
<div class="card">
  <h3 class="card-title">Title</h3>
  <p class="card-text">Description text here.</p>
</div>
```

```css
.card {
  background: var(--bg-secondary);
  border: 1px solid var(--border-default);
  border-radius: var(--radius-lg);
  padding: 32px;
  transition: all 0.3s ease;
}

.card:hover {
  transform: translateY(-2px);
  border-color: var(--border-hover);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
}
```

### Card with Icon
```html
<div class="card">
  <div class="icon-box">
    <svg>...</svg>
  </div>
  <h3 class="card-title">Title</h3>
  <p class="card-text">Description</p>
</div>
```

```css
.icon-box {
  width: 48px;
  height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: var(--bg-tertiary);
  border: 1px solid var(--border-default);
  border-radius: var(--radius-sm);
  margin-bottom: 16px;
}
```

## Grids

```css
.grid-2 { grid-template-columns: repeat(2, 1fr); gap: 16px; }
.grid-3 { grid-template-columns: repeat(3, 1fr); gap: 16px; }
.grid-4 { grid-template-columns: repeat(4, 1fr); gap: 12px; }

@media (max-width: 768px) {
  .grid-2, .grid-3, .grid-4 {
    grid-template-columns: 1fr;
  }
}
```

## Flow Diagram

```html
<div class="flow">
  <div class="flow-node">Step 1</div>
  <span class="flow-arrow">→</span>
  <div class="flow-node">Step 2</div>
  <span class="flow-arrow">→</span>
  <div class="flow-node">Step 3</div>
</div>
```

```css
.flow {
  display: flex;
  align-items: center;
  gap: 16px;
  flex-wrap: wrap;
  justify-content: center;
}

.flow-node {
  background: var(--bg-secondary);
  border: 1px solid var(--border-default);
  border-radius: var(--radius-md);
  padding: 16px 24px;
  font-family: var(--font-mono);
  font-size: 14px;
  transition: all 0.2s ease;
}

.flow-node:hover {
  border-color: var(--accent-blue);
}

.flow-arrow {
  color: var(--text-tertiary);
  font-size: 20px;
}
```

## Progress Bars

```html
<div class="progress-item">
  <div class="progress-label">
    <span>Label</span>
    <span>75%</span>
  </div>
  <div class="progress-track">
    <div class="progress-fill" data-width="75"></div>
  </div>
</div>
```

```css
.progress-track {
  height: 4px;
  background: var(--bg-tertiary);
  border-radius: 2px;
  overflow: hidden;
}

.progress-fill {
  height: 100%;
  background: var(--accent-blue);
  border-radius: 2px;
  width: 0;
  transition: width 1s ease;
}

.progress-fill--green { background: var(--accent-green); }
.progress-fill--amber { background: var(--accent-amber); }
```

JavaScript trigger:
```javascript
const bar = document.querySelector('.progress-fill');
bar.style.width = bar.dataset.width + '%';
```

## Tables

```html
<table>
  <thead>
    <tr>
      <th>Column 1</th>
      <th>Column 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Data 1</td>
      <td>Data 2</td>
    </tr>
  </tbody>
</table>
```

```css
table {
  width: 100%;
  border-collapse: collapse;
}

th {
  text-align: left;
  font-family: var(--font-mono);
  font-size: 11px;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: var(--text-tertiary);
  padding: 12px 16px;
  border-bottom: 1px solid var(--border-default);
}

td {
  padding: 16px;
  font-size: 14px;
  border-bottom: 1px solid var(--border-default);
  color: var(--text-secondary);
}

tr:last-child td { border-bottom: none; }
td:first-child { color: var(--text-primary); font-weight: 500; }
```

## Badges

```html
<div class="badge">
  <span class="badge-dot"></span>
  <span>Status text</span>
</div>
```

```css
.badge {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  padding: 6px 12px;
  border: 1px solid var(--border-default);
  border-radius: 100px;
  font-size: 12px;
  font-weight: 500;
}

.badge-dot {
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: var(--accent-green);
  animation: pulse 2s infinite;
}
```

## Terminal

```html
<div class="terminal">
  <div class="terminal-header">
    <div class="terminal-dot terminal-dot--red"></div>
    <div class="terminal-dot terminal-dot--yellow"></div>
    <div class="terminal-dot terminal-dot--green"></div>
  </div>
  <div class="terminal-body">
    <div><span class="terminal-prompt">$</span> <span class="terminal-command">command here</span></div>
    <div class="terminal-output">Output here</div>
  </div>
</div>
```

```css
.terminal {
  background: var(--bg-secondary);
  border: 1px solid var(--border-default);
  border-radius: var(--radius-lg);
  overflow: hidden;
}

.terminal-header {
  display: flex;
  gap: 8px;
  padding: 12px 16px;
  background: var(--bg-tertiary);
  border-bottom: 1px solid var(--border-default);
}

.terminal-dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
}

.terminal-dot--red { background: #ef4444; }
.terminal-dot--yellow { background: #f59e0b; }
.terminal-dot--green { background: #22c55e; }

.terminal-body {
  padding: 20px;
  font-family: var(--font-mono);
  font-size: 13px;
  line-height: 1.8;
}

.terminal-prompt { color: var(--accent-green); }
.terminal-command { color: var(--text-primary); }
.terminal-output { color: var(--text-secondary); }
```

## Code Block

```html
<div class="code-block">
  <span class="code-comment">// Comment</span>
  <span class="code-keyword">const</span> x = <span class="code-string">"value"</span>;
</div>
```

```css
.code-block {
  background: var(--bg-secondary);
  border: 1px solid var(--border-default);
  border-radius: var(--radius-md);
  padding: 24px;
  font-family: var(--font-mono);
  font-size: 14px;
  overflow-x: auto;
}

.code-comment { color: var(--text-tertiary); }
.code-keyword { color: var(--accent-blue); }
.code-string { color: var(--accent-green); }
.code-function { color: var(--accent-amber); }
```

## Comparison Cards

```html
<div class="comparison">
  <div class="comparison-card comparison-card--before">
    <div class="comparison-label">Before</div>
    <ul class="comparison-list">
      <li>Item 1</li>
      <li>Item 2</li>
    </ul>
  </div>
  <div class="comparison-card comparison-card--after">
    <div class="comparison-label">After</div>
    <ul class="comparison-list">
      <li>Item 1</li>
      <li>Item 2</li>
    </ul>
  </div>
</div>
```

```css
.comparison {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 24px;
}

.comparison-card {
  padding: 32px;
  border-radius: var(--radius-lg);
}

.comparison-card--before {
  background: rgba(239, 68, 68, 0.05);
  border: 1px solid rgba(239, 68, 68, 0.2);
}

.comparison-card--after {
  background: rgba(34, 197, 94, 0.05);
  border: 1px solid rgba(34, 197, 94, 0.2);
}

.comparison-card--before .comparison-label { color: #ef4444; }
.comparison-card--after .comparison-label { color: var(--accent-green); }
```

## Stats

```html
<div class="stats-grid">
  <div class="stat">
    <div class="stat-value">99%</div>
    <div class="stat-label">Accuracy</div>
  </div>
</div>
```

```css
.stats-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 32px;
}

.stat { text-align: center; }

.stat-value {
  font-family: var(--font-mono);
  font-size: clamp(48px, 6vw, 72px);
  font-weight: 600;
  letter-spacing: -0.03em;
}

.stat-label {
  font-size: 14px;
  color: var(--text-tertiary);
  margin-top: 8px;
}
```

## Workflow Steps

```html
<div class="workflow">
  <div class="workflow-step">
    <div class="step-number">01</div>
    <div class="step-content">
      <h4>Step Title</h4>
      <p>Step description.</p>
    </div>
  </div>
</div>
```

```css
.workflow {
  display: flex;
  flex-direction: column;
  gap: 2px;
}

.workflow-step {
  display: grid;
  grid-template-columns: 48px 1fr;
  gap: 24px;
  padding: 24px;
  background: var(--bg-secondary);
}

.workflow-step:first-child {
  border-radius: var(--radius-lg) var(--radius-lg) 0 0;
}

.workflow-step:last-child {
  border-radius: 0 0 var(--radius-lg) var(--radius-lg);
}

.step-number {
  width: 48px;
  height: 48px;
  border: 1px solid var(--border-default);
  border-radius: var(--radius-sm);
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: var(--font-mono);
}
```

## Buttons

```html
<button class="btn btn-primary">Primary</button>
<button class="btn btn-secondary">Secondary</button>
```

```css
.btn {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 14px 28px;
  border-radius: var(--radius-sm);
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.2s ease;
}

.btn-primary {
  background: var(--text-primary);
  color: var(--bg-primary);
  border: none;
}

.btn-primary:hover { background: #e0e0e0; }

.btn-secondary {
  background: transparent;
  color: var(--text-primary);
  border: 1px solid var(--border-default);
}

.btn-secondary:hover { border-color: var(--border-hover); }
```

## Keyboard Shortcut

```html
<span class="kbd">Space</span>
```

```css
.kbd {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-width: 28px;
  height: 28px;
  padding: 0 8px;
  background: var(--bg-tertiary);
  border: 1px solid var(--border-default);
  border-radius: 6px;
  font-family: var(--font-mono);
  font-size: 12px;
  color: var(--text-secondary);
}
```

## Quote

```html
<blockquote class="quote">
  Quote text here.
  <span class="quote-author">— Author Name</span>
</blockquote>
```

```css
.quote {
  font-size: clamp(24px, 3vw, 36px);
  font-weight: 500;
  letter-spacing: -0.01em;
  line-height: 1.4;
  padding-left: 32px;
  border-left: 2px solid var(--accent-blue);
}

.quote-author {
  display: block;
  font-size: 14px;
  color: var(--text-tertiary);
  margin-top: 16px;
  font-weight: 400;
}
```
