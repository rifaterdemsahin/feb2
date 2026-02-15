# 🔣 5_Symbols - Core Source Code

## 🎯 Purpose
Contains the main application files and source code.

## 📁 File Organization

### 🌐 HTML Files
- `postproduction_helper.html` - Main application interface
- `index.html` - Project landing page

### 📜 JavaScript Modules (To Be Created)
- `fileParser.js` - Parse various input formats
- `dataTransformer.js` - Transform data between formats
- `uiController.js` - Handle UI interactions
- `validator.js` - Validate data integrity
- `exporter.js` - Export to various formats

### 🎨 CSS Stylesheets (To Be Created)
- `main.css` - Core styles
- `prism-theme.css` - Syntax highlighting theme
- `responsive.css` - Mobile/tablet layouts

## 📏 Code Conventions

### 🏷️ Naming
- **Variables**: camelCase (`inputFile`, `chapterData`)
- **Functions**: camelCase, verb-first (`parseChapters`, `validateTimestamp`)
- **Classes**: PascalCase (`FileParser`, `DataExporter`)
- **Constants**: UPPER_SNAKE_CASE (`MAX_FILE_SIZE`, `DEFAULT_FORMAT`)

### 🏗️ File Structure
```javascript
// 1. Imports
import { helper } from './utils.js';

// 2. Constants
const CONFIG = {...};

// 3. State
let appState = {};

// 4. Functions
function init() {...}

// 5. Event Listeners
document.addEventListener('DOMContentLoaded', init);

// 6. Exports
export { parseData, transformData };
```

### Comments
- Use JSDoc for functions
- Inline comments for complex logic
- TODO/FIXME tags for known issues

## Integration with PrismJS

### Setup
```html
<link href="https://cdn.jsdelivr.net/npm/prismjs@1.29.0/themes/prism.css" rel="stylesheet" />
<script src="https://cdn.jsdelivr.net/npm/prismjs@1.29.0/prism.js"></script>
<script src="https://cdn.jsdelivr.net/npm/prismjs@1.29.0/components/prism-yaml.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/prismjs@1.29.0/components/prism-json.min.js"></script>
```

### Usage
```javascript
const highlighted = Prism.highlight(code, Prism.languages.yaml, 'yaml');
element.innerHTML = highlighted;
```
