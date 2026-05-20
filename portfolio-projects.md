# Portfolio Projects

## Numeral Studio Monorepo Template | Numeral Studio | Mar 2026 - May 2026 (proposal, pending adoption)

**Role:** Senior Software Engineer (proposal author).
**Status:** Proposal-in-progress. Build complete; team adoption, outcome metrics, and refinements pending. Status note carried because the template's value is conditional on the team actually using it.

### Origin

The template pulls from patterns we've already used across client projects, especially setup conventions that have worked. It is not trying to be prescriptive. The goal is to start a conversation about how to make our default project setup stronger, faster to spin up, and more reliable. Part of the thinking: this could help us move faster on pitches and prototypes, and give us a cleaner path from prototype to production-quality code. If we standardise the repetitive setup, add sensible defaults, and introduce quality gates early, we save time at the start of projects and have more confidence in what we ship.

Some pieces I feel fairly strongly about (better automation, stronger testing and default quality checks, codebase legibility). Other pieces are open questions, especially UI primitives, package managers, logging conventions, optional libraries, and how much to bake in vs keep minimal per project.

### Project Overview

A monorepo template for new client engagements. Default stack, opt-in integrations, CI gates and accessibility tests in place from day one. Engineers ramp once on the conventions, not per project.

### Key Contributions

- Set the default stack (Next.js 15, React 19, TypeScript 5, Tailwind 4, Chakra UI) so every new project starts from the same foundation.
- Designed the monorepo structure with Turborepo and npm workspaces. One lockfile, clear app and package boundaries.
- Built the quality-gate split: pre-commit autofix only; CI lint / test / e2e are advisory; only type-check and build can block a PR. The balance came from watching teams lose velocity to over-strict gates.
- Migrated the component library from shadcn primitives to Chakra UI (driven by team preference): 30+ components rebuilt with Storybook stories and axe-core tests per component.
- Structured the integration-branch pattern: five opt-in feature branches (Prisma, Kinde auth, Sanity, Resend, GSAP) so teams pull in what they need without polluting the base.
- Wrote AGENTS.md and CLAUDE.md so the template ships with pattern-driven onboarding for humans and agents, not tribal knowledge.

### Technical Implementation Details

- **Stack:** Next.js 15, React 19, TypeScript 5, Tailwind 4 + Chakra UI, Vitest, Playwright, Storybook, Turborepo, npm workspaces.
- **CI breadth:** 18 GitHub Actions workflows covering lint, type-check, test, e2e (4 parallel shards + visual snapshots), accessibility (axe-core), CodeQL, lighthouse budgets, bundle analysis, image optimisation, release, stale cleanup, dependabot auto-merge, rebase integrations.
- **Coverage threshold:** raised mid-build from 60% to 95% as an intentional team call.
- **Deployment:** dual-branch model with `deploy/production` and `deploy/pre-production` as staged release targets.
- **Build scope:** 107 commits over 54 days.

### Pending Validation

- Estimated ~30% reduction in project initiation time vs the prior kickoff cadence. **Aspirational, not yet measured against a real client engagement.** True outcome metrics arrive once new projects launch on the template.
- Pending team adoption + feedback. Outcomes (kickoff time, defect rate, contractor onboarding cost) become measurable after N projects ship on it.

### Open Questions in the Proposal

- UI primitives (Chakra is the current pick; team preference confirmed, broader fit-for-purpose review still pending)
- Package manager choice (npm currently; alternatives under consideration)
- Logging conventions
- How much to bake in vs keep minimal per project

### Learning and Development

- The quality-gate split was the most interesting design call. Most templates default to blocking on everything. Advisory CI on lint / unit / e2e keeps the feedback loop fast while still surfacing issues. Teams fix them when they are ready, not when they are blocked mid-PR.
- Framing the work as a conversation-starter rather than a prescription mattered. The template lands as something the team can shape, not something handed down.

---

## Price → Impact | Habitual Genesis | May 2026

**Problem Statement / Challenge:**

-   Online shopping is a moment when people are about to spend money intentionally. It's also the moment when "I could donate that instead" rarely happens, because the friction is high: open a new tab, look up charity options, calculate equivalents, switch context, lose the intent. I wanted to put a donation option inside the shopping flow itself, so the alternative is visible at the moment a purchase is about to happen.

**Scope of Work:**

-   Built a Chrome MV3 extension that detects prices on shopping pages and offers two donation interventions in place: **divert** (point a planned purchase at a charity equivalent instead), and **round-up** (push the cart total up to the next round number and donate the difference to a high-impact charity). Companion web app and bookmarklet ship from the same monorepo for installs that don't need the extension.

**Team Size and Collaboration:**

-   Solo project. MIT licensed and open to contributions.

**Tools and Environment:**

