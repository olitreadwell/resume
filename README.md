# Software Engineer Resume - Oli Treadwell

## Table of Contents


* <strong>[PDF Resume for Downloading, NZ (2026-10-07)](./Oli%20Treadwell%20-%20Senior%20Software%20Engineer%20Resume%20-%20NZ%20-%202026-10-07.pdf)</strong>
* <strong>[PDF Resume for Downloading, Remote (2026-10-01)](./Oli%20Treadwell%20-%20Senior%20Software%20Engineer%20Resume%20-%20Remote%20-%202026-10-01.pdf)</strong>
* <strong>[Portfolio Projects](./portfolio-projects.md)</strong>
* <strong>[Open Source Contributions](./open-source-contributions.md)</strong>
* <strong>[Common Hiring Questions](./common-hiring-questions.md)</strong>
* <strong>[Recommendations & References](./linkedin-recommendations.md)</strong>
* <strong>[Skills & Experience](./skills-and-experience.md)</strong>
* [Links](#links)
<!-- * [Resume Images](#resume-images) -->
* [Markdown Resume](#markdown-resume)
    * [Summary](#summary)
    * [Skills](#skills)
    * [Experience](#experience)
    * [Technical Training & Mentoring](#technical-training--mentoring)
    * [Education](#education)
    * [Industry Thought Leadership & Speaking Engagements](#industry-thought-leadership--speaking-engagements)
    * [Professional Development](#professional-development)
    * [Conference & Workshop Attendance](#conference--workshop-attendance)
* [Skills](./skills-and-experience.md)

## Links

[Back to Top](#table-of-contents)

<!--
* Link to PDF on Google Drive - [https://drive.google.com/file/d/1hKKt-3GvHqYuSnT4gtddXZFoU8xTtw4b/view?usp=sharing](https://drive.google.com/file/d/1hKKt-3GvHqYuSnT4gtddXZFoU8xTtw4b/view?usp=sharing)
-->
* LinkedIn - [https://www.linkedin.com/in/olitreadwell](https://www.linkedin.com/in/olitreadwell)

* Sample Teaching Videos - [https://www.youtube.com/playlist?list=PLqSaJmO19SING0DHaVGNzgOWZzRu5drWv](https://www.youtube.com/playlist?list=PLqSaJmO19SING0DHaVGNzgOWZzRu5drWv)

---

<!--
## Resume Images

[Back to Top](#table-of-contents)

![Oli Treadwell Software Engineer Resume - 2024 06 22 page 1](https://github.com/user-attachments/assets/553bd156-5d73-4ed8-b979-db5d1bddb8bf)

![Oli Treadwell Software Engineer Resume - 2024 06 22 page 2](https://github.com/user-attachments/assets/f68001f0-3fe9-4800-89db-3015f3dcbac0)

---
-->

## Markdown Resume

[Back to Top](#table-of-contents)

### Oli Treadwell
#### Senior Software Engineer & Technical Trainer  

- [oliver.treadwell@gmail.com](mailto:oliver.treadwell@gmail.com)
- [linkedin.com/in/olitreadwell](https://www.linkedin.com/in/olitreadwell)
- [github.com/olitreadwell](https://www.github.com/olitreadwell)

#### SUMMARY

Senior full-stack engineer shipping across multiple client products in a forward-deployed style: embedded with clients, owning frontend and full-stack scope, working closely with design, PM and backend partners. Decade of experience across media, HR tech, healthcare, compliance and conference platforms. Builds the agentic layer teams need for AI-assisted delivery rather than using the tools by hand: an MCP server that lets a coding agent audit and fix React performance, a GitHub Action that tiers pull request authors, and a code-review agent template a delivery team ran on every change. Taught over 300 engineers to use ChatGPT and GitHub Copilot to the standard that they can explain the work rather than outsource it. UK and US citizen.

#### Skills

- **AI & Automation:** AI-assisted SDLC adoption and team rollout, agentic and multi-agent pipelines, agent-consumable tooling (MCP servers, GitHub Actions for agents), LLM API integration, AI-assisted engineering workflows, ChatGPT and GitHub Copilot instruction, local and hosted open models (Ollama, Qwen, DeepSeek), agentic IDE and AI code review tooling, spec-driven workflows.
- **Front-end Systems:** React, Next.js, Electron, Tailwind CSS, Sass/SCSS, design tokens, Storybook, accessibility testing (axe, Lighthouse), component governance.
- **Back-end & Services:** Node.js/TypeScript, Ruby on Rails, Python/Flask, C#/.NET, Prisma & ActiveRecord, PostgreSQL, MySQL, REST/JSON:API, GraphQL, domain-driven microservices.
- **Quality & Reliability:** Jest, React Testing Library, Cypress, Puppeteer, RSpec, CI pipelines (GitHub Actions, CircleCI, Jenkins), lint/type enforcement, feature flagging.
- **DevOps & Platforms:** CI/CD pipeline ownership (GitHub Actions, CircleCI, Jenkins), build and test gates, monitoring and error tracking, AWS/GCP/Azure basics, Docker, Vagrant, Terraform-adjacent workflows, Netlify/Vercel/Render deployments.
- **Product & Collaboration:** Agile/Scrum/Kanban facilitation, RFC-driven decision making, Linear, Jira, Notion, Confluence, Figma, Loom.
- **Mentoring & Community:** Code-review-driven mentorship, technical training, accessibility advocacy, community organising (meetup organiser and speaker across multiple cities).

#### EXPERIENCE

##### Senior Software Engineer | Numeral Studio
Wellington / Remote

Feb 2025 – Jun 2026 (role made redundant)

- Delivered multi-client throughput via **580+ commits** with consistently green lint/type/test gates by pairing tightly with design, PM, and back-end partners across compliance, healthcare, marketing, and conference products.
- Built the studio's AI-assisted delivery layer: a reusable template that ran AI code review and caught errors before they reached production, with the team contributing rules to it.
- Used AI-assisted tooling on nearly every pull request shipped, which made room for test-driven development, end-to-end tests, accessibility testing and the documentation a tight schedule would otherwise have skipped.

- **Regulatory compliance desktop app:** Rebuilt shared React TypeScript components, predictable validation flows, and accessibility wrappers inside a React/Electron shell, then backed the refactor with targeted Jest suites so compliance analysts stopped encountering silent audit errors.
- **HR & case management platform:** Extended staff/case schemas (preferred case owners, privacy filters), shipped numerous components to the design system for improved workflows.
- **Consumer device multi-market web experience:** Orchestrated a WebP asset pipeline, automated resizing scripts, and EN/KR localisation fixes that removed iOS search glitches and aligned translations across wearables and tutorial flows.
- **Design conference event site:** Cut code duplication by 40%, and maintained Storybook/JSDoc docs so new contributors could ship within a day.
- Technologies: React, TypeScript, Electron, Next.js 15, Tailwind CSS, Sass, Sanity v3, Prisma, Cypress, Jest/React Testing Library, Storybook, GitHub Actions, AWS, Figma, Jira.

##### Principal Engineer & Technical Consultant | Habitual Genesis

2016 – Present

- Maintains **ai-harness**, a public, versioned home for AI coding-agent configuration: 127 reusable skills validated against the agentskills.io spec, global instructions readable by Claude Code, Codex, Cursor and Gemini CLI, an installer that wires into every installed tool, and subagent role definitions.
- Wrote the **React Performance Checklist**, public training material on fixing slow React apps: 34 rules held as structured data, a plain-language glossary, worked examples, and an MCP server so an agent can list rules, fetch one, and produce audit or fix plans.
- Built **PR Vetting**, a dependency-free Python CLI and GitHub Action that tiers pull request authors from public GitHub signals, so unknown or bot accounts cannot merge without a human decision.
- Contributes to open source projects, with **13 pull requests merged upstream** by outside maintainers (adobe/react-spectrum, freeCodeCamp/devdocs, plausible/analytics, encode/django-rest-framework and others).
- Maintains a public portfolio of open-data directories and connectors across New Zealand, the UK and the US, produced from one repeatable pipeline, plus a project template carrying quality gates, CI and an interactive scaffolder.
- Shipped a mobile-first, low-maintenance website for award-winning author Jon Cohn's book 'Slashtag' using Bootstrap, HTML5, CSS3, and JavaScript; the site served as a focused marketing surface and supported book sales.
- Consulted Mexic-Arte Museum’s volunteer team to create a seamless, volunteer-maintained web presence, prior to the museum and their collection becoming web-only during building renovations.
- Added newsletter signup and reworked mobile layout and information architecture for non-profit Read the Room Education to highlight their early-childhood programs.
- Technologies: TypeScript, Node.js, Python, JavaScript, HTML5, CSS3, Bootstrap, GitHub Actions, MCP, GitHub Pages, SquareSpace, Mailchimp, Google Drive.

##### Software Engineer (Contract) | PartsTrader Markets Ltd
Wellington

2024 – 2025

- Picked up .NET and C# from zero, then retired spreadsheet-driven onboarding steps by shipping a .NET service facade (Repository, Domain Model, Mapper, Application Service layers), a React/TypeScript console, and a Windows-native toolchain aligned to Figma prototypes.
- Stabilized BAU releases as measured by dependable automation runs by defining Repository→Domain→Mapper→Service layers plus Cypress smoke tests and GitHub Actions pipelines.
- Technologies: C#/.NET, React, TypeScript, styled-components, Cypress, GitHub Actions, Azure DevOps, Jira, Confluence.

##### Senior Software Engineer | HR / Rewards SaaS Platform
Remote

2019 – 2020

- Led a Rails-to-React migration on an HR and employee-rewards SaaS platform, with a 15% lift in customer engagement after launch.
- Built a modular design system that tightened UI consistency and raised developer velocity for the frontend team of 3.
- Shipped integrations across the Performance Management and Rewards products as part of a wider suite overhaul.
- Mentored junior engineers and formalised the technology decision-making process for third-party libraries.
- Technologies: ReactJS, Storybook, NodeJS, Jest, Chai, TypeScript, Ruby on Rails, ActiveRecord, RSpec, GraphQL, PostgreSQL, CircleCI, SASS/SCSS, GitHub, design systems, JIRA, Zeplin, Figma.

##### Software Engineer | Condé Nast
Hybrid - Austin, TX

2017 – 2019

- Delivered new design features & ReactJS components for over 26 media brands, improving readership and SEO.
- Built and iterated upon a brand-agnostic paywall architecture and suite of components, driving significant growth and achieving a year-over-year increase of over 100% in monthly subscriptions for Vanity Fair and Wired.
- Authored a technology blog post on End-to-End Testing the Condé Nast Paywalls. [https://technology.condenast.com/story/end-to-end-testing-conde-nast-paywalls](https://web.archive.org/web/20211202210445/https://technology.condenast.com/story/end-to-end-testing-conde-nast-paywalls)
- Technologies: ReactJS, Storybook, NodeJS, Jest, Puppeteer, TypeScript, SASS, GitHub, Jenkins, CI/CD, Design Language Systems, JIRA.

##### Software Engineer (Contract) | Bypass Mobile
Onsite - Austin, TX

2016 – 2016

- Designed and developed a JSON-API spec product licensing platform using Ruby-on-Rails as part of a small team. - Resolved development environment issues and performed code reviews using Github.com.
- Technologies: JSON-API, Ruby on Rails, ActiveRecord, RSpec, MySQL, Git, GitHub, Vagrant, bash, JIRA.

##### Software Engineer | Union Metrics
Onsite - Austin, TX

2014 – 2016

- Migrated and refactored two legacy codebases to use Rails 4, improving maintainability, security of core business features, and performance by 20%.
- Created knowledge base of 100 most common customer technical challenges, reducing resolution time by 50%.
- Liaised between customer and engineering teams to diagnose and resolve customer issues.
- Technologies: JavaScript, Ruby on Rails, ActiveRecord, RSpec, jQuery, HTML, CSS3, SASS/SCSS, MySQL, Git, GitHub, Vagrant, Jenkins, bash.

#### TECHNICAL TRAINING & MENTORING

##### Technical Training & Mentoring | Junior-to-mid engineers across a variety of orgs

2016 – 2017, 2022 – 2023

- Delivered technical training on ChatGPT and GitHub Copilot to a remote cohort of over 300 students, with the standard that they demonstrate understanding of the work rather than outsource it to the tool.
- Designed and delivered curriculum and live workshops covering JavaScript, HTML/CSS, ReactJS, Python, Flask, PostgreSQL, OOP, CI/CD, Agile, APIs, and web accessibility, with structured assessments and PR-level feedback.
- Mentored junior engineers through their first production-grade work; cohorts I supported achieved a 90% graduation rate and 75% job placement within 90 days of graduation.
- Built a mock-interview app that lifted career-services feedback capacity well beyond what one-on-one sessions allowed.
- Co-led an inclusive web design and accessibility working group across the engineering org.
- Technologies: JavaScript, HTML5, CSS3, ReactJS, React Router, Python, Flask, OOP, CI/CD, Render.com, Agile, APIs, web accessibility.

#### EDUCATION
- Postgraduate Diploma in Information Technology | Whitireia and WelTec
- Full-Stack Web Development, Ruby on Rails, and JavaScript Certification | Dev Bootcamp
- BS in Business Administration, Entrepreneurship, & International Business | Chapman University

#### INDUSTRY THOUGHT LEADERSHIP & SPEAKING ENGAGEMENTS

- Selected to speak on cognitive accessibility, NZ Tech Rally, 2026 (withdrew unwell)
- Panel Discussion on Ethics, Austin on Rails Event, Moderator, 2019
- “A Day in the Life of a Programmer,” General Assembly Congress Austin, Presenter, 2018
- Refresh Austin, Organizer, Speaker, and MC, 2015 – 2017
- Silicon Beach Melbourne, Organizer, Speaker, MC, 2012 – 2013
- TechStars Startup Weekend, Co-organiser across San Diego, Orange County, Melbourne, Sydney, and Wellington, 2012 – 2014

#### PROFESSIONAL DEVELOPMENT

- Open Source Contributor, Open San Diego - Code for America Brigade
- Member, a11ySD - San Diego Accessibility Meetup
- Member, ReactJS San Diego & San Diego JavaScript
- Member, ReactJS Austin
- Member, Austin on Rails & AustinRB
- Member, Austin Bleeding Edge Web

#### CONFERENCE & WORKSHOP ATTENDANCE

- axe-con Accessibility Conference, Attendee, 2023, 2024, 2025
- Assert(JS) Conference, Attendee, 2018
- Rocky Mountain Ruby, Attendee, 2017
- Keep Ruby Weird, Attendee, 2015
- LoneStarRuby Conference, Attendee, 2015 - RubyConf, Attendee, 2015
- Keep Ruby Weird, Attendee, 2014
