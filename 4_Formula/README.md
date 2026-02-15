# ⚗️ 4_Formula - Guides and Best Practices

## 🎯 Purpose
Provides guidelines and step-by-step formulas built by GPT for common post-production tasks.

## 🔢 Formula 1: Parse Chapter Markers from Text

### 📋 Steps
1. 📖 **Read Input**: Load source_chapter_markers.txt
2. ✂️ **Split Lines**: Separate by newline character
3. ⏰ **Parse Timestamp**: Extract HH:MM:SS or MM:SS format
4. 📝 **Extract Title**: Get text after timestamp
5. ✅ **Validate**: Ensure timestamps are sequential
6. 🎨 **Format**: Convert to YouTube/video platform format

### 💻 Code Template
```javascript
function parseChapterMarkers(text) {
    const lines = text.split('\n').filter(line => line.trim());
    const chapters = lines.map(line => {
        const match = line.match(/(\d{1,2}:)?\d{1,2}:\d{2}\s+(.+)/);
        if (match) {
            return {
                timestamp: match[0].split(/\s+/)[0],
                title: match[2]
            };
        }
    }).filter(Boolean);
    return chapters;
}
```

## 🔄 Formula 2: Convert SRT to VTT

### 📋 Steps
1. 📖 **Read SRT**: Parse subtitle file
2. 🔍 **Extract Components**: Number, timestamp, text
3. 🔄 **Convert Format**: SRT → VTT syntax
4. ➕ **Add Header**: "WEBVTT" at top
5. ✅ **Validate**: Check timing overlaps
6. 💾 **Export**: Save as .vtt file

## 📝 Formula 3: Generate Video Description

### 📋 Steps
1. 🔗 **Combine Sources**: Transcript + chapters + links
2. ⏰ **Format Timestamps**: Convert to clickable format (0:00)
3. 📑 **Add Sections**: Intro, chapters, resources, social links
4. 📏 **Optimize Length**: Stay under platform limits (5000 chars)
5. 🔍 **Add Keywords**: For SEO
6. 👀 **Preview**: Show final output

## 🎬 Formula 4: Process EDL (Edit Decision List)

### 📋 Steps
1. 📊 **Parse EDL**: Extract events, timecodes, transitions
2. 🔗 **Map Assets**: Link to source files
3. ⏱️ **Calculate Duration**: For each clip
4. 🔍 **Identify Gaps**: Find missing footage
5. 📄 **Generate Report**: Summary for editor
6. 💾 **Export**: Compatible format for NLE

## ⚙️ Formula 5: Validate Asset Configuration

### 📋 Steps
1. 📁 **Load Config**: Read assets_config.json
2. ✅ **Check Paths**: Verify all file paths exist
3. 📋 **Validate Schema**: Ensure required fields present
4. 🔍 **Test Formats**: Confirm file types supported
5. 🚨 **Report Issues**: List missing or invalid assets
6. 🔧 **Suggest Fixes**: Auto-correct common issues
