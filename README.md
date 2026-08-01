# Privacy Policy — DevUnlock (Chrome extension)

**Last updated: August 1, 2026**

DevUnlock is a Chrome extension that lets a developer keep Chrome DevTools open on one specific site without that page ending their session. This document describes exactly what the extension does and does not do with data.

Rendered version: <https://walle-go.github.io/devtools-unlock-privacy/>

## Summary

**DevUnlock does not collect, transmit, sell, or share any user data.** There is no server, no analytics, no telemetry, and no network request of any kind originating from this extension.

## Data we collect

None.

The extension collects none of the following: personally identifiable information, health information, financial or payment information, authentication information, personal communications, location, web history, or user activity. It does not read page content, form values, or cookies, and it has no access to any site beyond the single one declared in its manifest.

## Data stored on your device

The extension keeps one optional diagnostic log in your own browser's `localStorage`, under the key `__du_log`, on that site's origin only. It is a ring buffer capped at 200 entries and it never leaves your computer.

Each entry records only non-identifying technical facts about a page load, so that unexpected sign-outs can be diagnosed:

- the type of event (page load, sweep, sign-out page reached, page unload)
- the page URL within that same site
- whether the DevTools window appeared to be docked, derived from the window's inner/outer size difference
- timing values and timer id counts

You can view this log at any time by running `JSON.parse(localStorage.__du_log)` in the console, and erase it by appending `#du-clear-log` to the URL and reloading. Removing the extension and clearing that site's data also erases it.

## Permissions

The extension declares no Chrome permissions at all. Its only access is a content script matched to the single site named in its manifest, which is required for its single purpose: stopping the page's repeating DevTools-detection timer.

## Remote code

The extension executes no remotely hosted code. All of its logic is contained in the single `guard.js` file included in the published package.

## Changes to this policy

Any change to this policy will be published in this repository.

## Contact

Questions about this policy: open an issue at <https://github.com/walle-go/devtools-unlock-privacy/issues>.
