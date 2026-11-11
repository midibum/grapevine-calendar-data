# Grapevine Community Calendar — page backup

This folder holds a backup copy of the calendar website's own pages, so the
site can be rebuilt even if the files on the GoDaddy server are lost.

- `index.html` — the live calendar page (the file that runs grapevinecalendar.com).
  Last updated 2026-11-09, 131,757 bytes. The page loads its events from
  `events.json` in this same repo, so restoring this one file brings the
  calendar itself back.
- `links.html` — the link-in-bio page at grapevinecalendar.com/links.html
  (the link in the Whittington Station TikTok bio).
- `events.json` (repo root) — the live event list. `photos/` (repo root) —
  every event photo. GitHub keeps every version of these files, so a bad
  upload can be rolled back from the repo's history.

## How to restore the site if it goes down

1. Log in to GoDaddy, open the ericcoard.com cPanel, then File Manager.
2. Go to public_html, then grapevinecalendar.com. Do NOT delete anything first.
3. Upload the `index.html` from this folder. It overwrites the one on the
   server. (Same for `links.html` if that page is the problem.)
4. Wait a minute, then open https://grapevinecalendar.com and check the
   events show up. If they don't, the problem is the event data, not the
   page — see the recovery runbook in the Whittington Station workspace
   (grapevine-calendar-recovery-runbook.md).

## What is NOT backed up here

- The domain name (grapevinecalendar.com) and its SSL certificate live in
  GoDaddy, not in this repo. Keep the domain on auto-renew with a current
  card, and keep the SSL on auto-renew.
- The "Submit an Event" form is a Wufoo form (midibum.wufoo.com). If the
  form stops working, the calendar still works; only new submissions stop.
