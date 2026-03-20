# PRD: GitHub Activity Dashboard

## 1. Overview

- **Project Name:** GitHub Activity Dashboard
- **One-liner:** A web app that visualizes your GitHub contribution data — commits, PRs, issues, and reviews — in one clean dashboard.
- **Target Users:** Individual developers who want a better view of their GitHub activity than the default profile heatmap. Also useful for managers tracking team contributions.
- **Success Criteria:**
  - Users can connect their GitHub account and see a dashboard within 60 seconds
  - Dashboard loads in under 2 seconds for up to 1 year of data
  - At least 3 distinct visualization types (chart, timeline, summary stats)

## 2. Problem Statement

GitHub's built-in contribution graph is a green heatmap. That's it. You can't see what types of contributions you made, which repos you were most active in, or how your activity trends over time. If you want to share your work in a standup, review, or portfolio — you're stuck screenshotting a grid of green squares.

The current alternatives are either too complex (self-hosted Grafana dashboards pulling from GitHub's API) or too simple (just the profile page). There's a gap for a focused, good-looking dashboard that just works.

## 3. Features & Requirements

### Authentication

**Feature: GitHub OAuth Login**
- **User Story:** As a developer, I want to sign in with my GitHub account so the app can access my contribution data.
- **Requirements:**
  1. OAuth 2.0 flow with GitHub as the provider
  2. Request minimal scopes: `read:user` and `repo` (for private repo activity)
  3. Store access tokens securely (encrypted at rest)
  4. Support token refresh without requiring re-login
  5. Provide a "Sign out" option that revokes the token
- **Acceptance Criteria:** User clicks "Sign in with GitHub," completes OAuth flow, and is redirected to their dashboard with data loading.
- **Priority:** Must-have
- **Notes:** Consider offering a "public only" mode that uses `read:user` scope only, for users who don't want to grant repo access.

### Dashboard

**Feature: Activity Overview**
- **User Story:** As a developer, I want to see a summary of my GitHub activity at a glance so I can understand my contribution patterns.
- **Requirements:**
  1. Display total counts for: commits, PRs opened, PRs reviewed, issues opened, issues commented on
  2. Show data for a selectable time range (last 7 days, 30 days, 90 days, 1 year, all time)
  3. Highlight the most active repository and most active day of the week
  4. Show a contribution streak counter (consecutive days with activity)
- **Acceptance Criteria:** Dashboard shows accurate counts matching GitHub's data. Changing the time range updates all stats within 1 second.
- **Priority:** Must-have

**Feature: Activity Timeline**
- **User Story:** As a developer, I want to see my contributions on a timeline so I can understand when I'm most productive.
- **Requirements:**
  1. Interactive line/area chart showing contributions over time
  2. Filterable by contribution type (commits, PRs, issues, reviews)
  3. Hover to see details for a specific day
  4. Zoomable — click and drag to focus on a date range
- **Acceptance Criteria:** Chart renders with real data, filters work, hover shows accurate details.
- **Priority:** Must-have

**Feature: Repository Breakdown**
- **User Story:** As a developer, I want to see which repositories I contribute to most so I can understand where my time goes.
- **Requirements:**
  1. Bar chart or treemap showing contributions per repository
  2. Sortable by total contributions, recent activity, or repo name
  3. Click a repo to see contribution details for that repo
  4. Show top 10 by default with "show all" option
- **Acceptance Criteria:** Chart accurately reflects per-repo contribution counts. Clicking a repo shows a detail view.
- **Priority:** Should-have

**Feature: Shareable Profile Card**
- **User Story:** As a developer, I want to generate a shareable image of my stats so I can include it in my portfolio or share on social media.
- **Requirements:**
  1. Generate a card image (PNG) with key stats and a mini chart
  2. Customizable color theme (at least 3 options)
  3. Include GitHub username and avatar
  4. Copy image or direct link to clipboard
- **Acceptance Criteria:** Generated image is visually clean, accurate, and shareable via URL or download.
- **Priority:** Nice-to-have

## 4. Technical Requirements

- **Performance:** Dashboard must load in under 2 seconds with cached data. Initial data fetch for 1 year of history should complete within 10 seconds.
- **Security:** OAuth tokens encrypted at rest. No tokens stored in localStorage. HTTPS only. Rate-limit API calls to prevent abuse.
- **Compatibility:** Chrome, Firefox, Safari, Edge (latest 2 versions). Mobile-responsive but optimized for desktop.
- **Integrations:** GitHub REST API v3 and/or GraphQL API v4. No other third-party services required.
- **Data:** Cache GitHub data for 1 hour to reduce API calls. Users can force-refresh. No long-term storage of contribution data (fetch on demand).

## 5. UI/UX Requirements

- **Key Screens:**
  1. Landing page — hero, value proposition, "Sign in with GitHub" button
  2. Dashboard — stats summary, timeline chart, repo breakdown, all on one scrollable page
  3. Settings — manage connection, select time range default, choose theme
- **Navigation:** Minimal. Dashboard is the main (and nearly only) screen. Settings accessible from a header menu.
- **Responsive:** Full layout on desktop. Stacked single-column on mobile with simplified charts.
- **Accessibility:** Keyboard navigable. Charts include alt text or data table fallback. Sufficient color contrast.

## 6. Out of Scope

- **Team dashboards** — this version is single-user only
- **Non-GitHub sources** — no GitLab, Bitbucket, etc.
- **Notifications or alerts** — no "you haven't committed in 3 days" nudges
- **Historical comparison** — no "this month vs. last month" views (might add later)
- **Mobile app** — responsive web only, no native apps

## 7. Open Questions

1. **Private repo data:** Should we default to public-only and let users opt into private repo access? (Product decision)
2. **Rate limiting:** GitHub API has a 5,000 req/hour limit for authenticated users. Is caching + incremental fetching enough, or do we need a backend queue? (Technical investigation)
3. **Hosting:** Vercel (easiest for Next.js) or self-hosted? Affects cost and deployment complexity. (Infrastructure decision)

## 8. Timeline & Phases

| Phase | What Gets Built | Estimate |
|-------|----------------|----------|
| 1. Project Setup | Next.js scaffold, GitHub OAuth, basic layout | Small |
| 2. Data Layer | GitHub API integration, data fetching, caching | Medium |
| 3. Dashboard Core | Stats summary, activity timeline chart | Medium |
| 4. Dashboard Extended | Repo breakdown, time range selector | Medium |
| 5. Shareable Cards | Profile card generation, themes | Small |
| 6. Polish | Responsive design, loading states, error handling, accessibility | Medium |
