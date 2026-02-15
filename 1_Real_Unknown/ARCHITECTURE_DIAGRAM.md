# Project Architecture Diagram

## Overview
This diagram represents the 7-phase architecture of the Video Post Production Helper project.

## Mermaid Diagram


```mermaid
graph TD
    A[1_Real_Unknown<br/>Goals & Objectives] --> B[2_Environment<br/>Input Data]
    B --> C[3_Simulation<br/>Examples & AI Logs]
    C --> D[4_Formula<br/>Methodologies & Guides]
    D --> E[5_Symbols<br/>Web Interfaces]
    E --> F[6_Semblance<br/>Quality Checks]
    F --> G[7_Testing_known<br/>Validation & Tests]

    H[Root Files<br/>index.html, README.md] --> A
    I[Git Config<br/>.gitignore] --> H

    B --> B1[assets_config.json]
    B --> B2[batch_generation_data.yaml]
    B --> B3[source_*.md/txt/srt]
    B --> B4[icons.json]

    C --> C1[DETAILED_FILE_INVENTORY.csv]
    C --> C2[DETAILED_AI_USAGE.md]
    C --> C3[2026-02-14/input/]

    D --> D1[METHODOLOGY.md]
    D --> D2[PROJECT_STRUCTURE*.md]
    D --> D3[OLLAMA_KILOCODE_SETUP.md]
    D --> D4[QDRANT_DOCKER_LOGS_METHODOLOGY.md]

    E --> E1[postproduction_helper.html]
    E --> E2[video_editing_plan_ready.html]
    E --> E3[file_inventory.html]
    E --> E4[markdown_renderer.html]
    E --> E5[timeline.html]
    E --> E6[nav_5symbols.html]

    F --> F1[SANITY_CHECK_1_REAL_UNKNOWN.md]

    G --> G1[QDRANT_LATEST_LOGS.txt]

    A --> A1[README.md<br/>Objectives & OKRs]
    A --> A2[AI_USAGE_REPORT_XAI.md]
    A --> A3[PROJECT_FILES_ANALYSIS.md]
    A --> A4[ARCHITECTURE_DIAGRAM.md]

    style A fill:#e1f5fe
    style B fill:#f3e5f5
    style C fill:#fff3e0
    style D fill:#e8f5e8
    style E fill:#fce4ec
    style F fill:#ffebee
    style G fill:#e0f2f1
```

## Architecture Explanation

### Flow Direction
The project follows a logical 7-phase progression from unknown problems to known solutions:

1. **1_Real_Unknown**: Define goals and objectives
2. **2_Environment**: Gather and organize input data
3. **3_Simulation**: Create examples and test scenarios
4. **4_Formula**: Develop methodologies and processes
5. **5_Symbols**: Implement working code and interfaces
6. **6_Semblance**: Perform quality checks and error handling
7. **7_Testing_known**: Validate and reach final proof

### Key Components
- **Root Level**: Entry points and general documentation
- **Data Flow**: Information moves from raw inputs to processed outputs
- **Quality Gates**: Each phase includes validation and documentation
- **AI Integration**: AI usage tracked throughout development

### File Organization
- Each phase contains relevant files for that development stage
- Shared components (like navigation) centralized where appropriate
- Documentation distributed across phases for context

*Diagram created on 2026-02-15*