-   TypeScript, Chrome MV3 manifest, MutationObserver-based content script, Bun workspaces, Vitest, GitHub Actions CI. JSON-encoded charity reference data sourced from GiveWell cost-per-outcome estimates. Next.js for the companion web app.

**Key Contributions:**

-   Shipped the Chrome MV3 extension: a manifest plus content script that detects prices as a page renders (including DOM mutations from infinite scroll and dynamic results) and presents both donation interventions inline.
-   Built `packages/charities`: a typed reference dataset of charity cost-per-outcome figures with an `asOf` field, a static FX-rate layer, and pure functions for parsing prices in any currency and converting to outcome units. 62 tests across two workspaces.
-   Designed the two intervention paths (divert and round-up) so the friction-cost is one click rather than a workflow context-switch. The donation moment happens inside the shopping moment.
-   Shipped the companion web converter and bookmarklet from the same codebase, so the same charity data and conversion logic backs every shell.
-   CI runs lint, typecheck, test, and build on every push to `main` and every PR.

**Metrics and KPIs:**

-   Shipped end-to-end in a single weekend pass (51 commits in one day). Extension, web app, and bookmarklet all live and installable.
-   169 tests across the extension, web app, and charity-data workspaces; full type coverage; green CI on every push and PR.
-   Four user-facing surfaces in the extension: in-page donation pill, popup jar with threshold picker, options page, and history table.
-   Amazon ships as the first detector; Etsy and Shopify are next on the roadmap.

**Learning and Development:**

-   The interesting design problem wasn't the price detection. It was understanding that "donate to charity instead" already loses to "buy the thing" almost every time, because the donate option lives in a completely different context. Bringing the donate option into the shopping context — same page, same moment, one click — is what changes the choice architecture. The technical work is in service of that.
-   The MV3 content-security-policy constraints reinforced this: no remote loads, single self-contained bundle, MutationObserver for DOM updates. That separation paid off when the same data layer was reused in the web app and the bookmarklet.

**Repository:**

-   <https://github.com/olitreadwell/price-to-impact>

---

## NZ Hardware/Software Systems Company: Marketing & Case-Study Site | Numeral Studio | Mar 2026 - May 2026

**Role:** Senior Front-end Software Engineer, end-to-end build lead.
**Status:** Delivered for launch (weeks from going live as of May 2026).

### Project Overview

Marketing and case-study website for an NZ hardware and software systems company. The site is the company's main pitch surface for new business, covering a portfolio of client work anonymised by industry and size (transport, retail, hospitality). Built to communicate competence across sectors without feeling templated.

### Role on the Engagement

Led the build end-to-end after initial setup: scoping, client comms, technical direction, delivery cadence, and QA. Worked with a contracted PM and designer (who brought us in), the studio lead (strategy, initial calls, animation contributions, ongoing guidance), and a senior dev who handled the initial setup and infrastructure.

### Key Contributions

- 231 commits across 57 days, around 37% of total project commits.
- **Fluid responsive system:** nav drawer that scales continuously from 820 to 1800px instead of step-changing at fixed breakpoints. Smoother visual continuity across viewport sizes.
- **Hero refactor:** moved from a fixed-position plus spacer pattern to a scroll-driven sticky hero with time-driven word animation. Simpler scroll behaviour, cleaner scroll restoration.
- **Case-study image grid systems:** designed varied grid layouts (6-6+8-3, 3-8) so each anonymised case study carries distinct visual weight.
- **Geometry as testable:** added pure utility functions (`computeAnchorY`, `pickClosestIndex`) with unit tests so layout math can be reasoned about independently of render.
- **Nav-drawer e2e suite:** roughly 280 lines covering scroll-lock, hash-scroll, and scroll-restore behaviour.

### Technical Implementation Details

- **Frontend:** Next.js 15, React 19, TypeScript 5, Tailwind 4 + Sass, GSAP for animation, Zustand for state.
- **Testing:** Vitest for layout-math utilities; Playwright e2e for nav-drawer and case-study hero behaviour.
- **Tooling:** husky + lint-staged on TS / TSX + JSON / MD; pre-commit hook discipline.

### Decisions and Tradeoffs

- Scroll-driven sticky hero over fixed-position plus spacer: cleaner scroll behaviour at the cost of a bit more component state.
- ~60 commits of layout polish over feature breadth: quality bar over scope; the site needed to feel hand-tuned.
- Fluid responsive over breakpoint-driven: smoother visual continuity, more math in the layout helpers (which is why the pure-function utilities earned unit tests).
- GSAP over CSS-only animation: bundle size and runtime dependency cost in exchange for a richer animation toolchain.

### Impact

