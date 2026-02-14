# Video Post Production Helper - Project Structure

This project implements a 7-phase methodology for video post-production workflows, from unknown problems to validated solutions.

## Methodology Overview

The project follows a structured approach where each phase builds upon the previous:

**1_Real_Unknown** → **2_Environment** → **3_Simulation** → **4_Formula** → **5_Symbols** → **6_Semblance** → **7_Testing_known**

This creates a feedback loop: start with unknown problems, implement solutions, test them, and reach back to validate against the original objectives.

---

## 7-Phase Folder Structure

### 1_Real_Unknown/ - Objectives (OKRs)

**Purpose**: Define project objectives and key results, starting with the unknown problem.

**Contents**:
- Project goals and objectives
- Key results to measure success  
- Unknown challenges to solve
- Problem statements

**For this project**: Streamlining video post-production workflows to reduce manual effort by 80%.

---

### 2_Environment/ - Roadmap and Use Cases

**Purpose**: Project roadmap with development phases and detailed use cases.

**Contents**:
- Development roadmap (4 phases)
- User scenarios and use cases
- Input file examples:
  - `assets_config.json` - Asset configuration
  - `batch_generation_data.yaml` - Batch processing data
  - `icons.json` - Icon definitions
  - `source_broll.md` - B-roll footage notes
  - `source_chapter_markers.txt` - Video chapter markers
  - `source_edl.md` - Edit Decision List
  - `source_graphics.md` - Graphics assets
  - `source_music.md` - Music cues
  - `source_shotlist.md` - Shot list
  - `source_storyboard.md` - Storyboard
  - `source_subtitle.srt` - Subtitle file
  - `source_transcript.md` - Video transcript

**User Personas**: Content creators, video editors, producers

---

### 3_Simulation/ - UI Examples

**Purpose**: User interfaces and technologies, including best practices for UI development.

**Contents**:
- UI component examples
- Technology documentation (HTML5, CSS3, JavaScript)
- PrismJS implementation guide
- Responsive design patterns
- Accessibility guidelines
- Performance optimization tips

**Technologies**: HTML5, CSS3, JavaScript ES6+, PrismJS for syntax highlighting

---

### 4_Formula/ - Guides and Best Practices

**Purpose**: Step-by-step formulas and algorithms built by GPT.

**Contents**:
- Formula 1: Parse Chapter Markers from Text
- Formula 2: Convert SRT to VTT
- Formula 3: Generate Video Description
- Formula 4: Process EDL (Edit Decision List)
- Formula 5: Validate Asset Configuration

Each formula includes:
- Step-by-step instructions
- Code templates
- Validation procedures

---

### 5_Symbols/ - Core Source Code

**Purpose**: Main application files and source code.

**Contents**:
- `postproduction_helper.html` - Main application
- `README.md` - Code documentation
- Code conventions and standards
- PrismJS integration examples
- File structure guidelines

**Application Features**:
- Multi-file upload (drag & drop)
- Syntax highlighting
- Copy to clipboard
- File download
- Real-time parsing and preview

---

### 6_Semblance/ - Error Logs and Solutions

**Purpose**: Common issues, causes, and solutions with debugging tips.

**Contents**:
- Error 1: File Reading Failed
- Error 2: Invalid Timestamp Format
- Error 3: YAML Parse Error  
- Error 4: PrismJS Not Highlighting
- Error 5: Cross-Origin Issues
- Browser compatibility matrix
- Debugging workflow
- Workarounds for common problems

**Browser Support**: Chrome 6+, Firefox 3.6+, Safari 6+, Edge (all versions)

---

### 7_Testing_known/ - Validation

**Purpose**: Test plans, validation procedures, and acceptance criteria.

**Contents**:
- Unit tests (file parser, transformer, validator)
- Integration tests (end-to-end workflows)
- UI tests (responsive design, interactions)
- Performance tests (load time, resource usage)
- Acceptance criteria checklist
- Real-world test scenarios

**Validation Loop**: Tests reach from unknown problem back to known proof, validating that objectives are met.

---

## Quick Start

1. Review objectives in [1_Real_Unknown/README.md](1_Real_Unknown/README.md)
2. Explore use cases in [2_Environment/README.md](2_Environment/README.md)
3. Open the application: [5_Symbols/postproduction_helper.html](5_Symbols/postproduction_helper.html)
4. Upload sample files from [2_Environment/](2_Environment/)
5. Test with scenarios in [7_Testing_known/README.md](7_Testing_known/README.md)

## Development Workflow

```
┌─────────────┐
│ 1_Real      │ Define unknown problem
│ (Unknown)   │
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ 2_Environment│ Gather requirements
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ 3_Simulation│ Design solution
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ 4_Formula   │ Build algorithms
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ 5_Symbols   │ Implement code
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ 6_Semblance │ Handle errors
└──────┬──────┘
       │
       ▼
┌─────────────┐
│ 7_Testing   │ Validate solution ──┐
│ (Known)     │                     │
└──────┬──────┘                     │
       │                            │
       └─── Reach back to Real ─────┘
            (Proof achieved)
```

## Technologies Used

- **Frontend**: HTML5, CSS3, JavaScript ES6+
- **Syntax Highlighting**: PrismJS
- **YAML Parsing**: js-yaml
- **File Handling**: FileReader API
- **Browser Support**: Modern browsers (2017+)

## File Processing Capabilities

### Supported Formats
- ✅ YAML (.yaml, .yml)
- ✅ JSON (.json)  
- ✅ Subtitles (.srt)
- ✅ Markdown (.md)
- ✅ Text files (.txt)
- ✅ EDL files (.edl)

### Processing Features
- Parse chapter markers with timestamps
- Convert SRT to VTT format
- Generate video descriptions
- Validate asset configurations
- Transform data between formats

## Success Metrics

- ✅ Time saved: 80% reduction in manual formatting
- ✅ Error rate: < 2% in automated outputs  
- ✅ User satisfaction: 9/10 target rating
- ✅ Adoption: 100% of weekly video projects

---

**Project Status**: Week 2, February 2026 - Active Development

**Methodology**: Unknown → Environment → Simulation → Formula → Symbols → Semblance → Testing → Known ✓
