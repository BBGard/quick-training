# QuickTraining

A single-page web app that generates short, equipment-aware workouts, stretch sessions, and full weekly training plans — built for people who only have 10–40 minutes to train.

No build step, no backend, no dependencies. It's one self-contained `index.html` file you can open locally or host anywhere for free.

## Features

**Generate**
- **Workout** — pick a time budget (10–45 min), available equipment (dumbbells / bodyweight / bands), and a focus (full body, upper, lower, pull + core, push + conditioning). Builds a warm-up, superset pairs, and a finisher scaled to fit your time.
- **Stretch** — pick a time budget (5–30 min) and a focus area (neck & shoulders, back, hips & glutes, legs, or full body).
- **Weekly Plan** — pick days per week (3–6), time per session, equipment, and whether to include a dedicated stretch/mobility day. Focus rotates automatically across the week so you're not hitting the same muscles back-to-back.

Every "Generate" click reshuffles the exercise pool for variety, prioritizing your favorites and skipping anything you've excluded.

**Manage**
- Browse every exercise and stretch in the library (search + filter by equipment/favorites/excluded).
- **★ Favorite** an exercise to have it prioritized whenever it fits a session.
- **✕ Exclude** an exercise to remove it from generation entirely (e.g. an injury, or one you just don't like).
- **Info button** on every exercise (in Manage and in any generated session) opens a plain-language how-to description.

**Save & organize**
- Save any generated Workout, Stretch session, or Weekly Plan under a custom name.
- The **Saved** tab organizes everything into three sections: Weekly Plans, Workouts, Stretches. Expand a card to see the full breakdown, or delete it.
- **Build a plan from saved sessions**: on any saved Workout or Stretch card, hit **+ Add to Plan** to slot it into a new or existing saved Weekly Plan under a day label of your choice — a fully manual way to assemble a week from sessions you already like.

**Data & portability**
- Favorites, exclusions, and saved sessions autosave as you go.
- **Export/Import** (in the Manage tab) lets you back up your favorites/exclusions to a `.json` file or move them to another browser/device.

## Tech

Plain HTML, CSS, and vanilla JavaScript in one file — no frameworks, no build tools, no external JS libraries. Fonts are loaded from Google Fonts via CDN; everything else runs client-side.

## Customizing

- **Exercise library**: all exercises and stretches live in the `STRENGTH` and `STRETCHES` arrays near the top of the `<script>` block, each with a name, equipment tag(s), muscle group, and a how-to description (`d` field).
- **Colors/theme**: CSS custom properties (`--bg`, `--ink`, `--accent`, etc.) are defined once at the top of the `<style>` block.
- **Focus rotation logic** for workouts and weekly plans lives in `FOCUS_GROUPS` and `generateWeeklyPlan()`.