The site is the company's main pitch surface. Quality of presentation maps directly to whether prospects believe the company can deliver what the case studies claim. Delivered for an imminent launch; post-launch metrics (traffic, inquiry rate, sales-pipeline impact) follow go-live.

---

## Live-Event Stage Display System for a Fortune 2000 Enterprise Conference | Numeral Studio | Apr 2026 - May 2026

**Role:** Senior Front-end Software Engineer (team contributor).
**Status:** Shipped (ran live at the event).

### Project Overview

Multi-screen LED stage display system for a single live moment at a Fortune 2000 enterprise conference. Three synchronised screens consume real-time game and MC events via webhooks and render a leaderboard, branded ticker / stinger, and live progress tracker. The venue operator runs three browser windows (one per screen) against a shared in-memory runtime. Delivered end-to-end in 18 calendar days. Ran live at the event.

### Role on the Engagement

Team contribution rather than lead. Jumped in on a small team and pulled off large frontend chunks end-to-end. Worked with a contracted PM and a senior fullstack dev (setup, infra, backend, initial frontend, review-merge-deploy on my PRs), and the studio lead for strategy and client comms.

### Key Contributions

- 53 commits in 18 calendar days.
- **Reveal-orchestration engine:** the primary component driving choreographed reveals across all three screens.
- **Stage-geometry math:** elliptical arcs for variable row counts, S-curve stage flow, bus alignment for connectors between screen elements. Geometry primitives in TypeScript that adapt to variable inputs without manual rework per layout.
- **Cross-screen animation sequencing:** shared 0.9s odometer baseline so reveals stay visually coherent across LEDs. OdometerNumber, meter fill, signal bar reveals.
- **Polish pass:** backdrop blurs, stroke unification, connector colour coherence, robot-ASCII video background luminance.
- **CI on day one:** pre-push build hook and GitHub Actions workflow added at the start of the build.

### Technical Implementation Details

- **Frontend:** Next.js 16, React 19, TypeScript 5, Three.js + React Three Fiber (ASCII video backgrounds), GSAP for timeline choreography, Base UI React for accessible primitives, Tailwind 4.
- **Multi-screen sync:** shared in-memory runtime against three browser windows (one per screen), real-time webhook ingest.
- **Testing:** unit tests across draft-card cache, leaderboard data, transition keys, and post-clear audio despite the short build cycle.

### Decisions and Tradeoffs

- Speed vs UI quality vs scope balanced against a hard event date. No possibility of a second chance to ship.
- In-memory shared runtime over a heavier database-backed model: lower complexity for a single-event run.
- TypeScript geometry primitives over hand-tuned SVGs per layout: more code up front in exchange for layouts that adapt to variable inputs without manual rework.

### Impact

A Fortune 2000 enterprise client needed a single live moment to land in front of a large conference audience. The team delivered it on a fixed date with no extension possible. Quality of presentation in front of the audience was the bar.

---

## NZ Tech Events Community Contributions | Habitual Genesis | 2026 (ongoing)

**Problem Statement / Challenge:**

- `nz-tech-events` is a public Ruby on Rails app that powers a community-run calendar of NZ tech events. It's a resource a lot of the local tech community relies on. The maintainer was the bottleneck, and parts of the app could be hardened without changing how end users experienced it.

**Scope of Work:**

- Spotted an opportunity to improve a community resource popular with the local tech community and contributed back across a number of areas: developer experience, search reach, distribution, reliability, and project hygiene.

**Team Size and Collaboration:**

- Open-source contributor. Worked with the maintainer through PR review.

**Tools and Environment:**

- Ruby on Rails, RSpec, GitHub Actions, JSON-LD structured data, Atom / RSS feeds.

**Key Contributions:**

- Added GitHub Actions CI with quality gates so incoming PRs get linted, type-checked, and tested before merge.
- Added JSON-LD structured data to event pages so they show up better in search results and shareable previews.
- Added Atom and RSS feeds for upcoming events so the community can subscribe instead of polling the site.
- Extracted a shared `HasRegion` model concern across three models, removing duplicated region-handling logic.
- Added test coverage for the password-reset flow and weekly-digest job, both of which had previously gone untested.
- Added CONTRIBUTING.md and an MIT LICENSE so future contributors land on a clear contributing flow.

**Metrics and KPIs:**

- Eight PRs merged so far, with more in flight. Coverage and developer-experience improvements compound: every future PR runs through the gates added in this work.

**Learning and Development:**

- The pattern that works for outside-contributor OSS work: start with the quality gates and the docs (so future contributors have an easier path), then the tests, then the features. Maintainers say yes faster to PRs that come with tests.

**Repository:**

- <https://github.com/ro-savage/nz-tech-events>

---

## Commercial Reporting and Compliance Electron App | Numeral Studio | Nov 2025 - Jan 2026

### Role & Scope

