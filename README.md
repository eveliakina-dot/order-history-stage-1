# Order History, Stage 1: Test Steps from the Requirement Card

⌨️ **Stage 1 of 4.** Over the next four lessons you build the test boilerplate for one TechShop feature, order history, the way the module taught it: Claude drafts, you decide, you deliver. Everything lands in one repository, and every stage gets a code review with comments on your lines.

Stage 1 is the foundation. The test steps you deliver here are what the page object in the next stage will be generated from — so a sloppy step now is a sloppy method later.

**You'll need:** a fork of `order-history-stage-1` (link below) · `requirements/TECH-342-order-history.md` · `conventions/test-step-template.md` · `prompts/01-test-steps.md` · `samples/tech-318-*` · a new Claude conversation.

**How the review works.** You submit your repo; an AI reviewer reads it and comments on specific lines. 🔴 means fix it and resubmit; 🟡 is a suggestion; 🟢 is praise. On the first pass it tells you *what* is wrong, not how to fix it. That part is yours.


### The card

Open `requirements/TECH-342-order-history.md` and read all of it — description, every AC, the out-of-scope list. Here it is for reference; the file is the source.

```
📋 TECH-342 — Order history

Description:
Registered users can see a list of their past orders, filter it by status and by
date range, and open any order to view its details. The list is paginated, 10
orders per page, newest first.

Acceptance criteria:
AC-1  On the account page, clicking "Order history" navigates the user to the
      order-history page, which lists the user's orders newest first with order
      number, date, status and total for each.
AC-2  The list shows 10 orders per page; when the user has more than 10 orders,
      pagination controls appear and the user can move between pages.
AC-3  Selecting a status in the status filter and clicking "Apply" shows only
      orders with that status; the status filter offers all statuses.
AC-4  Entering a date range and clicking "Apply" shows only orders placed within
      that range, inclusive.
AC-5  Clicking "View details" on an order opens that order's details page.
AC-6  A user with no orders sees an empty-state message with a link to the
      catalogue.

Out of scope:
- Guest (not logged-in) users
- Downloading invoices
- Reordering from history
```



### 1. Decide before you generate

Three questions, answered in `review-notes.md › Stage 1 › Before generating`, 3–5 lines total:
- Which AC assumes something it doesn't say — the condition a word-for-word conversion would drop?
- Which AC names something the card never defines, so any concrete value you'd put in a step is a guess?
- Which AC is a boundary, where the interesting test lives at the edge?

This is the part the model can't do. It's also the first thing the reviewer reads.

### 2. Let Claude draft it

New conversation. Paste `prompts/01-test-steps.md` with the full card in the slot. Don't add hints about what you found. Send.

Save the whole exchange, untouched, as `claude-runs/01-test-steps.md`.

### 3. Review the draft

Four criteria, one pass per criterion: **complete** (every AC has a step) · **precise** (two testers would do the same thing) · **testable** (the expected result can be seen) · **traceable** (every step names its AC).

Three mistakes to expect from a model: two ACs merged into one step; a precondition with no test data ("user has orders"); a sensible step that traces to no AC at all.

Every finding goes in `Stage 1 › Defects found`: *draft line · criterion · what I changed*. Clean on a criterion? Say how you checked — "six ACs, six steps, counted" is a check.

### 4. Deliver

`tests/steps/TECH-342.md`, one or more steps per AC, in the fixed template:

```
Test Step [number]
  Source AC:        [AC tag(s)]
  Precondition:     [state before the action]
  Action:           [one precise action]
  Expected Result:  [something you can observe]
```

Concrete data in every step — an order number, a date, a status — never "a valid order". Where the card leaves something open, write `[⚠ AMBIGUOUS: …]` rather than guessing. Nothing you flagged in step 3 survives into this file.

### 5. Control pass

`samples/tech-318-ai-draft.md` is a model's steps for a different card (`samples/tech-318-password-reset.md`). It has all three of the mistakes above. Find them; list them in `Stage 1 › Control pass` as *step · criterion · what's wrong*. No rewrite.

### 6. One sentence

`Stage 1 › Hardest call`: which AC was the hardest to convert, and what would a literal conversion of it miss? Naming the AC isn't the answer; saying what gets dropped is.

### Submit

Commit, push, submit the repo link. The reviewer reads `tests/steps/TECH-342.md`, `claude-runs/01-test-steps.md` and your Stage 1 notes.

### ✅ Before you submit

- `claude-runs/01-test-steps.md` — exact prompt, full response, untouched
- Notes › Before generating — implicit condition, undefined value, boundary: named
- `tests/steps/TECH-342.md` — every AC covered; fixed template; concrete data; every step has a Source AC; open points flagged, not guessed
- Notes › Defects found — draft line · criterion · change; each fixed in the file
- Notes › Control pass — the three mistake types found in the sample
- Notes › Hardest call — one AC, and what a literal conversion drops
