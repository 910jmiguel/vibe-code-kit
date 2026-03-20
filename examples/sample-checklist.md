# Checklist: GitHub Activity Dashboard

## Phase 1: Project Setup
_Goal: App runs locally with GitHub OAuth working and a basic page layout._

- [x] Initialize Next.js project with TypeScript and Tailwind CSS
- [x] Set up ESLint and Prettier with project conventions
- [x] Create GitHub OAuth app (dev environment) and store credentials in `.env.local`
- [x] Implement GitHub OAuth flow (sign in, callback, token storage)
- [x] Create basic app layout — header with logo, nav, sign in/out button
- [x] Add a protected route wrapper that redirects unauthenticated users to landing page
- [x] Create landing page with hero section and "Sign in with GitHub" CTA
- [ ] **Decision point:** Confirm OAuth scopes — `read:user` only or `read:user` + `repo`?

## Phase 2: Data Layer
_Goal: App fetches and caches GitHub contribution data for the signed-in user._

- [x] Create GitHub API client with token-based auth
- [x] Implement data fetching for commits (GET /users/{user}/events)
- [x] Implement data fetching for PRs (search API: author:{user} type:pr)
- [ ] Implement data fetching for issues (search API: author:{user} type:issue)
- [ ] Implement data fetching for PR reviews (GET /user/repos + PR review endpoints)
- [ ] Normalize all data into a unified activity format: `{ type, repo, date, url, title }`
- [ ] Add in-memory cache with 1-hour TTL
- [ ] Handle GitHub API rate limiting — detect 403 responses, show user-friendly message
- [ ] Add "force refresh" function that clears cache and re-fetches
- [ ] **Decision point:** Is the REST API sufficient or do we need GraphQL for any queries?

## Phase 3: Dashboard Core
_Goal: Dashboard shows stats summary and an interactive activity timeline._

- [ ] Create dashboard page layout — stats bar at top, chart below
- [ ] Build stats summary component showing: total commits, PRs opened, PRs reviewed, issues opened, issues commented
- [ ] Add time range selector (7 days, 30 days, 90 days, 1 year, all time)
- [ ] Build activity timeline chart using Recharts or Chart.js
  - [ ] Line/area chart with date on x-axis, contribution count on y-axis
  - [ ] Filter toggles for contribution type (commits, PRs, issues, reviews)
  - [ ] Hover tooltip showing day details
- [ ] Wire time range selector to filter both stats and chart
- [ ] Add loading skeletons for stats and chart while data is fetching
- [ ] Handle empty state — new user with no data

## Phase 4: Dashboard Extended
_Goal: Dashboard includes repo breakdown and all interactive features are working._

- [ ] Build repository breakdown component
  - [ ] Bar chart showing top 10 repos by contribution count
  - [ ] Sort options: total contributions, recent activity, repo name
  - [ ] "Show all" toggle for users with many repos
- [ ] Add click-through from repo chart to repo detail view
  - [ ] Show contribution breakdown by type for that repo
  - [ ] Link to the repo on GitHub
- [ ] Calculate and display "most active day of the week" stat
- [ ] Calculate and display contribution streak counter
- [ ] Ensure all components respond to time range changes

## Phase 5: Shareable Profile Card
_Goal: Users can generate and share a profile card image with their stats._

- [ ] Design profile card layout (400x200px PNG)
  - [ ] GitHub avatar, username, key stats, mini activity chart
- [ ] Implement server-side card generation (use @vercel/og or canvas)
- [ ] Add 3 color themes: light, dark, ocean
- [ ] Create card preview in settings/share page
- [ ] Add "Copy link" and "Download PNG" buttons
- [ ] Generate unique shareable URL for each user's card

## Phase 6: Polish
_Goal: App is production-ready — responsive, accessible, handles all error states._

- [ ] Responsive design pass — test and fix layout on mobile and tablet
- [ ] Simplify charts on small screens (fewer data points, stacked layout)
- [ ] Add keyboard navigation to all interactive elements
- [ ] Add alt text / data table fallback for charts
- [ ] Audit color contrast (WCAG AA minimum)
- [ ] Add error boundaries — graceful handling of API failures, missing data
- [ ] Add proper 404 and error pages
- [ ] Remove all console.logs, TODO comments, and debug code
- [ ] Write a README with setup instructions and screenshots

## Final Checks
- [ ] All features from PRD are implemented
- [ ] Manual smoke test: sign in → view dashboard → change time range → view repo detail → generate card
- [ ] Test with a GitHub account that has minimal activity (edge case)
- [ ] Test with a GitHub account that has heavy activity (performance)
- [ ] Error states tested: revoked token, API rate limit, network offline
- [ ] Code cleaned up — no dead code, debug logs, or commented-out blocks
- [ ] Ready for deploy to Vercel