- **Role:** Senior Front-end Software Engineer working in React/Electron/TypeScript; collaborated with design/PM and backend.
- **Focus areas:** Complex form UX, validation, accessibility, shared UI components, date/time correctness, testing and tooling improvements.
- **Team mode:** Iterative delivery with code reviews, small refactors, and test-first validation for risky changes.
- **Collaboration style:** Pairing on design tweaks, async reviews for velocity, and short feedback loops with stakeholders.
- **Delivery cadence:** Frequent, small UI refinements to de-risk changes, backed by tests and visual checks.
- **Environment:** Desktop-style front end with occasional offline/online needs, emphasizing predictable state management.
- **Guardrails:** Treated compliance/adaptability as constraints; prioritized accessibility, clarity, and minimal surprise for users.

### Core Contributions (High-Level)

- Built and refined reusable inputs (date picker, selects, form inputs) to standardize UX and reduce defects.
- Overhauled complex form flows: clearer validation, better spacing/states, more accessible icons and controls.
- Strengthened quality gates: added targeted unit/integration tests around forms and formatting; enforced lint/type health.
- Polished accessibility: consistent icon wrapping with accessibility helpers, keyboard navigation, clearer hover/disabled states.
- Hardened edge cases: normalized empty/default values, reduced prop surface where redundant, and improved fallback states.
- Documented behavior in code where non-obvious (e.g., formatting expectations, accessibility wrappers).
- Aligned component variants (primary/secondary/ghost) to reduce bespoke styling and improve predictability.
- Tuned input ergonomics (focus order, spacing, inline help) for dense forms to reduce cognitive load during data entry.
- Increased reliability with defensive defaults for missing/partial data to prevent UI breakage when backend responses vary.

### Challenge → Action → Result

1. **Validation clarity & form UX**
   - **Challenge:** Inconsistent form layouts and unclear guidance slowed data entry.
   - **Action:** Refined form layouts, spacing, and validation messaging; added tab status indicators and custom option labels for selectors.
   - **Result:** Faster data entry and fewer user mistakes due to clearer guidance and consistent dropdown behavior.
   - **Extra:** Filtered out already-selected options and improved empty-state messaging for selects to guide users.
2. **Accessibility & component polish**
   - **Challenge:** Inconsistent and inaccessible interactive components.
   - **Action:** Standardized icon components with accessibility wrappers; improved disabled/hover states; aligned sizes across navigation elements.
   - **Result:** More accessible UI with predictable interaction states; simpler theming and maintenance across shared components.
   - **Extra:** Normalized focus rings and keyboard navigation paths for primary actions and dropdowns.
3. **Testing & reliability**
   - **Challenge:** UI regressions after changes and lack of confidence in edge cases.
   - **Action:** Expanded form and input tests (including date/time formatting and select behaviors) to lock in expected UX; mocked edge cases to prevent regressions.
   - **Result:** Higher confidence shipping UI changes; quicker detection of breakage after refactors or dependency updates.
   - **Extra:** Added coverage for validation edge cases (empty, partial, and read-only states) to prevent silent breakage.
4. **Tooling & stability**
   - **Challenge:** Difficult dependency upgrades and unclear debugging.
   - **Action:** Updated dependency sets and project configs while keeping lint/type/test suites green; standardized logging format for easier debugging.
   - **Result:** Smoother upgrades with fewer surprises; clearer diagnostics when issues arise.
   - **Extra:** Simplified import paths and module resolution to reduce merge conflicts and onboarding friction.

---

## Conference Website Platform Modernisation | Numeral Studio | Mar 2025 - Jan 2026

**Company:** Numeral Studio  
**Project:** Conference website platform  
**Role:** Senior Front-end Software Engineer
**Duration:** March 2025 - Present (Multiple Engagements)

### Project Overview

A comprehensive conference management platform providing speaker profiles, session schedules, sponsorship information, and attendee engagement features. The platform serves as the primary digital hub for conference participants and organizers.

### Key Contributions

#### Advanced Filtering & Search System

- Developed a comprehensive FilterList component with consistent UX patterns for speakers, sponsors, and sessions.
- Implemented mobile-first filter panels with responsive height adjustments.
- Created consistent toggle behavior, button interactions, and standardized tag formatting across implementations.

#### Large List Component Architecture

- Built scalable components for displaying conference data with reusable LargeListHeader and sponsor-specific layouts.
- Enhanced mobile display of large datasets with responsive layouts and type-safe props.

#### Rule Bar Navigation System

- Developed a reusable RuleBar navigation component with multiple styling variants, ChildLink systems, and hover interactions.
- Integrated Storybook documentation to improve component discoverability.

#### Comprehensive Testing Infrastructure

