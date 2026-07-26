# System Design Document

**Project:** Multi Device Preview  
**Version:** 1.0  
**Last Updated:** July 26, 2024  
**Document Type:** Technical Architecture

---

## 1. System Overview

Multi Device Preview is a client-side web application that renders multiple webpage previews in isolated iframe containers. The system emphasizes performance, security, and user experience.

### High-Level Architecture

```
┌─────────────────────────────────────────────────────┐
│                  User Browser                        │
│  ┌───────────────────────────────────────────────┐  │
│  │         Multi Device Preview App              │  │
│  │  (Next.js + React + TypeScript)               │  │
│  │                                               │  │
│  │  ┌─────────────────────────────────────────┐ │  │
│  │  │     Main UI (Control Panel)            │ │  │
│  │  │  - Device Selector                     │ │  │
│  │  │  - URL Input                           │ │  │
│  │  │  - Layout Manager                      │ │  │
│  │  └─────────────────────────────────────────┘ │  │
│  │                                               │  │
│  │  ┌────────┬──────────┬─────────────────────┐ │  │
│  │  │ Panel1 │ Panel2   │ Panel3...Panel6     │ │  │
│  │  │ (iframe)│ (iframe) │ (iframes)           │ │  │
│  │  └────────┴──────────┴─────────────────────┘ │  │
│  │                                               │  │
│  │  Local Storage / SessionStorage               │  │
│  │  - Workspace configurations                   │  │
│  │  - User preferences                          │  │
│  └───────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────┘
         │                              │
         └──────────────────────────────┘
         (iframe requests to target URLs)
         
┌─────────────────────────────────────────────────────┐
│          Target Websites (External)                 │
│  - https://example.com                              │
│  - https://competitor.com                           │
│  - Any CORS-enabled website                         │
└─────────────────────────────────────────────────────┘
```

---

## 2. Core Components

### 2.1 Frontend Architecture

```
src/
├── app/
│   ├── layout.tsx              # Root layout
│   ├── page.tsx                # Main page
│   ├── api/                    # API routes (future)
│   └── globals.css             # Global styles
│
├── components/
│   ├── PreviewGrid.tsx         # Main container (6 panels)
│   ├── PreviewPanel.tsx        # Individual iframe + controls
│   ├── ControlBar.tsx          # Device selector, URL input
│   ├── DeviceSelector.tsx      # Device type dropdown
│   ├── URLInput.tsx            # URL input with validation
│   └── ui/
│       ├── Button.tsx          # Basic button
│       ├── Input.tsx           # Form input
│       └── Select.tsx          # Dropdown select
│
├── hooks/
│   ├── usePreviewPanels.ts     # Panel state management
│   ├── useWorkspace.ts         # Workspace save/load (Phase 2)
│   └── useResponsive.ts        # Responsive layout
│
├── types/
│   ├── index.ts
│   └── preview.ts              # Preview panel types
│
├── utils/
│   ├── devices.ts              # Device presets (sizes)
│   ├── validation.ts           # URL validation
│   ├── storage.ts              # LocalStorage helpers
│   └── performance.ts          # Performance metrics
│
└── styles/
    └── globals.css             # Tailwind + custom styles
```

### 2.2 Key Components Detail

#### PreviewGrid Component
- **Responsibility:** Manage 6 preview panels layout
- **State Management:** Panel URLs, device types, visibility
- **Props:** 
  - `panels: PreviewPanel[]`
  - `onPanelUpdate: (panelId, config) => void`
- **Features:**
  - Responsive grid (1-6 columns based on screen)
  - Drag-to-resize panels (future)
  - Enable/disable individual panels

#### PreviewPanel Component
- **Responsibility:** Render single webpage iframe
- **Props:**
  - `id: string`
  - `url: string`
  - `deviceType: 'mobile' | 'tablet' | 'desktop'`
  - `onUpdate: (config) => void`
- **Features:**
  - iframe sandbox security
  - Loading state
  - Error boundary
  - Device frame mockup (future)

#### ControlBar Component
- **Responsibility:** Global controls
- **Features:**
  - Device selector (affects all panels)
  - URL input
  - Add/remove panel buttons
  - Export/save options (Phase 2)

---

## 3. Data Flow

### 3.1 Preview Panel Update Flow

```
User Input (URL/Device)
         │
         ▼
Input Validation
         │
    ┌────┴────┐
    │ Valid? ├─No─► Show Error
    └─Yes─┘
         │
         ▼
Update Panel State (React)
         │
         ▼
iframe src attribute updated
         │
         ▼
Browser loads webpage in iframe
         │
         ▼
Page renders (respects device size)
         │
         ▼
UI Updated (preview visible)
```

### 3.2 State Management Strategy

**Local State (React Hooks):**
- Active panel configurations
- UI state (loading, errors)
- User interactions

**Persistent State (Phase 2):**
- Saved workspaces (LocalStorage MVP → Database Phase 2)
- User preferences
- Recent URLs

---

## Document Metadata

**Author:** Technical Architecture Team  
**Version Control:** GitHub  
**Last Review:** July 26, 2024  
**Next Review:** September 26, 2024