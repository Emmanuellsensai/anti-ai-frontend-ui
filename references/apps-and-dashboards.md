# Apps and dashboards

Landing pages persuade; apps get work done. The same four habits apply (fidelity, study, specificity, restraint),
but an app is judged on speed of use, not first impression. Read this for any signed-in product: dashboards,
admin areas, developer consoles, support desks and embeddable widgets.

## 1. Rules that change from a landing page

| Landing page | App |
|---|---|
| Big photos, grain, wordmarks | Quiet chrome. The user's data is the picture. Brand shows in the colour of actions, the logo, type and one accent |
| Alternating feature rows | A predictable grid: the same page header, the same table, the same form layout on every page |
| Motion to reveal sections | Motion only for state: a row added, a panel opening, a toast. 150 to 250 ms, ease-out, never on load |
| One display face for drama | The display face only for page titles and big numbers, if at all |
| Real proof or nothing | Real data or an honest empty state. Never invented metrics, users or activity, even as "sample" |

## 2. Shell

- **Sidebar** on desktop: logo, organisation switcher, at most 7 items, account at the bottom. Icons are recognisable
  glyphs at 20 px, no tinted chips. Active item: brand-tinted background plus brand text, not a glowing bar.
- **Top bar**: page title on the left, one primary action on the right, search if there is something to search.
- **Phone**: a bottom tab bar with the 4 or 5 most used items and "More"; the sidebar becomes a sheet. Every tap
  target 44 px.
- **Page header**: title, one sentence saying what the page is for (only on first visits or empty pages), actions.
- Width: content max about 1200 px for reading pages; tables may use the full width.

## 3. Showing data

- **Tables beat cards** for anything people compare or scan. Hairline rows, tabular figures, numbers right-aligned,
  the most important column first, row click opens a side panel (not a new page) so the list stays in place.
- On phones a table row becomes a two-line list item: the main fact large, two secondary facts small.
- **Numbers**: one row of 3 or 4 key figures at the top of an overview, large numerals, a plain label, the change in
  words ("12 more than yesterday"), no sparkline unless the trend matters.
- **Charts**: only when the shape matters. Flat bars or a single line, brand colour, direct labels instead of
  legends, no gradients, no 3D, no donut for more than three parts.
- **Status**: plain words in quiet text, or the brand colour for the one state that needs action. One semantic
  colour (error red) is the allowed exception. No rainbow of pills.
- **Times**: relative for recent ("4 min ago"), absolute on hover and in exports, always in the user's time zone.

## 4. States every screen needs

| State | Do |
|---|---|
| Empty | Say what will appear here and give the one action that fills it ("No calls yet. Start your first job.") |
| Loading | Keep the layout; show the page header at once; a quiet skeleton only for the region that is loading |
| Error | Say what failed in plain words, keep the user's input, offer retry |
| No permission or locked | Show the page, lock the action, say why and how to unlock ("Verify your business to start live calls") |
| Preview / not connected | If a backend is not live yet, the page works on an honest empty account and a quiet line says "Billing connects soon"; never fake numbers |

## 5. Forms and actions

- One column, labels above fields, help text under the field only when needed, errors next to the field.
- Primary button in the brand colour, one per view. Destructive actions ask once, naming exactly what goes.
- Save state visibly ("Saved") instead of toasts for every keystroke. Undo beats "Are you sure?" for small things.
- Long setups become steps with Back, Skip and Next, each step one decision.

## 6. Developer consoles

- **Keys**: shown once in full with a copy button, then only the prefix; revoke is one click with the name confirmed.
  Test and live keys look different (label and prefix), never only by colour.
- **Code samples**: curl first, then the main languages, copy button on every block, the user's real key prefix
  filled in, no fake output: show the real response shape.
- **Playground**: the real product, not a mock. One box, language and voice pickers, play. Shows the exact request
  it sent, so it doubles as documentation.
- **Logs**: newest first, status, latency, size; click a row for request and response with secrets masked.
- **Usage and billing**: the balance, what one unit costs, the last 30 days as a simple bar per day, and the top-up
  button. Prices in the local currency.

## 7. Support desks and embeddable widgets

- **Queue**: a list sorted by urgency, then waiting time; each row shows reason, customer, waiting time, owner.
- **Case panel**: summary first (three lines a busy agent can read in five seconds), then suggested next step, then
  transcript and recording, then history. Actions at the top: call back, resolve, reassign.
- **Timers**: show time left against the target, turning to the brand accent when close, the error colour when late.
- **Keyboard**: j/k to move, Enter to open, e to resolve, ? to show shortcuts. Agents live in the queue all day.
- **Widget inside someone else's app**: one script tag; render inside a shadow root or an iframe so the host's CSS
  cannot break it and ours cannot leak; a small launcher with a count; opens a side panel; respects the host's
  page (no full-screen takeover, no sound without consent); works without our cookies (token from the host).

## 8. QA additions for apps

- Walk every flow as a first-time user on a 360 px phone with touch sizes forced: sign up to the first success.
- Test every state in section 4 by forcing it (empty account, failed request, locked role).
- Keyboard only: every action reachable, focus visible, side panels trap and return focus.
- Lighthouse on the production build of signed-in pages (use a preview session or the preview mode), plus axe.
- Check numbers in tables line up (tabular figures) and long names and amounts do not break rows at 320 px.

## 9. Keep this file growing

After building a new kind of app (marketplace, editor, analytics, mobile app, game UI), add a section here or a
new reference file with what was learned and the corrections the product owner made. Link it from SKILL.md under
"Application types".
