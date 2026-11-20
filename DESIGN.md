---
name: "AgentHub Admin System"
description: "Crisp, high-legibility enterprise SaaS design system for AgentHub's AI agent rental and operations console, supporting seamless light and dark themes."
---

## Overview

AgentHub is a B2B SaaS platform where companies rent preconfigured AI agents equipped with modular skills. The administrative console is built for operations leads, support engineers, and platform administrators who monitor revenue, manage client accounts, inspect agent system prompts, audit skill catalogs, track rental contracts, and triage runtime execution errors.

The visual direction is **Corporate / Modern** with a technical precision edge: high-contrast typography, tonal surface layering, crisp 1px structural borders, and restrained semantic color coding reserved strictly for operational states (active, inactive, warning, failing, resolved). Both light and dark modes are first-class citizens, switching cleanly via Tailwind's `dark:` utilities.

- **Iconography:** Use crisp, uniform-stroke inline `<svg>` icons (`1.75` stroke width, `20px` or `16px` viewBox) rather than icon fonts or `<style>` blocks, keeping the UI self-contained and free of custom CSS.
- **No custom CSS:** Rely exclusively on Tailwind CSS utility classes and design tokens. Never add `<style>` blocks or inline `style` attributes.

## Colors

The palette anchors on a deep cobalt-indigo primary (`#2A14B4` in light mode, `#C3C0FF` in dark mode) paired with cool slate-tinted neutrals and dedicated semantic status tokens (`success`, `warning`, `error`) for operational clarity across tables, badges, and logs.

- **Primary:** Used for active navigation indicators, primary actions, focus rings, and key interactive controls.
- **Surfaces & Containers:** Tonal steps separate the persistent sidebar, top bar, main canvas, cards, and modal dialogs without heavy drop shadows.
- **Semantic Status:** `success` (active/resolved), `warning` (degraded/rate-limit/past), and `error` (failing/critical) are used strictly for state badges, indicators, and alert surfaces—never decoratively.

```yaml
colors:
  light:
    primary: "#2A14B4"
    on-primary: "#FFFFFF"
    primary-container: "#4338CA"
    on-primary-container: "#FFFFFF"
    secondary: "#5A5893"
    on-secondary: "#FFFFFF"
    secondary-container: "#E3DFFF"
    on-secondary-container: "#2C2961"
    tertiary: "#692400"
    on-tertiary: "#FFFFFF"
    tertiary-container: "#FFDBCD"
    on-tertiary-container: "#591D00"
    success: "#15803D"
    on-success: "#FFFFFF"
    success-container: "#DCFCE7"
    on-success-container: "#14532D"
    warning: "#B45309"
    on-warning: "#FFFFFF"
    warning-container: "#FEF3C7"
    on-warning-container: "#78350F"
    error: "#BA1A1A"
    on-error: "#FFFFFF"
    error-container: "#FFDAD6"
    on-error-container: "#93000A"
    background: "#FCF8FF"
    on-background: "#1B1B23"
    surface: "#FCF8FF"
    surface-dim: "#DCD8E4"
    surface-bright: "#FCF8FF"
    surface-container-lowest: "#FFFFFF"
    surface-container-low: "#F6F2FE"
    surface-container: "#F0ECF8"
    surface-container-high: "#EAE6F3"
    surface-container-highest: "#E4E1ED"
    on-surface: "#1B1B23"
    surface-variant: "#E4E0F3"
    on-surface-variant: "#464554"
    outline: "#777586"
    outline-variant: "#C7C4D7"
    inverse-surface: "#302F39"
    inverse-on-surface: "#F3EFFB"
    inverse-primary: "#C3C0FF"
  dark:
    primary: "#C3C0FF"
    on-primary: "#1F00A4"
    primary-container: "#4338CA"
    on-primary-container: "#FFFFFF"
    secondary: "#C3C0FF"
    on-secondary: "#2C2961"
    secondary-container: "#42407A"
    on-secondary-container: "#E3DFFF"
    tertiary: "#FFB597"
    on-tertiary: "#591D00"
    tertiary-container: "#8F3400"
    on-tertiary-container: "#FFDBCD"
    success: "#4ADE80"
    on-success: "#052E16"
    success-container: "#14532D"
    on-success-container: "#DCFCE7"
    warning: "#FBBF24"
    on-warning: "#451A03"
    warning-container: "#78350F"
    on-warning-container: "#FEF3C7"
    error: "#FFB4AB"
    on-error: "#690005"
    error-container: "#93000A"
    on-error-container: "#FFDAD6"
    background: "#13121B"
    on-background: "#E4E1ED"
    surface: "#13121B"
    surface-dim: "#13121B"
    surface-bright: "#393842"
    surface-container-lowest: "#0E0D15"
    surface-container-low: "#1B1B23"
    surface-container: "#1F1F27"
    surface-container-high: "#2A2932"
    surface-container-highest: "#35343D"
    on-surface: "#E4E1ED"
    surface-variant: "#464554"
    on-surface-variant: "#C7C4D7"
    outline: "#918FA0"
    outline-variant: "#464554"
    inverse-surface: "#E4E1ED"
    inverse-on-surface: "#302F39"
    inverse-primary: "#5148D7"
```

## Typography

A technical, highly legible pairing: **Red Hat Text** for section headings and KPI figures, **Instrument Sans** for dense table rows, navigation, and modal copy, and **Red Hat Mono** for timestamps, error stack traces, agent IDs, and system prompts.

