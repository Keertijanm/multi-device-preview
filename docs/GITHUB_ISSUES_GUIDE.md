# GitHub Issues Migration Guide

**Project:** Multi Device Preview  
**Purpose:** Convert TASKS.md into GitHub Issues  
**Total Issues:** 35 MVP Tasks (MDP-001 to MDP-035)

---

## 📋 Quick Reference: All MVP Tasks

### Sprint 1-2: Foundation (7 tasks)

```
MDP-001: Project Setup & Development Environment
MDP-002: Design System & Tailwind Configuration
MDP-003: Base UI Components Setup (shadcn/ui)
MDP-004: Create TypeScript Types & Interfaces
MDP-005: Implement Device Presets Utility
MDP-006: URL Validation Utility
MDP-007: Local Storage Utility
```

### Sprint 2-4: Core Features (7 tasks)

```
MDP-008: Create PreviewGrid Component
MDP-009: Create PreviewPanel Component
MDP-010: Create URLInput Component
MDP-011: Create DeviceSelector Component
MDP-012: Create ControlBar Component
MDP-013: Create Main Page Layout
```

### Sprint 4-5: Quality & UX (7 tasks)

```
MDP-014: Implement Error Boundary Component
MDP-015: Create CORS Error Handling
MDP-016: Implement Loading States
MDP-017: Implement Responsive Layout
MDP-018: Implement Keyboard Navigation
MDP-019: Implement Screen Reader Support
```

### Sprint 6-8: Performance & Security (8 tasks)

```
MDP-020: Performance Optimization - Code Splitting
MDP-021: Performance Optimization - iframe Loading
MDP-022: Implement iframe Security Sandbox
MDP-023: Implement Content Security Policy
MDP-024: Unit Test Suite - Components
MDP-025: Unit Test Suite - Utilities
MDP-026: Cross-Browser Testing
MDP-027: Accessibility Audit (WCAG 2.1 AA)
```

### Sprint 8-9: Launch (8 tasks)

```
MDP-028: Documentation - Component Documentation
MDP-029: Documentation - API Documentation
MDP-030: Setup Continuous Integration
MDP-031: Deploy to Vercel
MDP-032: Performance Monitoring Setup
MDP-033: Beta Testing & Feedback Collection
MDP-034: Bug Fixes & Iteration (Week 9)
MDP-035: MVP Launch Preparation
```

---

## 🏷️ GitHub Labels to Create

Before creating issues, create these labels in GitHub:

```
Type-Feature       (Blue) - New feature implementation
Type-Technical     (Purple) - Technical setup/infrastructure
Type-Testing       (Orange) - Testing & QA
Type-Documentation (Gray) - Documentation
Type-Launch        (Red) - Launch-related tasks

Priority-P0        (Red) - Critical/Blocking
Priority-P1        (Orange) - High priority
Priority-P2        (Yellow) - Medium priority

Sprint-1           (Light Blue)
Sprint-2           (Light Blue)
Sprint-3           (Light Blue)
... Sprint-9       (Light Blue)

Component-UI       (Green)
Component-Core     (Green)
Component-Utils    (Green)
Component-Testing  (Green)

MVP                (Purple)
Phase-2            (Blue)
```

---

## 📌 Milestones to Create

```
Milestone: Sprint 1
Milestone: Sprint 2
Milestone: Sprint 3
Milestone: Sprint 4
Milestone: Sprint 5
Milestone: Sprint 6
Milestone: Sprint 7
Milestone: Sprint 8
Milestone: Sprint 9
Milestone: MVP Launch
Milestone: Phase 2 Planning
```

---

## 🔗 Issue Template Format

Each GitHub Issue should follow this format:

```markdown
## User Story
As a [user type]
I want to [capability]
So that [benefit]

## Acceptance Criteria
- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3

## Technical Notes
- Implementation guidance
- Technology choices
- Known constraints

## Definition of Done
- [ ] Code complete with TypeScript types
- [ ] Unit tests written (80%+ coverage)
- [ ] Component documented
- [ ] Cross-browser tested
- [ ] Accessibility verified
- [ ] Code review approved
- [ ] Merged to main branch
```

---

## 🛠️ How to Create Issues

### Option 1: Manual Creation (Recommended for first few)

1. Go to: https://github.com/Keertijanm/multi-device-preview/issues/new
2. Copy issue title from TASKS.md (e.g., "MDP-001: Project Setup & Development Environment")
3. Copy description content
4. Add labels
5. Assign to milestone
6. Click "Create issue"

### Option 2: GitHub CLI (Fastest for batch)

```bash
# Install GitHub CLI if not already installed
brew install gh  # macOS
# or apt install gh  # Linux
# or download from https://cli.github.com

# Authenticate
gh auth login

# Navigate to repo
cd multi-device-preview

# Create single issue
gh issue create \
  --title "MDP-001: Project Setup & Development Environment" \
  --body "$(cat <<'EOF'
## Type
Technical Setup

## Priority
P0

## Complexity
M

## Story Points
5

## Description
Initialize the Next.js 15 project with TypeScript, Tailwind CSS, and development tools.

## Acceptance Criteria
- [ ] Next.js 15 project created with App Router
- [ ] TypeScript configured (strict mode enabled)
- [ ] Tailwind CSS integrated and configured
- [ ] ESLint configured
- [ ] Prettier configured
- [ ] Git repository initialized
- [ ] GitHub repository configured
- [ ] Development server runs
- [ ] Build process works
- [ ] Environment configuration ready

## Technical Notes
- Use npx create-next-app@latest
- Configure tsconfig.json with strict mode
- Add path aliases
- Configure Prettier with Tailwind

## Definition of Done
- [ ] npm run dev starts dev server
- [ ] npm run build builds production bundle
- [ ] TypeScript compilation succeeds
- [ ] ESLint passes
- [ ] Prettier formats code correctly
- [ ] README updated
- [ ] Git workflow documented
EOF
)" \
  --label "Type-Technical,Priority-P0,Sprint-1,MVP" \
  --milestone "Sprint 1"
```

### Option 3: Bulk Creation with Script

Create a file `create-issues.sh`:

