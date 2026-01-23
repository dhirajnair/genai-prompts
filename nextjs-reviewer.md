# 🔍 Comprehensive Next.js Frontend Code Review Prompt

## Next.js Frontend Code Review & Analysis Request

Please perform a comprehensive code review of the following Next.js frontend code. Analyze the code across ALL categories below and provide a detailed report.

---

## 📋 Analysis Categories

### 1. Next.js Best Practices & Patterns
- Proper use of App Router vs Pages Router
- Server Components vs Client Components usage
- Correct file-based routing structure
- Proper use of layouts and templates
- Loading and error boundaries implementation
- Streaming and Suspense usage
- Route handlers vs API routes
- Middleware implementation
- next.config.js configuration
- Environment variable handling (.env.local)

### 2. Performance Optimization
- Image optimization (next/image usage)
- Font optimization (next/font)
- Code splitting and dynamic imports
- Bundle size optimization
- Lazy loading components
- Prefetching and preloading strategies
- Static vs Dynamic rendering choices
- Incremental Static Regeneration (ISR) usage
- Cache configuration and strategies
- Third-party script optimization (next/script)
- Unnecessary client-side JavaScript
- Large dependency imports
- Missing React.memo() for expensive renders
- Inefficient re-renders

### 3. SEO Optimization
- Metadata API usage (generateMetadata)
- Open Graph tags completeness
- Twitter Card meta tags
- Canonical URLs
- Structured data (JSON-LD)
- Sitemap.xml generation
- Robots.txt configuration
- Dynamic meta tags for pages
- Alt text on images
- Semantic HTML usage
- Heading hierarchy (h1, h2, h3)
- Internal linking structure
- Mobile-friendly viewport meta tags

### 4. Vercel Deployment Best Practices
- Edge Runtime vs Node.js Runtime usage
- Edge Functions implementation
- Middleware at the edge
- Image optimization via Vercel
- Analytics integration
- Web Vitals tracking
- Environment variables configuration
- Build optimization
- Output file tracing
- Serverless function size limits
- Cold start optimization
- Regional edge caching

### 5. React Best Practices
- Proper hook usage (useState, useEffect, etc.)
- Custom hooks implementation
- Avoiding unnecessary useEffect
- Dependencies array correctness
- Key props in lists
- Avoiding index as key
- PropTypes or TypeScript types
- Component composition patterns
- Avoiding prop drilling
- Context API usage
- State management efficiency
- Controlled vs uncontrolled components

### 6. TypeScript & Type Safety
- Proper type definitions
- Interface vs Type usage
- Generic types usage
- Any type avoidance
- Null/undefined handling
- Type guards implementation
- Utility types usage
- Strict mode compliance
- Import type optimization

### 7. Accessibility (a11y)
- ARIA labels and roles
- Keyboard navigation support
- Focus management
- Color contrast ratios
- Screen reader compatibility
- Alt text for images
- Form label associations
- Semantic HTML elements
- Skip navigation links
- Focus indicators visibility
- Error message accessibility
- Live regions for dynamic content

### 8. UI/UX Best Practices
- Responsive design implementation
- Mobile-first approach
- Touch target sizes (min 44x44px)
- Loading states and skeletons
- Error state handling
- Empty state designs
- Feedback on user actions
- Consistent spacing and typography
- Visual hierarchy clarity
- Button and link distinction
- Form validation UX
- Progressive disclosure
- Micro-interactions
- Animation performance (60fps)
- Dark mode support

### 9. Security Vulnerabilities
- XSS prevention (input sanitization)
- CSRF protection
- Content Security Policy (CSP)
- Secure headers configuration
- API key exposure in client code
- LocalStorage security considerations
- Cookie security (httpOnly, secure, sameSite)
- Dependency vulnerabilities
- Input validation on forms
- SQL injection in server actions
- Authentication implementation
- Authorization checks
- Rate limiting on API routes

### 10. State Management
- Global state necessity evaluation
- Redux/Zustand/Jotai proper usage
- Server state vs client state separation
- React Query/SWR implementation
- Optimistic updates
- Cache invalidation strategies
- State normalization
- Avoiding state duplication
- Local vs global state decisions

### 11. Data Fetching Patterns
- Server-side data fetching (fetch in Server Components)
- Client-side data fetching hooks
- Parallel data fetching
- Sequential vs parallel requests
- Error handling in data fetching
- Loading states
- Retry logic
- Request deduplication
- Stale-while-revalidate patterns
- Polling vs WebSocket decisions

### 12. CSS & Styling
- CSS Modules usage
- Tailwind CSS best practices
- Styled-components SSR setup
- CSS-in-JS performance
- Global styles organization
- Unused CSS elimination
- Critical CSS inlining
- CSS custom properties usage
- Responsive breakpoints consistency
- Animation performance (transform/opacity)
- Avoiding layout thrashing
- BEM or consistent naming convention