All numeric figures, currency amounts, dates, and timestamps use `tabular-nums` so columns align cleanly.

```yaml
typography:
  display-md:
    fontFamily: "Red Hat Text"
    fontSize: 36px
    fontWeight: 700
    lineHeight: 44px
    letterSpacing: -0.5px
  display-md-mobile:
    fontFamily: "Red Hat Text"
    fontSize: 28px
    fontWeight: 700
    lineHeight: 36px
    letterSpacing: -0.25px
  headline-lg:
    fontFamily: "Red Hat Text"
    fontSize: 24px
    fontWeight: 600
    lineHeight: 32px
    letterSpacing: -0.25px
  headline-md:
    fontFamily: "Red Hat Text"
    fontSize: 20px
    fontWeight: 600
    lineHeight: 28px
    letterSpacing: -0.15px
  title-md:
    fontFamily: "Red Hat Text"
    fontSize: 16px
    fontWeight: 600
    lineHeight: 24px
    letterSpacing: 0px
  body-md:
    fontFamily: "Instrument Sans"
    fontSize: 14px
    fontWeight: 400
    lineHeight: 20px
    letterSpacing: 0px
  body-sm:
    fontFamily: "Instrument Sans"
    fontSize: 13px
    fontWeight: 400
    lineHeight: 18px
    letterSpacing: 0px
  label-lg:
    fontFamily: "Instrument Sans"
    fontSize: 14px
    fontWeight: 500
    lineHeight: 20px
    letterSpacing: 0px
  label-sm:
    fontFamily: "Instrument Sans"
    fontSize: 12px
    fontWeight: 500
    lineHeight: 16px
    letterSpacing: 0.2px
  mono-sm:
    fontFamily: "Red Hat Mono"
    fontSize: 12px
    fontWeight: 400
    lineHeight: 18px
    letterSpacing: 0px
```

## Layout & Spacing

Desktop-first administrative shell (`1280px+` primary target, remaining usable on narrower viewports):
- **Persistent Left Sidebar:** Fixed `256px` width on desktop (`w-64`), holding brand mark, 6 primary navigation items, and environment indicator.
- **Top Bar:** `64px` height (`h-16`) holding current section title, search/context summary, and the light/dark theme toggle.
- **Main Content Area:** Fluid workspace with `24px`–`32px` padding and a `4px`/`8px` spacing scale.

```yaml
spacing:
  gutter-xs: 4px
  gutter-sm: 8px
  gutter-md: 16px
  gutter-lg: 24px
  gutter-xl: 32px
  section: 40px
  page-margin: 24px
```

## Elevation & Depth

Hierarchy relies on **tonal surface steps** and **1px low-contrast outlines** (`outline-variant`) rather than heavy drop shadows. Elevated overlays—action dropdown menus and detail modals—use `surface-container-lowest` (light) or `surface-container-high` (dark) with a crisp 1px border and subtle ambient shadow (`shadow-lg`) to separate from the dimmed backdrop.

## Shapes

Structured, geometric corners keep the enterprise console crisp: `8px` default for buttons and inputs, `12px` for cards and data tables, `16px` for modal dialogs, and `9999px` (pill) for status badges and skill chips.

```yaml
rounded:
  sm: 4px
  DEFAULT: 8px
  md: 12px
  lg: 16px
  xl: 24px
  full: 9999px
```

## Motion & Micro-interaction

Transitions are crisp and functional, respecting `prefers-reduced-motion`. Dropdowns and modals fade/scale cleanly, and agent skill lists expand/collapse smoothly using `transition-all duration-200 ease-out` or `grid-rows` transitions without jarring jumps.

```yaml
motion:
  state-change:
    duration: 150ms
    delay: 0ms
    timingFunction: ease-out
  surface-enter:
    duration: 200ms
    delay: 0ms
    timingFunction: cubic-bezier(0.2, 0, 0, 1)
  surface-exit:
    duration: 150ms
    delay: 0ms
    timingFunction: cubic-bezier(0.3, 0, 1, 1)
```

## Voice & Content Strategy

- **Language:** All UI copy, headings, table headers, badges, and sample data are written in clear, professional Spanish (`es`).
- **Tone:** Direct, operational, and concise. Action labels use clear verbs (*Ver detalle*, *Configurar*, *Marcar como resuelto*, *Eliminar*, *Marcar como devuelto*).
- **Formatting:** Currency uses USD (`$12,480.00`), dates use `YYYY-MM-DD` or `DD MMM YYYY`, and timestamps use ISO-style `YYYY-MM-DD HH:mm:ss` in monospace.

## Components

Component implementations live as individual HTML sticker sheet files in
`components/`. Each file contains the canonical, styled HTML components with
`<!-- COMPONENT: name -->` comment markers. Read each file before use.

- **Badge** → `@components/badge.html`: `badge-numeric`, `badge-dot`
- **Button** → `@components/button.html`: `button-primary`, `button-icon`, `button-with-icon`
- **Card** → `@components/card.html`: `card-elevated`, `card-action`, `card-interactive`, `card-interactive-2`
- **Modal** → `@components/modal.html`: `modal-standard`, `modal-alert`, `modal-drawer`
- **Table** → `@components/table.html`: `table-standard`, `table-interactive`, `table-selectable`
