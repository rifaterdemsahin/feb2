# 6_Semblance - Error Logs and Solutions

## Purpose
Documents common issues, their causes, and solutions. Includes debugging tips and workarounds for browser compatibility.

## Common Errors

### Error 1: File Reading Failed
**Symptom**: Unable to read uploaded file
**Cause**: File API not supported or incorrect file handle
**Solution**:
```javascript
// Check browser support
if (!window.FileReader) {
    alert('FileReader API not supported');
    return;
}

// Proper file reading
const reader = new FileReader();
reader.onload = (e) => {
    const content = e.target.result;
    processFile(content);
};
reader.onerror = (e) => {
    console.error('File reading error:', e);
};
reader.readAsText(file);
```

### Error 2: Invalid Timestamp Format
**Symptom**: Chapter markers not parsing correctly
**Cause**: Inconsistent timestamp formats (HH:MM:SS vs MM:SS)
**Solution**:
```javascript
function normalizeTimestamp(ts) {
    const parts = ts.split(':');
    if (parts.length === 2) {
        return `00:${ts}`; // Add hours
    }
    return ts;
}
```

### Error 3: YAML Parse Error
**Symptom**: "Unexpected token" when parsing YAML
**Cause**: Indentation errors or special characters
**Solution**:
- Validate YAML structure using js-yaml library
- Check for tabs vs spaces (use spaces only)
- Escape special characters in strings

```javascript
try {
    const data = jsyaml.load(content);
} catch (e) {
    console.error('YAML parse error:', e.message);
    // Show user-friendly error message
}
```

### Error 4: PrismJS Not Highlighting
**Symptom**: Code appears as plain text
**Cause**: Language component not loaded or incorrect class name
**Solution**:
```html
<!-- Load language components -->
<script src="prism-core.js"></script>
<script src="prism-yaml.js"></script>

<!-- Correct markup -->
<pre><code class="language-yaml">
key: value
</code></pre>

<!-- Trigger highlight -->
<script>Prism.highlightAll();</script>
```

### Error 5: Cross-Origin Issues
**Symptom**: Cannot load external resources
**Cause**: CORS policy restrictions
**Solution**:
- Use CDN resources with proper CORS headers
- For local development, run a local server
- Use file:// protocol carefully (limited features)

```powershell
# Run local server
python -m http.server 8000
# or
npx serve
```

## Browser Compatibility

### FileReader API
- ✓ Chrome 6+
- ✓ Firefox 3.6+
- ✓ Safari 6+
- ✓ Edge (all versions)

### ES6 Features
- ✓ Modern browsers (2017+)
- Use Babel for older browser support

## Debugging Tips

### 1. Console Logging
```javascript
console.log('Data:', data);
console.table(chapters); // For arrays
console.dir(object); // For deep inspection
```

### 2. Breakpoints
Set breakpoints in DevTools at critical points:
- File upload handler
- Parse functions
- Data transformation
- Export functions

### 3. Network Tab
- Check if external resources load
- Verify CDN availability
- Monitor file upload size

### 4. Validation Checklist
- [ ] File uploaded successfully
- [ ] Content read without errors
- [ ] Data parsed correctly
- [ ] UI updated with data
- [ ] Export generates valid output

## Workarounds

### Large File Handling
If files > 50MB:
- Read in chunks using FileReader.readAsArrayBuffer()
- Process incrementally
- Show progress indicator

### Browser Cache Issues
Clear cache with:
- Ctrl+Shift+R (hard reload)
- Version query strings (?v=1.0.1)
- Service worker updates
