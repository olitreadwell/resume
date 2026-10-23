# Software Engineer Resume - Oli Treadwell

## Table of Contents


* <strong>[PDF Resume for Downloading, NZ (2026-10-07)](./Oli%20Treadwell%20-%20Senior%20Software%20Engineer%20Resume%20-%20NZ%20-%202026-10-07.pdf)</strong>
* <strong>[PDF Resume for Downloading, Remote (2026-10-01)](./Oli%20Treadwell%20-%20Senior%20Software%20Engineer%20Resume%20-%20Remote%20-%202026-10-01.pdf)</strong>
* <strong>[Portfolio Projects](./portfolio-projects.md)</strong>
* <strong>[Open Source Contributions](./open-source-contributions.md)</strong>
* <strong>[Common Hiring Questions](./common-hiring-questions.md)</strong>
* <strong>[Recommendations & References](./linkedin-recommendations.md)</strong>
* <strong>[Skills & Experience](./skills-and-experience.md)</strong>
* <strong>[Community & Events](./community-and-events.md)</strong>
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

Senior full-stack product engineer with 11 years in the industry, eight of them in React and five in Ruby on Rails. I take work from the problem statement to production: find the edge cases, write down the decisions, build it, ship it, and stay for what happens after launch. Worked across media, HR tech, healthcare, compliance and conference platforms.

I moved an HR and rewards platform's front end from Rails views to React, which lifted customer engagement by 15% after launch, and built the design system the front end ran on. At Condé Nast I shipped one brand-agnostic paywall across 26 media sites, and the rule engine behind it let each brand set its own trigger from user behaviour and content type rather than one rule for all of them.

I ship small pull requests against a trunk that deploys often, keep lint, type and test gates green, and expect a second engineer to read every change. I use AI tools for the first pass on review and scaffolding and keep a person on the decision. Accessibility, internationalisation and screen size are delivery requirements in my work, not a later pass, because the products I have shipped serve users in a lot of markets.

I build the agentic layer teams need for AI-assisted delivery rather than using the tools by hand: an MCP server that lets a coding agent audit and fix React performance, a GitHub Action that tiers pull request authors, and a code-review agent template a delivery team ran on every change. Taught over 300 engineers to use ChatGPT and GitHub Copilot to the standard that they can explain the work rather than outsource it. UK and US citizen.

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

Feb 2025 – Jun 2026

- Delivered 580+ commits across compliance, healthcare, marketing and conference products with every lint, type and test gate green, by pairing with design, PM and back-end partners from the first ticket to release.
- Built the studio's AI code-review template that caught errors before production, and grew it with team-contributed rules by shipping it as reusable config rather than a one-off script.
- Shipped with AI-assisted tooling on nearly every pull request, which made room for test-driven development, end-to-end tests, accessibility checks and the docs a tight schedule would have dropped.
- Rebuilt the compliance app's shared components, validation and accessibility wrappers in Electron, cutting form bug reports about 60% with Jest suites on each refactor. The component layer became the base for the next two client projects.
- Extended staff and case schemas on the HR case platform (preferred case owners, privacy filters) and shipped the components into the shared design system.
- Removed iOS search glitches on the multi-market wearables site, across EN and KR, by building a WebP asset pipeline and resizing scripts that kept images and translations aligned.
- Cut code duplication 40% on the design conference site by consolidating shared sections, and kept Storybook and JSDoc current so a new contributor shipped within a day.
- Technologies: React, TypeScript, Electron, Next.js 15, Tailwind CSS, Sass, Sanity v3, Prisma, Cypress, Jest/React Testing Library, Storybook, GitHub Actions, AWS, Figma, Jira.

##### Principal Engineer & Technical Consultant | Habitual Genesis

2016 – Present

