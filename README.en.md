# YouTube Playlist Watch Plan

Turn a visible YouTube playlist into a read-only daily watch-plan draft. It returns the original order, visible durations, daily time budget, source links, and explicit missing information; it never guesses hidden durations or changes your library or queue.

![Promo](assets/promo.png)

## Input and output

Provide a playlist URL, minutes available per day, and one user-selected Easy WebBridge `browserId`. The Skill reads at most ten visible items per run.

It returns a Markdown table with each item's order, title, visible duration, suggested day, source URL, confirmed total, and unresolved fields. Restricted, private, login-gated, CAPTCHA, or no-duration content is reported as missing rather than estimated.

## Install

```bash
npx skills add xxjrq/youtube-playlist-watch-plan-free
```

## Browser prerequisite

Install [Easy WebBridge from GitHub](https://github.com/xxjrq/easy-webbridge), or use the [Gitee mirror](https://gitee.com/xxjrq/easy-webbridge). A run uses exactly one supplied `browserId`, creates one task-owned tab group, and only closes that group. It never broadcasts across accounts or takes over existing tabs.

Offline fixtures in this repository are page-data simulations, not live collection results. Run `node scripts/self-test.mjs` for the standalone structural check.