- Established Jest + React Testing Library coverage for critical UI components.
- Created GitHub Actions workflows for automated code coverage and regression prevention.

#### Component Documentation & Standards

- Enhanced component documentation with JSDoc, Storybook, and clear TypeScript standards.
- Implemented ESLint rules and formatting standards to maintain quality.

### Technical Implementation Details

- **Frontend:** Next.js (React + TypeScript)
- **Styling:** SCSS component architecture
- **CMS:** Sanity with PortableText support
- **Animation:** GSAP for smooth transitions
- **Testing:** Jest, React Testing Library, GitHub Actions

### Impact & Results

- **Component Reusability:** 70% reduction in code duplication through unified FilterList system.
- **Development Velocity:** Faster feature delivery through standardized patterns and documentation.
- **User Experience:** Consistent interactions, improved mobile performance, and better accessibility.
- **System Architecture:** Scalable, type-safe components supporting future conference websites.

---

## HR Case-Management Platform | Numeral Studio | Jul 2025 - Oct 2025

**Company:** Numeral Studio  
**Project:** HR case-management platform  
**Role:** Senior Front-end Software Engineer
**Duration:** July 2025 - October 2025  


### Project Overview

An HR case management platform providing privacy-compliant case tracking, staff assignments, and reporting workflows for Human Resources organizations.

### Key Contributions

#### Case Management System Architecture

- Added preferred case owner fields and improved schemas to enable precise staff assignments.
- Enhanced report routing to exclude self-reports and protect privacy.
- Built comprehensive form hooks (`useReportForm`) with validation and error handling.

#### UI Component Development

- Implemented InfoBox components, improved modals, and enhanced form components with better loading states.
- Delivered dynamic HR user options for staff reporting workflows.

#### Testing Infrastructure

- Implemented Cypress E2E tests for Human Resources workflows and extensive unit testing for utilities and components.
- Established testing configurations for privacy, compliance, and regression prevention.

#### Code Quality & System Architecture

- Refactored permission systems and staff modules for secure, scalable access control.
- Enforced schema validation, documentation standards, and consistent development patterns.

### Technical Implementation Details

- **Frontend:** React/TypeScript with Storybook
- **Backend:** Node.js/Express with Prisma ORM
- **Database:** Human Resources-compliant schema with audit trails
- **Testing:** Cypress E2E, Jest unit tests
- **Tooling:** ESLint, Prettier, automated checks

### Impact & Results

- Comprehensive schema validation preventing data corruption.
- Enhanced user experience via improved loading states and error handling.
- Stronger security through refined permission systems and audit trails.

---

## Mobile Experience Platform | Numeral Studio | 2025 (Multiple Engagements)

**Company:** Numeral Studio  
**Project:** Mobile experience platform  
**Role:** Senior Front-end Software Engineer
**Duration:** Multiple engagement periods, 2025  

### Project Overview

A global mobile experience platform with localized experiences, interactive demos, and performance-sensitive mobile UI across multiple international markets.

### Key Contributions

#### Image Asset Optimization & Performance

- Replaced PNG assets with WebP, created optimization scripts, and enhanced build configurations for faster load times.
- Added tooling to resize images, process only changed assets, and streamline the asset pipeline.

#### International Localization & Translation Management

- Updated Korean translations, added new phrase keys, and ensured cross-market consistency for English/Korean regions.
- Enhanced tutorial content and wearable-device localization to support market expansion.

#### Mobile Search & Keyboard Interaction

- Fixed iOS-specific search issues on iPhone 15/16, improved Android keyboard handling, and created responsive search header positioning.
- Delivered unified keyboard handling for cross-platform support.

#### Code Quality & Architecture

- Documented the DashboardSearch component, removed debugging artifacts, and added unit tests for UI components.
- Optimized webpack configuration for fonts and assets to maintain performance.

### Technical Implementation Details

- **Frontend:** React/Next.js with TypeScript
- **Styling:** SCSS, mobile-first responsive design
- **Asset Management:** WebP conversion, automated scripts, webpack optimizations
- **Testing:** Jest unit and component tests

### Impact & Results

- Significant load-time reductions via WebP conversion and optimized asset handling.
- Consistent localized experiences across key international markets.
- Enhanced cross-platform mobile interactions with reliable keyboard and search experiences.

---

## Engineering Team Capacity Building | Enterprise engineering teams across the USA | 2015 - 2023

**Problem Statement / Challenge:**

- Engineering organisations across the USA needed to grow capacity faster than they could hire. The work was to build that capacity through structured training, ongoing mentoring, and pull-request-level coaching of working engineers, covering both hard skills (React, Python, Rails, accessibility, CI/CD) and the soft skills that determine whether new capacity actually translates to team throughput.

**Scope of Work:**

