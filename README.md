# streakpy: Norwegian practice automation experiment

streakpy is a Python browser-automation experiment for a Norwegian Duolingo practice lesson. It combines Pyppeteer, browser-based translation lookup, and a local cache of corrected answers.

## 1. How it works

The application opens separate lesson and translator pages. It reads supported translation prompts, uses the configured exception answer when one exists, and otherwise looks up a translation. When a correction appears, it records the expected answer in the language configuration for future runs.

Supported speaking and listening prompts are skipped when their skip controls are available. The script writes `realtime.png` during progress and removes it when the normal completion path finishes.

## 2. Requirements and configuration

Python 3 and Pyppeteer are required. The only included course configuration is `languages/Norwegian.json`, containing the practice URL, language name, translation code, and exception mappings.

The current application reads local credentials from `auth/username` and `auth/password`. The `auth/` directory is ignored by Git; keep those files local.

## 3. Project status

The repository contains a single-run lesson workflow, with no built-in scheduling or verification that a daily streak was recorded.
