# Life in Weeks

A single-file web app that draws a life as a grid of weeks — and lets anyone
build their own.

Enter a date of birth and an expected lifespan, add **periods** (school, a
job, a city, an era) and **milestones** (the moments that tether them), and
the grid renders itself: periods colour their weeks, each period's start and
end are outlined in the same colour, milestones land as dots, and the current
week is highlighted. Hover or tap any week for its dates, your age then, and
everything that week contains.

The lifespan can be typed in directly — or estimated **from lifestyle**:
pick a baseline (the default 79 is US life expectancy at birth, 2024, with an
optional sex adjustment) and set sixteen factors in three groups — **Habits**
(smoking, exercise, strength training, diet, alcohol, sleep duration, sleep
regularity), **Body & health** (body weight, blood pressure, chronic
condition, mental health), and **Life context** (social ties, partnership,
education, income, family longevity). Each carries a delta pooled from large
cohort studies and meta-analyses — approximate, and a few are associations
rather than proven causes. Two overlapping pairs (exercise + strength,
social ties + partnership) are capped instead of summed, and the estimate is
floored at your current age, so the grid never ends before the life already
lived. What you choose is which description fits your life, and the grid
grows or shrinks as you explore. The calendar is the point; the estimate is
a companion, not the headline.

## Run it

Open `index.html` in any browser. That's it — no build step, no dependencies,
no server.

## Design conventions

- **Periods are base colour.** A period fills its weeks; it never tints or
  overlays them.
- **Start and end take the period colour**, with a bold contrasting outline,
  so a chapter's edges read at a glance.
- **The key is minimal**: one swatch and a bare name per period. All detail
  lives in the week card on hover/tap.

## Data

Everything is stored in the browser's localStorage — nothing is sent anywhere.
Export/import moves a life between browsers as a small JSON file.

## Tech

Vanilla HTML/CSS/JS on a `<canvas>` grid (52 weeks per row, one row per year).
Zero dependencies, one file, ~36 KB.