- Designed engagements, ran them, and embedded with engineering teams. Wrote and graded real assessments rather than relying on attendance. Reviewed and gave feedback on hundreds of pull requests as part of structured mentoring engagements. Worked with engineering teams at Fortune 100 companies, including roughly 400 engineers at Amazon.

**Team Size and Collaboration:**

- Partnered directly with engineering managers at the client companies to scope training to what their teams needed. Worked alongside other instructors and curriculum developers to keep materials aligned with how engineering teams actually ship.

**Tools and Environment:**

- JavaScript / TypeScript, React, Node.js, Python, Flask, Ruby on Rails, PostgreSQL, CI/CD, web accessibility (WCAG, ARIA), Agile delivery patterns, code-review-driven mentorship.

**Key Contributions:**

- Built engineering capacity for teams at enterprise companies across the USA through structured technical training (hard skills, soft skills, accessibility, ship-cadence patterns) backed by real assessments and outcome metrics.
- Ran ongoing 1:1 and small-group mentoring for working engineers, focused on the soft skills that turn individual capacity into team throughput: code review etiquette, scoping work, navigating ambiguity, communicating trade-offs.
- Gave feedback on hundreds of pull requests as part of structured mentoring engagements, directly shaping how engineers ramped on new stacks and patterns.
- Established inclusive-design and accessibility practice within an engineering organisation, weaving those practices through the work so every team shipped accessible UIs by default.

**Metrics and KPIs:**

- Roughly **400 engineers at Amazon** went through training that I designed and delivered, with throughput increases reported by their engineering managers.
- Hundreds of pull-request reviews directly shaped how engineers ramped on new stacks and shipped production work.
- Programs were backed by real assessments and engineering-manager-level outcome metrics, not attendance.

**Learning and Development:**

- This work made it clear that the highest-leverage capacity-building intervention is not a lecture. It's specific code-review feedback on real work, repeated across enough touch-points that patterns get internalised. That belief shapes how I mentor engineers I work with day-to-day now.

**Stakeholders and Impact:**

- Engineering managers at client companies (Amazon notable among them) reported measurable increases in throughput and code quality from teams that went through the programs. The pattern across all engagements: train, then mentor through the first three or four real PRs, then watch the team get faster.

---

## Read the Room Education Website Enhancement | Habitual Genesis | Pro Bono | 2021-Present

**Problem Statement/Challenge:**

- Read the Room Education, a non-profit organisation, needed website enhancements to engage their audience and promote educational programs. The challenge was to improve the site’s mobile responsiveness and implement a mechanism to grow their mailing list.

**Scope of Work:**

- Assessed the existing website and implemented design and content enhancements focused on user engagement and accessibility. Integrated Mailchimp to capture visitor information and grow the mailing list.

**Team Size and Collaboration:**

- Worked directly with the organisation’s leadership team to align website improvements with organisational goals.

**Tools and Environment:**

- Squarespace, Mailchimp, Canva.

**Key Contributions:**

- Integrated Mailchimp for newsletter signups by embedding a custom form, which grew the mailing list by **40%**.
- Optimised the mobile layout using responsive design techniques, increasing mobile engagement by **25%**.
- Reorganised the content structure to highlight educational programs, making it easier for visitors to find relevant information quickly.

**Metrics and KPIs:**

- Increased user engagement by **25%** within three months of launch.
- Grew the mailing list by **40%** in the first quarter after the website enhancements.

**Learning and Development:**

- This project reinforced my skills in responsive design and integrating third-party services like Mailchimp into a content management system.

**Post-Launch Maintenance:**

- Provided post-launch support for two months, monitoring site performance and making adjustments based on user feedback.

**Stakeholders and Impact:**

- The leadership team reported a significant improvement in audience engagement and highlighted the mailing list growth as key to their outreach efforts.

---

## Slashtag Website Development | Habitual Genesis | 2021

**Problem Statement/Challenge:**

- Award-winning author Jon Cohn needed a mobile-first, low-maintenance website to promote his book _Slashtag_ and increase sales. The challenge was to create a responsive, user-friendly site that could be managed independently without ongoing technical support.

**Scope of Work:**

- Handled the full development of the website, working closely with the client to design and implement a mobile-first solution that aligned with the author's vision and marketing goals.

**Team Size and Collaboration:**

- This was a solo project where I managed all phases of development, from design through deployment.

**Tools and Environment:**

- Bootstrap, HTML5, CSS3, JavaScript, GitHub Pages, Git.

**Key Contributions:**

- Developed a fully responsive, mobile-first website using Bootstrap, which improved book sales by **20%** in the first month.

**Metrics and KPIs:**

- Increased book sales by **10%** within the first three months.
- Improved user engagement by **15%**, as indicated by website interaction metrics.

**Learning and Development:**