```bash
#!/bin/bash

# MDP-001
gh issue create \
  --title "MDP-001: Project Setup & Development Environment" \
  --body-file issues/mdp-001.md \
  --label "Type-Technical,Priority-P0,Sprint-1,MVP" \
  --milestone "Sprint 1"

# MDP-002
gh issue create \
  --title "MDP-002: Design System & Tailwind Configuration" \
  --body-file issues/mdp-002.md \
  --label "Type-Technical,Priority-P0,Sprint-1,MVP" \
  --milestone "Sprint 1"

# ... repeat for all 35 issues
```

---

## 📝 Individual Issue Templates

Below are the exact formatted templates for each MVP task ready to copy:

---

## MDP-001: Project Setup & Development Environment

**Type:** Technical Setup  
**Priority:** P0  
**Complexity:** M  
**Story Points:** 5  
**Labels:** Type-Technical, Priority-P0, Sprint-1, MVP  
**Milestone:** Sprint 1

**Body:**

```
## Description
Initialize the Next.js 15 project with TypeScript, Tailwind CSS, and development tools. Set up GitHub repository, configure ESLint, Prettier, and development environment.

## Acceptance Criteria
- [ ] Next.js 15 project created with App Router
- [ ] TypeScript configured (strict mode enabled)
- [ ] Tailwind CSS integrated and configured
- [ ] ESLint configured with recommended rules
- [ ] Prettier configured for code formatting
- [ ] Git repository initialized with proper .gitignore
- [ ] GitHub repository created and configured
- [ ] Development server runs without errors
- [ ] Build process works correctly
- [ ] Environment configuration ready for dev/prod

## Technical Notes
- Use `npx create-next-app@latest` with TypeScript flag
- Configure `tsconfig.json` with strict mode
- Add path aliases: `@/*` pointing to project root
- Configure Prettier to work with Tailwind class sorting
- Set up Git pre-commit hooks with Husky (optional for MVP)

## Dependencies
- None (starting point)

## Definition of Done
- [ ] `npm run dev` starts dev server on localhost:3000
- [ ] `npm run build` builds production bundle
- [ ] TypeScript compilation succeeds with no errors
- [ ] ESLint passes with zero warnings
- [ ] Prettier formats code correctly
- [ ] README updated with setup instructions
- [ ] Git workflow documented
```

---

## MDP-002: Design System & Tailwind Configuration

**Type:** Technical Setup  
**Priority:** P0  
**Complexity:** M  
**Story Points:** 5  
**Labels:** Type-Technical, Priority-P0, Sprint-1, MVP  
**Milestone:** Sprint 1

**Body:**

```
## Description
Configure Tailwind CSS with design tokens, typography, colors, and custom utility classes. Establish design system foundation for consistent UI.

## Acceptance Criteria
- [ ] Color palette defined and configured
- [ ] Typography system configured
- [ ] Spacing scale defined
- [ ] Custom utility classes created
- [ ] Dark mode CSS structure ready (Phase 2 activation)
- [ ] Responsive breakpoints configured
- [ ] Tailwind plugins integrated
- [ ] Global styles file created
- [ ] Design system documented

## Technical Notes
- Define primary, secondary, accent color schemes
- Create utility classes for common patterns
- Configure spacing scale (4px base unit)
- Set up responsive design tokens
- Prepare dark mode with `class` strategy

## Dependencies
- MDP-001: Project Setup

## Definition of Done
- [ ] `tailwind.config.js` fully configured
- [ ] `globals.css` includes Tailwind directives
- [ ] Design system documented in `/docs/DESIGN.md`
- [ ] Color palette exported as tokens
- [ ] Typography examples created
```

---

## MDP-003: Base UI Components Setup (shadcn/ui)

**Type:** Technical Setup  
**Priority:** P0  
**Complexity:** M  
**Story Points:** 8  
**Labels:** Type-Technical, Priority-P0, Sprint-1-2, MVP  
**Milestone:** Sprint 2

**Body:**

```
## Description
Configure and install shadcn/ui component library. Set up component structure and establish base components for the project.

## Acceptance Criteria
- [ ] shadcn/ui configured in project
- [ ] Button component installed and customized
- [ ] Input component installed and customized
- [ ] Select/Dropdown component installed and customized
- [ ] Alert component installed for error messages
- [ ] Spinner/Loading component installed
- [ ] Badge component installed
- [ ] Component structure documented
- [ ] Usage examples created

## Technical Notes
- Use `npx shadcn-ui@latest init` to set up
- Configure components path in `components.json`
- Customize components to match design system
- Create component wrappers for common patterns
- Document component usage in storybook (optional for MVP)

## Dependencies
- MDP-001: Project Setup
- MDP-002: Design System

## Definition of Done
- [ ] All base components installed and working
- [ ] Components tested in isolation
- [ ] Component documentation created
- [ ] Usage guide written
```

---

## MDP-004: Create TypeScript Types & Interfaces

**Type:** Technical Setup  
**Priority:** P0  
**Complexity:** M  
**Story Points:** 5  
**Labels:** Type-Technical, Priority-P0, Sprint-2, MVP  
**Milestone:** Sprint 2

**Body:**

```
## Description
Define all TypeScript types and interfaces for the application. Establish type safety across the codebase.

## Acceptance Criteria
- [ ] PreviewPanel interface defined
- [ ] Device type defined (Mobile | Tablet | Desktop)
- [ ] Device preset interface defined
- [ ] Workspace interface defined
- [ ] App state interface defined
- [ ] Error types defined
- [ ] API response types defined
- [ ] Utility types created
- [ ] Types documentation created

## Technical Notes
```
interface PreviewPanel {
  id: string;
  url: string;
  device: DeviceType;
  isLoading: boolean;
  error: string | null;
  isVisible: boolean;
}

type DeviceType = 'mobile-320' | 'mobile-375' | 'mobile-414' | 'tablet-768' | 'desktop-1920';

interface DevicePreset {
  name: string;
  width: number;
  height: number;
  userAgent?: string;
}
```

## Dependencies
- MDP-001: Project Setup

## Definition of Done
- [ ] `/src/types/index.ts` created with all types
- [ ] `/src/types/preview.ts` created with preview types
- [ ] `/src/types/devices.ts` created with device types
- [ ] All types properly exported
- [ ] No `any` types used
- [ ] Types documentation written
```

---

## MDP-005: Implement Device Presets Utility

**Type:** Feature  
**Priority:** P0  
**Complexity:** S  
**Story Points:** 3  
**Labels:** Type-Feature, Priority-P0, Sprint-2, Component-Utils, MVP  
**Milestone:** Sprint 2

**Body:**

```
## Description
Create device presets configuration with standard mobile, tablet, and desktop sizes. Define viewport dimensions and user agents.

## Acceptance Criteria
- [ ] Mobile presets defined (320px, 375px, 414px)
- [ ] Tablet preset defined (768px)
- [ ] Desktop preset defined (1920px)
- [ ] User agents configured for each device
- [ ] Device presets exported as constant
- [ ] Utility function to get preset by type
- [ ] Utility function to validate device
- [ ] Tests written for utilities

## Technical Notes
```
export const DEVICE_PRESETS: Record<DeviceType, DevicePreset> = {
  'mobile-320': { name: 'iPhone SE', width: 320, height: 667, ... },
  'mobile-375': { name: 'iPhone 12', width: 375, height: 812, ... },
  // ...
};
```

## Dependencies
- MDP-004: TypeScript Types

## Definition of Done
- [ ] `/src/utils/devices.ts` created
- [ ] All presets defined with accurate dimensions
- [ ] Utility functions working correctly
- [ ] Unit tests written (100% coverage)
```

---

## MDP-006: URL Validation Utility

**Type:** Feature  
**Priority:** P0  
**Complexity:** S  
**Story Points:** 3  
**Labels:** Type-Feature, Priority-P0, Sprint-2, Component-Utils, MVP  
**Milestone:** Sprint 2

**Body:**

```
## Description
Create URL validation utility to ensure only valid HTTP/HTTPS URLs are used, rejecting malicious protocols.

## Acceptance Criteria
- [ ] Validates http:// and https:// protocols
- [ ] Rejects javascript://, data://, file:// protocols
- [ ] Validates URL format with URL API
- [ ] Returns validation result with error message
- [ ] Handles edge cases (empty, null, undefined)
- [ ] Returns user-friendly error messages
- [ ] Unit tests written

## Technical Notes
```
export function validateURL(url: string): ValidationResult {
  // Returns { isValid: boolean, error?: string }
}

export function isSafeProtocol(url: string): boolean {
  // Returns true only for http:// or https://
}
```

## Dependencies
- MDP-004: TypeScript Types

## Definition of Done
- [ ] `/src/utils/validation.ts` created
- [ ] Validation function working correctly
- [ ] Error messages user-friendly
- [ ] Unit tests written (100% coverage)
```

---

## MDP-007: Local Storage Utility

**Type:** Technical Setup  
**Priority:** P1  
**Complexity:** S  
**Story Points:** 3  
**Labels:** Type-Technical, Priority-P1, Sprint-2, Component-Utils, MVP  
**Milestone:** Sprint 2

**Body:**

```
## Description
Create LocalStorage utility wrapper for consistent data persistence. Handle serialization, error handling, and type safety.

## Acceptance Criteria
- [ ] Generic get/set functions with type safety
- [ ] Error handling for quota exceeded
- [ ] Error handling for browser restrictions
- [ ] Clear function for data removal
- [ ] Key prefix for namespace isolation
- [ ] Unit tests written

## Technical Notes
```
export const storage = {
  set<T>(key: string, value: T): void { },
  get<T>(key: string): T | null { },
  remove(key: string): void { },
  clear(): void { }
};
```

## Dependencies
- MDP-004: TypeScript Types

## Definition of Done
- [ ] `/src/utils/storage.ts` created
- [ ] All functions type-safe
- [ ] Error handling complete
- [ ] Unit tests written (100% coverage)
```

---

## MDP-008: Create PreviewGrid Component

**Type:** Feature  
**Priority:** P0  
**Complexity:** L  
**Story Points:** 8  
**Labels:** Type-Feature, Priority-P0, Sprint-2-3, Component-UI, MVP  
**Milestone:** Sprint 3

**Body:**

```
## User Story
As a developer
I want to view up to 6 webpages in independent preview panels
So that I can compare multiple pages side-by-side

## Description
Create the main PreviewGrid component that manages layout of 6 preview panels with responsive grid layout.

## Acceptance Criteria
- [ ] Component accepts panel configuration array
- [ ] Renders up to 6 PreviewPanel components
- [ ] Responsive grid layout (1/2/3/6 columns based on screen)
- [ ] Grid uses CSS Grid for layout
- [ ] Panels resize smoothly
- [ ] State management for panel visibility
- [ ] Add/remove panel functionality
- [ ] Accessibility verified (WCAG 2.1 AA)
- [ ] TypeScript types properly defined
- [ ] Component tests written

## Technical Notes
- Use CSS Grid for responsive layout
- Responsive breakpoints: 320px (1 col), 768px (2 col), 1024px (3 col), 1920px (6 col)
- Use React state (useState) for panel management
- Implement key prop correctly for list rendering
- Optimize re-renders with React.memo if needed

## Dependencies
- MDP-002: Design System
- MDP-003: Base UI Components
- MDP-004: TypeScript Types

## Definition of Done
- [ ] `/src/components/PreviewGrid.tsx` created
- [ ] Responsive design tested on breakpoints
- [ ] Component renders correctly
- [ ] Props drilling simplified
- [ ] Unit tests written (80%+ coverage)
- [ ] Component props documented (JSDoc)
```

---

## MDP-009: Create PreviewPanel Component

**Type:** Feature  
**Priority:** P0  
**Complexity:** L  
**Story Points:** 8  
**Labels:** Type-Feature, Priority-P0, Sprint-3, Component-UI, MVP  
**Milestone:** Sprint 3

**Body:**

```
## User Story
As a developer
I want to view individual webpages in separate panels with device frames
So that I can see how pages look on specific devices

## Description
Create PreviewPanel component that renders individual iframe with device frame mockup and controls.

## Acceptance Criteria
- [ ] Component renders iframe with sandbox security
- [ ] Applies device viewport dimensions
- [ ] Displays loading state while content loads
- [ ] Displays error state for CORS/network issues
- [ ] Panel header with title and controls
- [ ] Enable/disable toggle button
- [ ] Remove button with confirmation
- [ ] Device selector dropdown
- [ ] URL display in header
- [ ] Accessibility verified (WCAG 2.1 AA)
- [ ] TypeScript types properly defined
- [ ] Component tests written

## Technical Notes
```
<iframe
  sandbox="allow-same-origin allow-scripts allow-popups allow-forms"
  src={url}
  title={`Preview panel for ${url}`}
  style={{ width: `${deviceWidth}px` }}
/>
```

## Dependencies
- MDP-002: Design System
- MDP-003: Base UI Components
- MDP-008: PreviewGrid Component
- MDP-004: TypeScript Types

## Definition of Done
- [ ] `/src/components/PreviewPanel.tsx` created
- [ ] iframe sandbox properly configured
- [ ] Loading and error states working
- [ ] Device dimensions applied correctly
- [ ] Unit tests written (80%+ coverage)
- [ ] Component props documented
```

---

## MDP-010: Create URLInput Component

**Type:** Feature  
**Priority:** P0  
**Complexity:** M  
**Story Points:** 5  
**Labels:** Type-Feature, Priority-P0, Sprint-3, Component-UI, MVP  
**Milestone:** Sprint 3

**Body:**

```
## User Story
As a developer
I want to enter URLs for preview panels
So that I can preview different webpages

## Description
Create URLInput component for entering and validating URLs for preview panels.

## Acceptance Criteria
- [ ] Input field accepts HTTP/HTTPS URLs
- [ ] Real-time validation on input
- [ ] Error message displayed for invalid URLs
- [ ] Clear button to reset URL
- [ ] Enter key submits URL
- [ ] Placeholder text provided
- [ ] Accessibility verified (WCAG 2.1 AA)
- [ ] TypeScript types properly defined
- [ ] Component tests written

## Technical Notes
- Use shadcn/ui Input component as base
- Validate on blur and on enter key
- Display inline error message
- Reset URL with clear button
- Debounce validation for performance

## Dependencies
- MDP-002: Design System
- MDP-003: Base UI Components
- MDP-006: URL Validation Utility
- MDP-004: TypeScript Types

## Definition of Done
- [ ] `/src/components/URLInput.tsx` created
- [ ] Validation working correctly
- [ ] Error messages user-friendly
- [ ] Unit tests written (80%+ coverage)
```

---

## MDP-011: Create DeviceSelector Component

**Type:** Feature  
**Priority:** P0  
**Complexity:** M  
**Story Points:** 5  
**Labels:** Type-Feature, Priority-P0, Sprint-3, Component-UI, MVP  
**Milestone:** Sprint 3

**Body:**

```
## User Story
As a QA engineer
I want to choose different device types for each panel
So that I can test responsive design across multiple devices

## Description
Create DeviceSelector component for choosing device type (Mobile, Tablet, Desktop).

## Acceptance Criteria
- [ ] Dropdown displays device options
- [ ] Options show device name and dimensions
- [ ] Select device applies to specific panel
- [ ] onChange callback triggers parent update
- [ ] Accessibility verified (WCAG 2.1 AA)
- [ ] Keyboard navigation works
- [ ] TypeScript types properly defined
- [ ] Component tests written

## Technical Notes
- Use shadcn/ui Select component as base
- Display device presets from utils
- Show dimensions in option label
- Handle selection change callback

## Dependencies
- MDP-002: Design System
- MDP-003: Base UI Components
- MDP-005: Device Presets Utility
- MDP-004: TypeScript Types

## Definition of Done
- [ ] `/src/components/DeviceSelector.tsx` created
- [ ] All device options displayed
- [ ] Selection working correctly
- [ ] Unit tests written (80%+ coverage)
```

---

## MDP-012: Create ControlBar Component

**Type:** Feature  
**Priority:** P0  
**Complexity:** M  
**Story Points:** 8  
**Labels:** Type-Feature, Priority-P0, Sprint-3-4, Component-UI, MVP  
**Milestone:** Sprint 4

**Body:**

```
## User Story
As a user
I want to have centralized controls for all preview settings
So that I can easily manage my preview configuration

## Description
Create ControlBar component with global controls for device selection, add/remove panels, and future export functionality.

## Acceptance Criteria
- [ ] Component displays above preview grid
- [ ] Global device selector (affects all panels)
- [ ] Add panel button (max 6 panels)
- [ ] Remove all button with confirmation
- [ ] Sticky positioning at top
- [ ] Responsive design on all screen sizes
- [ ] Clear visual hierarchy
- [ ] Accessibility verified (WCAG 2.1 AA)
- [ ] TypeScript types properly defined
- [ ] Component tests written

## Technical Notes
- Use flexbox for responsive layout
- Global device selector overrides individual selection
- Add/Remove buttons trigger parent callbacks
- Sticky positioning: `position: sticky; top: 0; z-index: 10;`
- Prepare for export button (Phase 2)

## Dependencies
- MDP-002: Design System
- MDP-003: Base UI Components
- MDP-011: DeviceSelector Component
- MDP-004: TypeScript Types

## Definition of Done
- [ ] `/src/components/ControlBar.tsx` created
- [ ] All controls working correctly
- [ ] Responsive design tested
- [ ] Unit tests written (80%+ coverage)
```

---

## MDP-013: Create Main Page Layout

**Type:** Feature  
**Priority:** P0  
**Complexity:** M  
**Story Points:** 5  
**Labels:** Type-Feature, Priority-P0, Sprint-4, Component-Core, MVP  
**Milestone:** Sprint 4

**Body:**

```
## User Story
As a user
I want to have a clean, organized interface
So that I can easily use Multi Device Preview

## Description
Create main application page (app/page.tsx) that integrates ControlBar and PreviewGrid components.

## Acceptance Criteria
- [ ] Page component imports ControlBar and PreviewGrid
- [ ] Manages global state for panels
- [ ] Handles panel add/remove logic
- [ ] Handles device selection logic
- [ ] Handles URL updates
- [ ] Responsive layout verified
- [ ] Performance optimized
- [ ] TypeScript types properly defined
- [ ] Page component tests written

## Technical Notes
- Use React hooks (useState, useCallback) for state
- Initialize with 3 default empty panels
- Implement callbacks for child components
- Optimize re-renders with useCallback
- Prepare for localStorage persistence (Phase 2)

## Dependencies
- MDP-012: ControlBar Component
- MDP-008: PreviewGrid Component
- MDP-009: PreviewPanel Component
- MDP-004: TypeScript Types

## Definition of Done
- [ ] `/src/app/page.tsx` created
- [ ] All components integrated
- [ ] State management working
- [ ] Page tests written
- [ ] Manual testing completed
```

---

## MDP-014: Implement Error Boundary Component

**Type:** Feature  
**Priority:** P1  
**Complexity:** M  
**Story Points:** 5  
**Labels:** Type-Feature, Priority-P1, Sprint-4, Component-Core, MVP  
**Milestone:** Sprint 4

**Body:**

```
## User Story
As a user
I want to see helpful error messages when something goes wrong
So that I can understand what happened and how to fix it

## Description
Create Error Boundary component to catch and display errors gracefully.

## Acceptance Criteria
- [ ] Component catches React errors
- [ ] Displays user-friendly error messages
- [ ] Error fallback UI created
- [ ] Option to retry/reset
- [ ] Logs errors to console (dev)
- [ ] Accessibility verified (WCAG 2.1 AA)
- [ ] TypeScript types properly defined
- [ ] Component tests written

## Technical Notes
- Use React error boundary pattern
- Create separate ErrorFallback component
- Log errors for debugging
- Provide reset functionality

## Dependencies
- MDP-002: Design System
- MDP-003: Base UI Components

## Definition of Done
- [ ] `/src/components/ErrorBoundary.tsx` created
- [ ] Error handling working
- [ ] Unit tests written
```

---

## MDP-015: Create CORS Error Handling

**Type:** Feature  
**Priority:** P1  
**Complexity:** M  
**Story Points:** 5  
**Labels:** Type-Feature, Priority-P1, Sprint-4, Component-Core, MVP  
**Milestone:** Sprint 4

**Body:**

```
## User Story
As a developer
I want to receive clear feedback about CORS errors
So that I understand why a website won't preview

## Description
Implement CORS error detection and user-friendly error messages with workaround suggestions.

## Acceptance Criteria
- [ ] Detect CORS errors from iframes
- [ ] Display user-friendly error message
- [ ] Suggest CORS workarounds
- [ ] Provide documentation link
- [ ] Clear error when issue resolved
- [ ] Error logging for debugging
- [ ] TypeScript types properly defined
- [ ] Tests written

## Technical Notes
- Monitor iframe onerror events
- Check for CORS-specific error messages
- Create helpful error component
- Link to CORS documentation

## Dependencies
- MDP-009: PreviewPanel Component
- MDP-014: Error Boundary Component

## Definition of Done
- [ ] Error detection working
- [ ] Error messages displayed
- [ ] Documentation provided
```

---

## MDP-016: Implement Loading States

**Type:** Feature  
**Priority:** P1  
**Complexity:** M  
**Story Points:** 5  
**Labels:** Type-Feature, Priority-P1, Sprint-4-5, Component-UI, MVP  
**Milestone:** Sprint 5

**Body:**

```
## User Story
As a user
I want to see loading indicators
So that I know when content is loading

## Description
Implement loading indicators and skeleton screens for preview panels.

## Acceptance Criteria
- [ ] Loading skeleton shown on panel
- [ ] Loading indicator displayed for 2+ seconds
- [ ] Smooth transition to loaded content
- [ ] Loading cancelled if panel disabled
- [ ] Loading timeout after 30 seconds
- [ ] Loading state in iframe onload event
- [ ] TypeScript types properly defined
- [ ] Component tests written

## Technical Notes
- Create LoadingSkeleton component
- Use iframe onload/onerror events
- Set timeout for stuck loading
- Smooth CSS transitions

## Dependencies
- MDP-009: PreviewPanel Component
- MDP-003: Base UI Components

## Definition of Done
- [ ] Loading component created
- [ ] Loading states working
- [ ] Tests written
```

---

## MDP-017: Implement Responsive Layout

**Type:** Feature  
**Priority:** P0  
**Complexity:** L  
**Story Points:** 8  
**Labels:** Type-Feature, Priority-P0, Sprint-5, MVP  
**Milestone:** Sprint 5

**Body:**

```
## User Story
As a mobile user
I want the application to work well on my phone
So that I can use Multi Device Preview on any device

## Description
Implement responsive CSS layout for mobile-first design with Tailwind breakpoints.

## Acceptance Criteria
- [ ] 1 column on mobile (320px)
- [ ] 2 columns on tablet (768px)
- [ ] 3 columns on mid-screen (1024px)
- [ ] 6 columns on desktop (1920px)
- [ ] Panels resize smoothly
- [ ] No horizontal scroll on mobile
- [ ] Content readable at all sizes
- [ ] Touch-friendly controls on mobile
- [ ] Performance optimized
- [ ] Tested on real devices

## Technical Notes
- Use Tailwind responsive classes
- Mobile-first CSS approach
- Test breakpoints: 320px, 375px, 768px, 1024px, 1920px
- Use CSS Grid for flexibility

## Dependencies
- MDP-008: PreviewGrid Component
- MDP-002: Design System

## Definition of Done
- [ ] Responsive design tested on all breakpoints
- [ ] No horizontal scroll
- [ ] Content readable at all sizes
- [ ] Cross-browser tested
```

---

## MDP-018: Implement Keyboard Navigation

**Type:** Feature  
**Priority:** P1  
**Complexity:** M  
**Story Points:** 8  
**Labels:** Type-Feature, Priority-P1, Sprint-5, MVP  
**Milestone:** Sprint 5

**Body:**

```
## User Story
As a keyboard user
I want to navigate the application using only keyboard
So that I can use Multi Device Preview without a mouse

## Description
Implement keyboard navigation and shortcuts for accessibility.

## Acceptance Criteria
- [ ] All controls keyboard accessible
- [ ] Tab order logical and intuitive
- [ ] Focus indicators visible (2px outline)
- [ ] Enter key submits forms/URLs
- [ ] Escape key clears selections
- [ ] Keyboard shortcuts documented
- [ ] Screen readers can navigate
- [ ] No keyboard traps
- [ ] Tests written

## Technical Notes
- Focus indicators: `outline-2 outline-offset-2 outline-blue-500`
- Logical tab order through components
- Document shortcuts in help/docs
- Test with screen readers

## Dependencies
- All UI Components

## Definition of Done
- [ ] Keyboard navigation tested
- [ ] Focus indicators visible
- [ ] No keyboard traps
- [ ] Shortcuts documented
```

---

## MDP-019: Implement Screen Reader Support

**Type:** Feature  
**Priority:** P1  
**Complexity:** L  
**Story Points:** 8  
**Labels:** Type-Feature, Priority-P1, Sprint-5-6, MVP  
**Milestone:** Sprint 6

**Body:**

```
## User Story
As a visually impaired user
I want to use Multi Device Preview with a screen reader
So that I can access all functionality

## Description
Implement ARIA labels, semantic HTML, and screen reader support.

## Acceptance Criteria
- [ ] ARIA labels on all controls
- [ ] Semantic HTML used throughout
- [ ] Form labels properly associated
- [ ] Images have alt text
- [ ] Links have descriptive text
- [ ] Tested with NVDA/JAWS/VoiceOver
- [ ] Headings properly structured
- [ ] Region landmarks used
- [ ] Tests written

## Technical Notes
- Use semantic HTML: `<button>`, `<input>`, `<label>`
- Add ARIA labels where semantic HTML insufficient
- Test with multiple screen readers
- Use proper heading hierarchy (h1, h2, h3)

## Dependencies
- All UI Components

## Definition of Done
- [ ] ARIA labels added throughout
- [ ] Screen reader tested
- [ ] Semantic HTML verified
- [ ] Tests written
```

---

## MDP-020: Performance Optimization - Code Splitting

**Type:** Technical  
**Priority:** P1  
**Complexity:** M  
**Story Points:** 8  
**Labels:** Type-Technical, Priority-P1, Sprint-6, MVP  
**Milestone:** Sprint 6

**Body:**

```
## Description
Implement code splitting and lazy loading for optimal performance.

## Acceptance Criteria
- [ ] Initial bundle < 100KB gzip
- [ ] CSS bundle < 50KB gzip
- [ ] Non-critical components lazy loaded
- [ ] Route-based code splitting
- [ ] Dynamic imports for utilities
- [ ] Prefetch on hover for common routes
- [ ] Bundle analyzer configured
- [ ] Performance metrics tracked
- [ ] Tests written

## Technical Notes
- Use Next.js automatic code splitting
- Configure bundle analyzer
- Lazy load with React.lazy()
- Use dynamic() for non-critical imports
- Monitor with Vercel Analytics

## Dependencies
- MDP-001: Project Setup

## Definition of Done
- [ ] Bundle size < 150KB gzip total
- [ ] Initial bundle < 100KB gzip
- [ ] Bundle analyzer configured
- [ ] Performance tested
```

---

## MDP-021: Performance Optimization - iframe Loading

**Type:** Feature  
**Priority:** P1  
**Complexity:** M  
**Story Points:** 8  
**Labels:** Type-Feature, Priority-P1, Sprint-6, MVP  
**Milestone:** Sprint 6

**Body:**

```
## Description
Optimize iframe loading performance with prioritization and lazy loading.

## Acceptance Criteria
- [ ] First 3 panels prioritized
- [ ] Remaining panels lazy loaded
- [ ] Off-screen panels unloaded
- [ ] Per-panel load time < 1 second
- [ ] Total 6-panel load < 6 seconds
- [ ] Memory usage < 500MB for 6 panels
- [ ] Performance metrics collected
- [ ] Load testing completed
- [ ] Tests written

## Technical Notes
- Prioritize first 3 panels for immediate display
- Use Intersection Observer for lazy loading
- Monitor memory with DevTools
- Implement cleanup on unmount

## Dependencies
- MDP-009: PreviewPanel Component

## Definition of Done
- [ ] Load time benchmarks met
- [ ] Memory usage optimized
- [ ] Load testing completed
```

---

## MDP-022: Implement iframe Security Sandbox

**Type:** Feature  
**Priority:** P0  
**Complexity:** M  
**Story Points:** 5  
**Labels:** Type-Feature, Priority-P0, Sprint-6, MVP  
**Milestone:** Sprint 6

**Body:**

```
## Description
Configure iframe sandbox security attributes and implement security best practices.

## Acceptance Criteria
- [ ] iframe sandbox attribute properly configured
- [ ] Only necessary permissions allowed
- [ ] Parent window inaccessible from iframe
- [ ] Plugins disabled
- [ ] Top-level navigation disabled
- [ ] Form submission controlled
- [ ] Pop-ups allowed but sandboxed
- [ ] Security policy documented
- [ ] Security audit completed
- [ ] Tests written

## Technical Notes
```
<iframe
  sandbox="allow-same-origin allow-scripts allow-popups allow-forms allow-popups-to-escape-sandbox allow-presentation"
  src={url}
/>
```

## Dependencies
- MDP-009: PreviewPanel Component

## Definition of Done
- [ ] Sandbox configured correctly
- [ ] Security tested
- [ ] Documentation written
```

---

## MDP-023: Implement Content Security Policy

**Type:** Feature  
**Priority:** P1  
**Complexity:** M  
**Story Points:** 5  
**Labels:** Type-Feature, Priority-P1, Sprint-6-7, MVP  
**Milestone:** Sprint 7

**Body:**

```
## Description
Implement Content Security Policy headers and restrictions.

## Acceptance Criteria
- [ ] CSP headers configured in next.config.js
- [ ] No inline scripts allowed
- [ ] No eval() usage
- [ ] External resources whitelisted
- [ ] Violations logged
- [ ] Policy tested with security tools
- [ ] Documentation written
- [ ] Tests written

## Technical Notes
- Configure CSP in `next.config.js`
- Use `Content-Security-Policy` header
- Monitor violations with report-uri
- Gradually tighten restrictions

## Dependencies
- MDP-001: Project Setup

## Definition of Done
- [ ] CSP headers configured
- [ ] Security tested
- [ ] No violations reported
```

---

## MDP-024: Unit Test Suite - Components

**Type:** Technical  
**Priority:** P1  
**Complexity:** L  
**Story Points:** 13  
**Labels:** Type-Testing, Priority-P1, Sprint-7, MVP  
**Milestone:** Sprint 7

**Body:**

```
## Description
Create comprehensive unit tests for all React components.

## Acceptance Criteria
- [ ] 80%+ code coverage for all components
- [ ] Tests for rendering
- [ ] Tests for user interactions
- [ ] Tests for props
- [ ] Tests for state changes
- [ ] Tests for error states
- [ ] Mock external dependencies
- [ ] Snapshot tests where appropriate
- [ ] Tests documented

## Technical Notes
- Use Vitest for unit testing
- Use React Testing Library
- Test user interactions, not implementation
- Mock API calls
- Use describe/it structure

## Dependencies
- All UI Components

## Definition of Done
- [ ] 80%+ test coverage
- [ ] All tests passing
- [ ] Test documentation written
```

---

## MDP-025: Unit Test Suite - Utilities

**Type:** Technical  
**Priority:** P1  
**Complexity:** M  
**Story Points:** 8  
**Labels:** Type-Testing, Priority-P1, Sprint-7, MVP  
**Milestone:** Sprint 7

**Body:**

```
## Description
Create comprehensive unit tests for utility functions.

## Acceptance Criteria
- [ ] 100% code coverage for utilities
- [ ] Tests for valid inputs
- [ ] Tests for invalid inputs
- [ ] Tests for edge cases
- [ ] Tests for error handling
- [ ] Tests for performance
- [ ] All tests passing
- [ ] Test documentation written

## Technical Notes
- Test all utilities: devices, validation, storage
- Test edge cases thoroughly
- Performance tests for critical paths

## Dependencies
- MDP-005: Device Presets
- MDP-006: URL Validation
- MDP-007: LocalStorage Utility

## Definition of Done
- [ ] 100% test coverage
- [ ] All tests passing
- [ ] Edge cases covered
```

---

## MDP-026: Cross-Browser Testing

**Type:** Technical  
**Priority:** P0  
**Complexity:** M  
**Story Points:** 8  
**Labels:** Type-Testing, Priority-P0, Sprint-7, MVP  
**Milestone:** Sprint 7

**Body:**

```
## Description
Test application across all major browsers and create browser compatibility matrix.

## Acceptance Criteria
- [ ] Chrome 120+ tested
- [ ] Firefox 121+ tested
- [ ] Safari 17+ tested
- [ ] Edge 120+ tested
- [ ] No layout issues
- [ ] All features working
- [ ] Performance acceptable
- [ ] Accessibility verified
- [ ] Bug report generated
- [ ] Compatibility matrix created

## Technical Notes
- Test on real devices/browsers if possible
- Use BrowserStack for remote testing
- Document any browser-specific issues
- Create compatibility matrix document

## Dependencies
- All Components Complete

## Definition of Done
- [ ] Tested on all major browsers
- [ ] Compatibility matrix created
- [ ] All tests passing
```

---

## MDP-027: Accessibility Audit (WCAG 2.1 AA)

**Type:** Technical  
**Priority:** P1  
**Complexity:** L  
**Story Points:** 8  
**Labels:** Type-Testing, Priority-P1, Sprint-7-8, MVP  
**Milestone:** Sprint 8

**Body:**

```
## Description
Perform comprehensive accessibility audit and fix any issues.

## Acceptance Criteria
- [ ] WCAG 2.1 AA compliance verified
- [ ] Automated audit tools pass
- [ ] Manual audit completed
- [ ] Screen reader tested
- [ ] Keyboard navigation tested
- [ ] Color contrast verified
- [ ] Font size accessible
- [ ] Resize text up to 200% works
- [ ] All issues fixed
- [ ] Audit report generated

## Technical Notes
- Use automated tools: Axe, Lighthouse, WAVE
- Manual testing with screen readers
- Test keyboard navigation
- Test with zoom/text resize

## Dependencies
- All Components Complete

## Definition of Done
- [ ] WCAG 2.1 AA compliance achieved
- [ ] Audit report generated
- [ ] All issues fixed
```

---

## MDP-028: Documentation - Component Documentation

**Type:** Documentation  
**Priority:** P1  
**Complexity:** M  
**Story Points:** 5  
**Labels:** Type-Documentation, Priority-P1, Sprint-8, MVP  
**Milestone:** Sprint 8

**Body:**

```
## Description
Create comprehensive component documentation with JSDoc comments and usage examples.

## Acceptance Criteria
- [ ] JSDoc comments for all components
- [ ] Props documented with types
- [ ] Usage examples provided
- [ ] Accessibility notes included
- [ ] Common patterns documented
- [ ] Edge cases documented
- [ ] Component API documented
- [ ] Usage guide created

## Technical Notes
- Use JSDoc format with TypeScript
- Include @param, @returns, @example
- Document all props with types

## Dependencies
- All Components Complete

## Definition of Done
- [ ] All components documented
- [ ] Usage guide created
- [ ] Examples provided
```

---

## MDP-029: Documentation - API Documentation

**Type:** Documentation  
**Priority:** P1  
**Complexity:** M  
**Story Points:** 5  
**Labels:** Type-Documentation, Priority-P1, Sprint-8, MVP  
**Milestone:** Sprint 8

**Body:**

```
## Description
Create comprehensive API documentation for utilities and hooks.

## Acceptance Criteria
- [ ] All utilities documented
- [ ] Function signatures documented
- [ ] Parameters documented
- [ ] Return types documented
- [ ] Examples provided
- [ ] Error cases documented
- [ ] Usage guide created
- [ ] API reference complete

## Technical Notes
- Document all exported functions
- Include usage examples
- Document error cases

## Dependencies
- All Utilities Complete

## Definition of Done
- [ ] All utilities documented
- [ ] API reference created
- [ ] Examples provided
```

---

## MDP-030: Setup Continuous Integration

**Type:** Technical  
**Priority:** P1  
**Complexity:** M  
**Story Points:** 8  
**Labels:** Type-Technical, Priority-P1, Sprint-8, MVP  
**Milestone:** Sprint 8

**Body:**

```
## Description
Set up GitHub Actions for automated testing and linting.

## Acceptance Criteria
- [ ] GitHub Actions workflow created
- [ ] Tests run on every push
- [ ] Linting checked on every push
- [ ] TypeScript compilation checked
- [ ] Build verification
- [ ] Workflow passes
- [ ] Failed checks block merge
- [ ] Workflow documented

## Technical Notes
- Create `.github/workflows/tests.yml`
- Run tests, linting, build
- Set required status checks on `main` branch

## Dependencies
- MDP-001: Project Setup

## Definition of Done
- [ ] GitHub Actions configured
- [ ] Workflow passing
- [ ] Status checks required
```

---

## MDP-031: Deploy to Vercel

**Type:** Technical  
**Priority:** P0  
**Complexity:** M  
**Story Points:** 5  
**Labels:** Type-Technical, Priority-P0, Sprint-8, MVP  
**Milestone:** Sprint 8

**Body:**

```
## Description
Deploy application to Vercel production environment.

## Acceptance Criteria
- [ ] Vercel project created
- [ ] GitHub integration configured
- [ ] Environment variables configured
- [ ] Custom domain configured
- [ ] SSL certificate active
- [ ] Auto-deploy on push enabled
- [ ] Deployment successful
- [ ] Production URL accessible

## Technical Notes
- Connect GitHub repo to Vercel
- Set environment variables
- Configure production settings
- Test deployment

## Dependencies
- MDP-030: CI/CD Setup

## Definition of Done
- [ ] Application deployed
- [ ] Production URL working
- [ ] Monitoring configured
```

---

## MDP-032: Performance Monitoring Setup

**Type:** Technical  
**Priority:** P1  
**Complexity:** M  
**Story Points:** 5  
**Labels:** Type-Technical, Priority-P1, Sprint-8, MVP  
**Milestone:** Sprint 8

**Body:**

```
## Description
Set up performance monitoring and Web Vitals tracking.

## Acceptance Criteria
- [ ] Vercel Analytics configured
- [ ] Web Vitals tracked
- [ ] Performance dashboard setup
- [ ] Alerts configured
- [ ] Benchmarks established
- [ ] Historical data collected
- [ ] Monitoring documented

## Technical Notes
- Enable Vercel Analytics
- Track Core Web Vitals
- Set performance budgets

## Dependencies
- MDP-031: Deploy to Vercel

## Definition of Done
- [ ] Monitoring active
- [ ] Dashboards configured
- [ ] Alerts working
```

---

## MDP-033: Beta Testing & Feedback Collection

**Type:** Testing  
**Priority:** P1  
**Complexity:** M  
**Story Points:** 5  
**Labels:** Type-Testing, Priority-P1, Sprint-9, MVP  
**Milestone:** Sprint 9

**Body:**

```
## Description
Set up beta testing with early users and collect feedback.

## Acceptance Criteria
- [ ] Beta testing group identified (5-10 users)
- [ ] Feedback form created
- [ ] Feedback collection system setup
- [ ] Initial feedback collected
- [ ] Critical issues logged
- [ ] User testing session completed
- [ ] Feedback documented
- [ ] Next iterations planned

## Technical Notes
- Create feedback form or survey
- Track user behavior (with permission)
- Document feedback for future releases

## Dependencies
- MDP-031: Deploy to Vercel

## Definition of Done
- [ ] Feedback collected
- [ ] Issues documented
- [ ] Iterations planned
```

---

## MDP-034: Bug Fixes & Iteration (Week 9)

**Type:** Maintenance  
**Priority:** P1  
**Complexity:** M  
**Story Points:** 8  
**Labels:** Type-Technical, Priority-P1, Sprint-9, MVP  
**Milestone:** Sprint 9

**Body:**

```
## Description
Fix bugs found during testing and iterate based on feedback.

## Acceptance Criteria
- [ ] All critical bugs fixed
- [ ] High-priority bugs fixed
- [ ] Medium-priority bugs triaged
- [ ] Performance optimizations applied
- [ ] User feedback addressed
- [ ] Code quality verified
- [ ] All tests passing
- [ ] Ready for public launch

## Technical Notes
- Prioritize bugs: critical → high → medium
- Track all issues in GitHub Issues
- Update documentation as needed

## Dependencies
- MDP-033: Beta Testing

## Definition of Done
- [ ] Critical bugs fixed
- [ ] Tests passing
- [ ] Ready for public launch
```

---

## MDP-035: MVP Launch Preparation

**Type:** Launch  
**Priority:** P0  
**Complexity:** M  
**Story Points:** 5  
**Labels:** Type-Launch, Priority-P0, Sprint-9, MVP  
**Milestone:** Sprint 9

**Body:**

```
## Description
Prepare for public launch with marketing materials and announcements.

## Acceptance Criteria
- [ ] Landing page created
- [ ] README updated for public
- [ ] Documentation complete
- [ ] Social media posts drafted
- [ ] Launch announcement prepared
- [ ] Email list prepared
- [ ] Legal/Privacy policy updated
- [ ] Launch checklist completed

## Technical Notes
- Create launch checklist
- Prepare social media content
- Update all documentation

## Dependencies
- MDP-034: Bug Fixes

## Definition of Done
- [ ] All launch materials ready
- [ ] Documentation complete
- [ ] Ready to announce
```

---

## How to Associate Issues with GitHub Project

After creating all issues, associate them with the "Web Toolkit" project:

1. Go to: https://github.com/users/Keertijanm/projects/9
2. Click "Add items" or "Add by ID"
3. Enter issue numbers: #1, #2, #3, etc.
4. Or use GitHub CLI:

```bash
# Add all issues to project
gh project item-add 9 --owner=Keertijanm --id-only << EOF
MDP-001
MDP-002
MDP-003
... (all 35)
EOF
```

---

## Next Steps

1. ✅ Create labels in GitHub
2. ✅ Create milestones in GitHub
3. ✅ Create 35 GitHub Issues (using template above or GitHub CLI)
4. ✅ Associate issues with "Web Toolkit" project
5. ✅ Start Sprint 1 with MDP-001 through MDP-007
6. ✅ Track progress using GitHub project board

---

## Quick Links

- **Repository:** https://github.com/Keertijanm/multi-device-preview
- **Issues:** https://github.com/Keertijanm/multi-device-preview/issues
- **Project:** https://github.com/users/Keertijanm/projects/9
- **TASKS.md:** https://github.com/Keertijanm/multi-device-preview/blob/main/docs/TASKS.md

---

**Document Version:** 1.0  
**Last Updated:** July 26, 2024  
**Created By:** Engineering Team