### 13. Code Quality & Maintainability
- Component size (< 300 lines)
- Function complexity
- Code duplication (DRY)
- Naming conventions consistency
- File/folder structure organization
- Separation of concerns
- Magic numbers/strings
- Comments and documentation
- Prop interfaces clarity
- Barrel exports usage
- Absolute vs relative imports

### 14. Error Handling & Logging
- Error boundaries implementation
- Try-catch in async operations
- User-friendly error messages
- Error logging strategy
- 404 page customization
- 500 error page
- Client-side error tracking
- API error handling
- Network failure handling
- Fallback UI components

### 15. Testing Readiness
- Testable component structure
- Props vs internal state
- Side effect isolation
- Data-testid attributes
- Mocking-friendly architecture
- Pure functions usage
- Component coupling level

### 16. Build & Bundle Optimization
- Tree shaking effectiveness
- Duplicate dependencies
- Large package imports
- Moment.js alternatives (date-fns, day.js)
- Lodash modular imports
- Polyfill necessity
- Source map configuration
- Compression settings

### 17. Forms & Validation
- Form library usage (React Hook Form, Formik)
- Client-side validation
- Server-side validation
- Error message display
- Accessible form errors
- Form submission states
- Optimistic UI updates
- File upload handling
- Multi-step form state management

### 18. Internationalization (i18n)
- next-intl or next-i18next setup
- Language routing strategy
- Translation key organization
- Dynamic content translation
- Date/number formatting
- RTL support
- Language switcher UX

---

## 📊 Output Format

For each issue found, provide:

```
### [SEVERITY: CRITICAL/HIGH/MEDIUM/LOW] Issue Title

**Category:** [Category Name]
**Location:** File path, Line X-Y or Component name
**Issue:** Clear description of the problem
**Impact:** User experience, performance, SEO, or security impact

**Current Code:**
```tsx
// problematic code snippet
```

**Suggested Fix:**
```tsx
// corrected code snippet
```

**Explanation:** Why this fix improves the code
**Resources:** [Relevant Next.js docs link or best practice article]
```

---

## 📝 Summary Section

After analysis, provide:

1. **Total Issues Found** by severity and category
2. **Top 5 Critical Issues** to address immediately
3. **Performance Score** (1-10 based on Core Web Vitals impact)
4. **SEO Score** (1-10)
5. **Accessibility Score** (1-10)
6. **Overall Code Health Score** (1-10)
7. **Recommended Priority Order** for fixes
8. **Quick Wins** (easy fixes with high impact)

---

## ✅ Confirmation & Fix Mode

After reviewing the analysis:

- Reply **"FIX ALL"** to apply all suggested fixes
- Reply **"FIX [issue numbers]"** to fix specific issues (e.g., "FIX 1,3,5")
- Reply **"EXPLAIN [issue number]"** for deeper explanation with examples
- Reply **"SKIP [issue numbers]"** to exclude from fixes
- Reply **"LIGHTHOUSE"** for Lighthouse audit considerations

I will then provide the complete corrected code with all approved fixes applied.

---

## 🎯 Code to Analyze

```tsx
// [PASTE YOUR NEXT.JS CODE HERE]
// Include: components, pages, app directory files, config files
```

**File Structure:**
```
/app
  /page.tsx
  /layout.tsx
/components
  /ComponentName.tsx
/lib
/public
next.config.js
```

---

## 🔧 Project Context (Required)

| Field | Value |
|-------|-------|
| **Next.js Version** | (e.g., 14.x, 15.x) |
| **Router Type** | App Router / Pages Router |
| **TypeScript** | Yes / No |
| **Styling Solution** | Tailwind / CSS Modules / Styled-components / Emotion |
| **State Management** | Redux / Zustand / Context / Server State only |
| **Deployment Platform** | Vercel / AWS / Other |
| **Target Audience** | Geographic region, device types |
| **Performance Budget** | LCP < 2.5s, FID < 100ms, CLS < 0.1 |
| **Specific Concerns** | SEO, Performance, Accessibility, Security |

---

## 💡 Usage Tips

1. **For single components:** Paste the component code with imports
2. **For pages:** Include the page component, layout, and related components
3. **For full review:** Provide file structure with all relevant files
4. **Include config:** Share next.config.js, tailwind.config.js, tsconfig.json
5. **Add context:** Mention user flows, critical paths, and business requirements
6. **Iterative review:** After fixes, request re-review for regression checking

---

## 🎯 Focus Areas (Optional - Select if needed)

- [ ] SEO optimization priority
- [ ] Performance optimization priority
- [ ] Accessibility compliance (WCAG 2.1 AA)
- [ ] Vercel deployment optimization
- [ ] Mobile-first responsive design
- [ ] Core Web Vitals improvement
- [ ] Security hardening
- [ ] Type safety improvements