- This project honed my skills in responsive design and taught me valuable lessons in user-centric design and managing client relationships.

**Stakeholders and Impact:**

- Jon Cohn praised the website for its professional design and ease of use, which directly contributed to higher book sales.

---

## Rewards Platform Re-architecture | WorkTango (formerly KazooHR) | 2019

**Problem Statement/Challenge:**

- WorkTango's existing Rewards platform, originally built on Ruby on Rails, needed modernisation to improve performance, user engagement, and scalability. The challenge was re-architecting the front-end using ReactJS while ensuring seamless integration with backend systems.

**Scope of Work:**

- Led a team to transition the platform’s front end from Ruby on Rails to ReactJS while implementing a modular design system and collaborating with backend developers and UI/UX designers for integration across the Performance Management and Rewards platforms.

**Team Size and Collaboration:**

- Led a front-end development team of 3 engineers and worked closely with back-end developers and UI/UX designers to ensure smooth integration.

**Tools and Environment:**

- ReactJS, Storybook, NodeJS, TypeScript, GraphQL, Ruby on Rails, ActiveRecord, PostgreSQL.

**Key Contributions:**

- Re-architected the Rewards platform from Ruby on Rails to ReactJS by implementing a modular design system, which improved customer engagement by **15%**.
- Optimised front-end performance, reducing page load times by **30%**, which enhanced user experience across the platform.
- Collaborated with backend teams to integrate new features for performance tracking and reward redemption, streamlining the product suite.

**Metrics and KPIs:**

- Increased customer engagement by **15%**, measured through user interaction metrics.
- Reduced page load times by **30%**, leading to a more responsive and enjoyable user experience.

**Learning and Development:**

- This project deepened my expertise in ReactJS and modular design systems, solidifying my leadership skills in guiding cross-functional teams through significant architectural changes.

**Post-Launch Maintenance:**

- Provided ongoing support post-launch, monitoring platform performance and addressing issues as users interacted with the newly re-architected platform.

**Stakeholders and Impact:**

- Users and stakeholders reported improved satisfaction with the platform’s performance and design, contributing to higher customer retention and increased use of the Rewards platform.

---

## Condé Nast Paywall Development | Condé Nast | 2017 - 2019

**Problem Statement/Challenge:**

- Condé Nast required a scalable paywall system to increase subscription revenue across its media brands, such as _Vanity Fair_ and _Wired_. The challenge was building a reusable, brand-agnostic paywall architecture to boost reader engagement and optimise subscription conversion.

**Scope of Work:**

- Developed the paywall architecture and components, which could be used across multiple brands. Worked with cross-functional teams to ensure the system integrated smoothly with each brand's unique needs while enhancing SEO and reader experience.

**Team Size and Collaboration:**

- Collaborated with multiple teams, including UI/UX designers and backend engineers, to develop and optimise the paywall components.

**Tools and Environment:**

- ReactJS, NodeJS, Puppeteer, TypeScript, SASS, Jenkins, CI/CD.

**Key Contributions:**

- Built and iterated on a brand-agnostic paywall architecture using ReactJS components, which increased subscriptions by **100%** year-over-year for _Vanity Fair_ and _Wired_.
- Improved SEO and user engagement by optimising paywall performance, which enhanced reader interaction across 26 media brands.

**Metrics and KPIs:**

- Increased subscription revenue by **100%** year-over-year for significant brands.
- Boosted SEO rankings and user engagement across all implemented brands.

**Learning and Development:**

- This project taught me valuable lessons in performance optimisation and scalable architecture for large media platforms.

**Post-Launch Maintenance:**

- Continued to iterate on the paywall components and supported backend teams to ensure smooth operation and integration across brands.

**Stakeholders and Impact:**

- The success of the paywall system contributed to significant growth in subscription revenue, earning positive feedback from business and technical teams alike.

---

## Mexic-Arte Museum Web Presence | Habitual Genesis | 2017

**Problem Statement/Challenge:**

- Mexic-Arte Museum needed to maintain public engagement while undergoing renovations, which required the museum and its collection to be accessible exclusively online. The challenge was to evaluate the museum's resources and determine the best solution for creating a sustainable, volunteer-managed digital presence.

**Scope of Work:**

- Worked with a team to strategically analyse the museum’s resources, evaluate possible web solutions, and develop a comprehensive recommendation. Researched various platforms and tools, focusing on usability for non-technical volunteers. Findings were presented to the board of trustees for approval.

**Team Size and Collaboration:**

- Collaborated with a team of 4, analysing different options and solutions, and presented our recommendations to the museum’s board of trustees.

**Tools and Environment:**

- HTML5, CSS3, JavaScript, Squarespace.

**Key Contributions:**

