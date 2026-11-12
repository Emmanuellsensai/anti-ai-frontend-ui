# Apps and dashboards

Landing pages persuade; apps get work done. The same four habits apply (fidelity, study, specificity, restraint),
but an app is judged on speed of use, not first impression. Read this for any signed-in product: dashboards,
admin areas, developer consoles, queues and inboxes, editors, analytics and embeddable widgets.

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
| Empty | Say what will appear here and give the one action that fills it ("No invoices yet. Create your first one.") |
| Loading | Keep the layout; show the page header at once; a quiet skeleton only for the region that is loading |
| Error | Say what failed in plain words, keep the user's input, offer retry |
| No permission or locked | Show the page, lock the action, say why and how to unlock ("Verify your email to publish your site") |
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
- **Playground**: the real product, not a mock. One input, the few options that matter, run. Shows the exact request
  it sent, so it doubles as documentation.
- **Logs**: newest first, status, latency, size; click a row for request and response with secrets masked.
- **Usage and billing**: the balance, what one unit costs, the last 30 days as a simple bar per day, and the top-up
  button. Prices in the local currency.

## 7. Queues, inboxes and embeddable widgets

Any screen where people work through a list all day: tickets, orders to fulfil, applications to review, content to
moderate, leads to follow up.

- **Queue**: a list sorted by urgency, then waiting time; each row shows the reason, who it is for, how long it has
  waited and who owns it.
- **Item panel**: summary first (three lines a busy person can read in five seconds), then the suggested next step,
  then the full record (messages, files, history). The main actions at the top: reply, resolve, reassign.
- **Timers**: show time left against the target, turning to the brand accent when close, the error colour when late.
- **Keyboard**: j/k to move, Enter to open, e to resolve, ? to show shortcuts. People who work a queue live in it.
- **Widget inside someone else's app**: one script tag; render inside a shadow root or an iframe so the host's CSS
  cannot break it and ours cannot leak; a small launcher with a count; opens a side panel; respects the host's
  page (no full-screen takeover, no sound without consent); works without our cookies (token from the host).

## 8. QA additions for apps

- Walk every flow as a first-time user on a 360 px phone with touch sizes forced: sign up to the first success.
- Test every state in section 4 by forcing it (empty account, failed request, locked role).
- Keyboard only: every action reachable, focus visible, side panels trap and return focus.
- Lighthouse on the production build of signed-in pages (use a preview session or the preview mode), plus axe.
- Check numbers in tables line up (tabular figures) and long names and amounts do not break rows at 320 px.

## 8b. Type for data-dense screens

One scale for every app screen of a product (consoles of the same company must match). A good default, in the brand's
text face:

| Role | Size / line | Weight |
|---|---|---|
| Page title | 28/34 (24/32 if dense) | the brand's headline weight |
| Section title | 18/26 | 600 |
| Panel or card title | 16/24 | 600 |
| Body and prose (max about 70 characters a line) | 15/24 or 14/20 | 400 |
| Table cell | 14/20 (13/20 if dense) | 400 |
| Table header | 12/16, sentence case, muted (not tiny uppercase with wide tracking) | 600 |
| Labels and buttons | 14/20 | 500 and 600 |
| Help, meta, captions | 13/18, never below 12 | 400 |
| Big numbers | 32/38 | 600 |

- Muted text must pass 4.5:1 on every background it sits on, including tinted panels; check the darkest tint.
- Numbers right-aligned. Ask for `font-variant-numeric: tabular-nums`, but test it: some web fonts (and Google Fonts
  subsets) have no tabular figures, and then only alignment keeps columns tidy.
- Variable fonts with an optical-size axis: load the axis (for example `axes: ["opsz"]` in next/font) and keep
  `font-optical-sizing: auto`.
- Rows about 44 px (cell padding 12 px 16 px); a side panel about 400 px wide.

## 8c. Interaction and state behaviour

- Filters, tabs and the open panel or case live in the URL, so refresh, Back and a shared link keep them.
- A loading state never shows the empty state first ("Nothing is waiting" flashing before the data arrives is a bug).
  Delay spinners about 200 ms so fast loads do not flicker.
- After an action, say what happened and link to the result ("Finished: passed to an agent. Open the call").
- New items in a live queue are announced to screen readers (`aria-live="polite"`).
- Sticky headers, bottom bars and widget launchers never cover the focused element.
- Stress-test every list with very long names and big amounts at 320 px.
- One primary action per view: the empty state does not repeat the header's button.
- Never show internal IDs to the people the product talks to (a voice or chat agent reading "esc_sbx_rs" aloud).

## 9. Keep this file growing

After building a new kind of app (marketplace, editor, analytics, mobile app, game UI), add a section here or a
new reference file with what was learned and the corrections the product owner made. Link it from SKILL.md under
"Application types".
