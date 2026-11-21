# Next-regen spec — native menus (Steven's direction, 2026-11-21)

When the Arcade package is next regenerated (packages regen only when Steven
calls for it), give it the same native menu bar as the main Everyday Cool app
(File | Help — see everyday-cool-app/src-tauri/src/main.rs), adapted:

## File menu
- Clear Cache (same cure as the main app's v1.1.6 item)
- Exit
(The main app's user items — Current User / Switch User / Add User — are
main-app-only: the Arcade keeps no per-user data.)

## Help menu
- **Game Documents** — opens an HTML page (bundled with the app, e.g.
  interface/documents.html) linking to the lesson document of EVERY game in
  the Arcade: all lessons from tools/games.manifest, kept in step with the
  manifest at each regen. Stack-a-Bot is listed honestly as "lesson in the
  works" until it has one. This page is the Arcade's documentation — a
  teacher holding the package should reach every game's back-door document
  from one menu item.
- GitHub Repository (the arcade repo)
- About (name, version)

## Notes
- The documents page must be generated from the manifest at sync time, not
  hand-maintained, so a newly added game brings its document link with it.
- Menu wiring follows the main app's pattern (on_menu_event in main.rs);
  document links open inside the app window like the lessons already do,
  external links (GitHub) go to the system browser via the opener.