- Led a team in strategic analysis of the problem and available resources, resulting in a comprehensive proposal for the board of trustees.
- Researched and evaluated multiple digital solutions to ensure the museum’s collection could be easily maintained by volunteers, providing the board with clear, actionable options.
- Presented recommended solutions to the board of trustees by outlining the benefits, costs, and volunteer-friendly features of each option, leading to the selection of Squarespace as the final platform.

**Metrics and KPIs:**

- Presented a cost-effective, easy-to-maintain solution, leading to increased online donations and sustained visitor interaction during the museum’s closure.

**Learning and Development:**

- This project enhanced my ability to approach problems strategically, working with cross-functional teams to assess resources, explore solutions, and communicate effectively with stakeholders.

**Stakeholders and Impact:**

- The museum’s board of trustees praised the thoroughness of the analysis.

---

## Mock Interview App for an Engineering Education Program | 2016 - 2017

**Problem Statement / Challenge:**

- An engineering education program needed a scalable way to give students mock-interview feedback. Career services was the bottleneck: one-on-one feedback sessions didn't scale to cohort size. The challenge was to build an app that increased the feedback volume without dropping quality.

**Scope of Work:**

- Designed and developed the mock interview app: students record interviews, the app structures common interview questions, and feedback can be collected and reviewed at scale rather than per-student.

**Team Size and Collaboration:**

- Worked with career services and instructional staff to align the app's functionality with how students actually prepared.

**Tools and Environment:**

- JavaScript, jQuery, HTML, CSS, Git, Heroku.

**Key Contributions:**

- Built the app with jQuery and HTML/CSS, expanding the program's mock-interview feedback capacity well beyond what one-on-one sessions had been able to support.
- Structured the question flows around common technical and behavioural interview formats so students got pattern-matched practice, not one-off feedback.

**Metrics and KPIs:**

- Career services reported a substantial increase in the number of students who could go through mock interviews per week, with the same staff capacity.
- Higher reported student preparedness translated to better interview outcomes downstream.

**Learning and Development:**

- This project taught me the unlock that "automate the structure, keep the human in the feedback loop" — a pattern I've kept coming back to since.

**Stakeholders and Impact:**

- Career services and instructional staff used the tool as a regular part of cohort preparation, with measurable increases in student readiness for technical interviews.

---

## Bypass Mobile JSON-API Licensing Platform | Bypass Mobile | 2016

**Problem Statement/Challenge:**

- Bypass Mobile needed a robust product licensing platform to manage and distribute licenses efficiently. The challenge was to design and implement a scalable solution using JSON-API specifications.

**Scope of Work:**

- Developed the licensing platform as part of a small team, resolving technical issues in the development environment and conducting code reviews to ensure high-quality, scalable solutions.

**Team Size and Collaboration:**

- Worked closely with a small development team, collaborating on design, implementation, and testing.

**Tools and Environment:**

- Ruby on Rails, JSON-API, ActiveRecord, MySQL, Git, GitHub, Vagrant.

**Key Contributions:**

- Developed a JSON-API licensing platform using Ruby on Rails, enabling efficient license management for the product suite.
- Resolved development environment issues by optimising workflows, which improved team productivity.

**Metrics and KPIs:**

- Improved licensing management efficiency, streamlining operations and supporting product distribution.

**Learning and Development:**

- This project strengthened my expertise in API development and enhanced my ability to work in small, fast-paced teams.

**Stakeholders and Impact:**

- The platform was successfully deployed, allowing the company to manage licensing more effectively and support future product growth.

---

## Union Metrics Legacy Codebase Migration | Union Metrics | 2014 - 2016

**Problem Statement/Challenge:**

- Union Metrics needed to modernise two critical legacy codebases that were difficult to maintain and hindering performance. The challenge was to migrate these codebases to Rails 4, harden security, and improve system performance.

**Scope of Work:**

- Involved in migration and refactoring efforts, focusing on maintainability and performance improvements. This included updating the codebases, completing quality assurance testing, and optimising performance-critical sections.

**Team Size and Collaboration:**

- Collaborated with a small team of developers and worked closely with IT and support teams to ensure minimal disruption.

**Tools and Environment:**

- Ruby on Rails, ActiveRecord, RSpec, JavaScript, jQuery, MySQL, Git, Vagrant, Jenkins.

**Key Contributions:**

- Migrated and refactored two legacy codebases to Rails 4 by improving maintainability and security, which enhanced system performance by **20%**.

**Metrics and KPIs:**

- Improved system performance by **20%**.

**Learning and Development:**

- This project refined my skills in legacy system modernisation and emphasised the importance of security and maintainability in large codebases.

**Stakeholders and Impact:**

- Internal stakeholders noted improved system stability and efficiency, contributing to faster customer issue resolution and reduced technical debt.