- Maintained **ai-harness** to 127 skills validated against the agentskills.io spec, installable into Claude Code, Codex, Cursor and Gemini CLI from one installer, so a team configures every agent from one repo.
- Wrote the **React Performance Checklist**, 34 rules as structured data with a plain-language glossary, worked examples and an MCP server, so an agent can list a rule, fetch it and return an audit or fix plan.
- Built **PR Vetting**, a dependency-free Python CLI and GitHub Action that tiers pull request authors from public signals, so an unknown or bot account cannot merge without a human decision.
- Landed **13 pull requests** with outside maintainers (adobe/react-spectrum, freeCodeCamp/devdocs, plausible/analytics, encode/django-rest-framework) by keeping each fix small enough to review in one sitting.
- Produced open-data directories and connectors for New Zealand, the UK and the US from one repeatable pipeline, with a project template carrying quality gates, CI and an interactive scaffolder.
- Shipped a mobile-first site for author Jon Cohn's book 'Slashtag' in Bootstrap, HTML5, CSS3 and JavaScript, built to run without maintenance between book launches.
- Rebuilt Mexic-Arte Museum's volunteer-maintained web presence before the collection went web-only during building renovations, so a non-technical volunteer team could keep it current.
- Added newsletter signup and reworked mobile layout and information architecture for Read the Room Education, so their early-childhood programs were findable on a phone.
- Technologies: TypeScript, Node.js, Python, JavaScript, HTML5, CSS3, Bootstrap, GitHub Actions, MCP, GitHub Pages, SquareSpace, Mailchimp, Google Drive.

##### Software Engineer (Contract) | PartsTrader Markets Ltd
Wellington

2024 – 2025

- Picked up .NET and C# from zero in one contract and retired spreadsheet-driven onboarding, by shipping a layered service facade, a React console and a Windows toolchain.
- Stabilised BAU releases so automation runs stopped failing, by defining the Repository, Domain, Mapper and Service layers and adding Cypress smoke tests and GitHub Actions pipelines.
- Technologies: C#/.NET, React, TypeScript, styled-components, Cypress, GitHub Actions, Azure DevOps, Jira, Confluence.

##### Senior Software Engineer | HR / Rewards SaaS Platform
Remote

2019 – 2020

- Moved the rewards platform's front end off Rails views and onto React, lifting customer engagement 15% after launch, by rebuilding the module around a shared design system.
- Built that modular design system, which cut inconsistent UI and raised velocity for a three-engineer front-end team.
- Shipped Performance Management and Rewards integrations as part of a suite-wide overhaul, so the two products read as one.
- Mentored junior engineers and formalised the third-party library decision process, so a library choice arrived with its trade-offs written down.
- Technologies: ReactJS, Storybook, NodeJS, Jest, Chai, TypeScript, Ruby on Rails, ActiveRecord, RSpec, GraphQL, PostgreSQL, CircleCI, SASS/SCSS, GitHub, design systems, JIRA, Zeplin, Figma.

##### Software Engineer | Condé Nast
Hybrid - Austin, TX

2017 – 2019

- Delivered React components and design features to 26 media brands, improving readership and search visibility.
- Built a brand-agnostic paywall and component suite that lifted monthly subscriptions for Vanity Fair and Wired by over 100% year on year, by keeping one core and putting brand rules in configuration.
- Wrote the engineering post on end-to-end testing the paywalls after building the Puppeteer suite that caught cross-brand regressions before release.
  <https://web.archive.org/web/20211202210445/https://technology.condenast.com/story/end-to-end-testing-conde-nast-paywalls>
- Technologies: ReactJS, Storybook, NodeJS, Jest, Puppeteer, TypeScript, SASS, GitHub, Jenkins, CI/CD, Design Language Systems, JIRA.

##### Software Engineer (Contract) | Bypass Mobile
Onsite - Austin, TX

2016 – 2016

- Designed and built a JSON:API product licensing platform in Rails with a small team, then resolved environment issues and reviewed code in GitHub to keep the release moving.
- Technologies: JSON-API, Ruby on Rails, ActiveRecord, RSpec, MySQL, Git, GitHub, Vagrant, bash, JIRA.

##### Software Engineer | Union Metrics
Onsite - Austin, TX

2014 – 2016

- Migrated two legacy codebases to Rails 4, improving core feature performance 20% and closing security gaps, by refactoring in place rather than rewriting.
- Created a knowledge base of the 100 most common customer technical issues, cutting resolution time 50% by giving support a written answer for each.
- Liaised between customers and engineering to diagnose and resolve issues, so a bug report arrived as a reproducible case rather than a description.
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
