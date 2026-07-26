# Architecture Decision Records

**Project:** Multi Device Preview  
**Version:** 1.0  
**Last Updated:** July 26, 2024

---

## Table of Contents

1. [Technology Stack](#technology-stack)
2. [Component Architecture](#component-architecture)
3. [State Management](#state-management)
4. [Styling Approach](#styling-approach)
5. [Deployment Strategy](#deployment-strategy)
6. [Future Architecture Evolution](#future-architecture-evolution)

---

## Technology Stack

### Decision: Next.js 15 with App Router

**Chosen:** Next.js 15 (App Router)  
**Alternatives Considered:** Create React App, Remix, Astro

**Rationale:**
- ✅ **Server & Client Components:** Flexibility for future backend integration
- ✅ **Built-in Optimization:** Automatic code splitting, image optimization
- ✅ **Excellent DX:** Fast refresh, great tooling
- ✅ **Vercel Integration:** Seamless deployment
- ✅ **Growing Ecosystem:** Large community, excellent documentation
- ✅ **TypeScript First:** Strong type support

**Trade-offs:**
- ⚠️ Steeper learning curve vs Create React App
- ⚠️ Opinionated structure (but beneficial for teams)

**Migration Path:** None needed for MVP

---

### Decision: React 19 with TypeScript

**Chosen:** React 19 + TypeScript (Strict Mode)  
**Alternatives Considered:** Vue.js, Svelte

**Rationale:**
- ✅ **Industry Standard:** Largest ecosystem and community
- ✅ **Type Safety:** TypeScript prevents runtime errors
- ✅ **Performance:** Excellent performance characteristics
- ✅ **React 19 Features:** Use and Server Components
- ✅ **Developer Experience:** Excellent tooling and extensions

**TypeScript Strict Mode:**
- Enforced null/undefined checks
- Strict function typing
- Strict property initialization

---

### Decision: Tailwind CSS + shadcn/ui

**Chosen:** Tailwind CSS + shadcn/ui  
**Alternatives Considered:** CSS Modules, Styled Components, Material-UI

**Rationale:**
- ✅ **Utility-First:** Faster development, smaller bundle
- ✅ **shadcn/ui:** Accessible, customizable components
- ✅ **Dark Mode Ready:** Built-in dark mode support (Phase 2)
- ✅ **Performance:** No runtime CSS-in-JS overhead
- ✅ **Developer Experience:** Excellent IntelliSense support

**Bundle Impact:** ~30KB gzip (Tailwind + shadcn/ui)

---

### Decision: Deployment on Vercel

**Chosen:** Vercel  
**Alternatives Considered:** Netlify, AWS Amplify, Self-hosted

**Rationale:**
- ✅ **Next.js Optimization:** Vercel is built by Next.js creators
- ✅ **Edge Functions:** Perfect for future backend needs
- ✅ **Zero Configuration:** Automatic deployments
- ✅ **Performance:** Global CDN with automatic optimization
- ✅ **Analytics:** Built-in performance monitoring

**Cost:** Free tier sufficient for MVP

---

## Component Architecture

### Decision: Functional Components with Hooks

**Chosen:** Functional components with React Hooks  
**Alternatives Considered:** Class components, render props

**Rationale:**
- ✅ **Modern Standard:** Industry best practice (2024)
- ✅ **Code Reusability:** Custom hooks for logic sharing
- ✅ **Performance:** Hooks are optimized by React team
- ✅ **Simplicity:** Less boilerplate than class components

**Custom Hooks Strategy:**
```typescript
// Encapsulate business logic
- usePreviewPanels()      // Panel state management
- useWorkspace()          // Workspace save/load (Phase 2)
- useResponsive()         // Responsive layout
- useDevicePresets()      // Device configuration
```

---

### Decision: Composition over Inheritance

**Rationale:**
- ✅ More flexible component design
- ✅ Easier testing and reusability
- ✅ React philosophy
- ✅ Better TypeScript support

**Example:**
```typescript
// Good: Composition
<PreviewGrid>
  <PreviewPanel device="mobile" />
  <PreviewPanel device="tablet" />
  <PreviewPanel device="desktop" />
</PreviewGrid>

// Avoid: Inheritance
class PreviewPanel extends BasePanel { }
```

---

### Decision: Server vs Client Components (Next.js)

**Rule:**
- **Server Components:** Layout, metadata, data fetching (Phase 2)
- **Client Components:** Interactive elements (buttons, inputs, iframes)
- **Mark as 'use client':** Only when necessary

**Rationale:**
- ✅ Better performance (less JavaScript sent to client)
- ✅ Security (sensitive logic stays on server)
- ✅ Reduced bundle size

---

## State Management

### Decision: React Hooks (MVP) → Context API (Phase 2)

**MVP Phase:**
- Use React hooks for local component state
- Props drilling for cross-component communication
- `useReducer` for complex state

**Phase 2 Migration:**
- Implement Context API for global state
- Consider Zustand if Context proves insufficient

**Why Not Redux/MobX?**
- Overkill for current complexity
- Extra boilerplate
- Slower initial development
- Can be added later if needed

**Example State Structure:**

```typescript
interface PreviewPanel {
  id: string;
  url: string;
  device: 'mobile' | 'tablet' | 'desktop';
  isLoading: boolean;
  error: string | null;
  isVisible: boolean;
}

interface AppState {
  panels: PreviewPanel[];
  activePanel: string | null;
  workspace: {
    name: string;
    savedAt: Date;
  };
}
```

---

### Decision: LocalStorage for Persistence (MVP)

**MVP Phase:**
- Use browser LocalStorage for workspace persistence
- No backend required
- Works entirely offline

**Phase 2 Migration:**
- Move to Supabase PostgreSQL
- Implement user authentication
- Enable cross-device synchronization

**LocalStorage Schema:**

```typescript
interface StoredWorkspace {
  id: string;
  name: string;
  panels: PreviewPanel[];
  createdAt: timestamp;
  updatedAt: timestamp;
}

// Key: 'mdp_workspace_{id}'
localStorage.setItem('mdp_workspace_abc123', JSON.stringify(workspace));
```

---

## Styling Approach

### Decision: Tailwind CSS (Utility-First)

**Why Tailwind over CSS Modules?**
- ✅ Faster development velocity
- ✅ Consistent design tokens
- ✅ Excellent dark mode support
- ✅ Built-in responsive utilities
- ✅ Smaller bundle with tree-shaking

**Tailwind Configuration:**

```javascript
// tailwind.config.js
module.exports = {
  content: [
    './src/pages/**/*.{js,ts,jsx,tsx}',
    './src/components/**/*.{js,ts,jsx,tsx}',
  ],
  theme: {
    extend: {
      colors: {
        // Custom colors for Multi Device Preview
      },
    },
  },
  darkMode: 'class', // Prepared for Phase 2
  plugins: [],
};
```

### Decision: shadcn/ui for Component Library

**Why shadcn/ui?**
- ✅ Copy-paste component library (customizable)
- ✅ Built on Radix UI (accessible)
- ✅ Uses Tailwind CSS
- ✅ No vendor lock-in
- ✅ Perfect for startups/open-source

**Components to Use:**
- Button
- Input
- Select/Dropdown
- Dialog/Modal (Phase 2)
- Tabs (Phase 2)
- Toast notifications (Phase 2)

---

## Deployment Strategy

### Decision: GitHub + Vercel for CI/CD

**Current Setup (MVP):**
- GitHub for version control
- Vercel for automatic deployments
- Deploy on every push to `main`

**Future Setup (Phase 2):**
- Add GitHub Actions for testing
- Implement pre-deployment checks
- Add staging environment

**Deployment Process:**

```
Push to main
    ↓
GitHub webhook
    ↓
Vercel receives event
    ↓
Vercel builds Next.js app
    ↓
Vercel runs tests
    ↓
Deploy to production (if tests pass)
    ↓
Update production URL
    ↓
Invalidate CDN cache
```

---

### Decision: Environment Configuration

**Environment Variables:**

```bash
# .env.local (development)
NEXT_PUBLIC_API_URL=http://localhost:3000

# .env.production
NEXT_PUBLIC_API_URL=https://multi-device-preview.vercel.app
```

**Why Separate?**
- Different URLs for dev/prod
- Analytics tracking
- Feature flags (Phase 2)

---

## Future Architecture Evolution

### Phase 2: Backend Services

**Add Next.js API Routes:**

```typescript
// app/api/workspaces/route.ts
export async function GET(request: Request) {
  // Fetch user workspaces from Supabase
}

export async function POST(request: Request) {
  // Create new workspace
}
```

**Integrate Supabase:**

```typescript
import { createClient } from '@supabase/supabase-js';

const supabase = createClient(
  process.env.NEXT_PUBLIC_SUPABASE_URL,
  process.env.SUPABASE_SERVICE_ROLE_KEY
);
```

---

### Phase 3: Microservices Architecture

**Separate Services:**
- Performance analyzer (Node.js)
- Screenshot service (Puppeteer/Playwright)
- Analytics pipeline (Node.js)

**Communication:**
- RESTful APIs between services
- Message queue for async tasks (optional)
- Shared logging (Vercel Analytics)

---

### Phase 4: Machine Learning Integration

**Future Enhancements:**
- Automated visual regression detection
- Design pattern recognition
- Performance prediction
- A/B testing recommendations

---

## Decision Making Framework

### For Future Architecture Decisions

Use this framework to evaluate new technologies:

| Criteria | Weight | Considerations |
|----------|--------|-----------------|
| Performance | 25% | Bundle size, load time, runtime |
| Developer Experience | 20% | Learning curve, documentation, tooling |
| Community & Support | 20% | GitHub stars, npm downloads, Stack Overflow |
| Maintenance Burden | 15% | Updates, security patches, breaking changes |
| Cost | 10% | Licensing, hosting, infrastructure |
| Scalability | 10% | Can it grow with us? |

---

## Architecture Principles

1. **Simplicity First** – Choose simple solutions until complexity justifies a change
2. **Performance by Default** – Optimize for performance in design phase
3. **TypeScript Everywhere** – Type safety reduces bugs
4. **Accessibility Always** – WCAG 2.1 AA compliance from day one
5. **Open Source Friendly** – Minimal external dependencies
6. **Future Proof** – Modular design allows easy upgrades

---

## Document Metadata

**Author:** Technical Architecture Team  
**Version Control:** GitHub  
**Last Review:** July 26, 2024  
**Next Review:** September 26, 2024  
**Decision Framework Updated:** July 26, 2024
