---
name: Obsidian Kinetic
colors:
  surface: '#0f131c'
  surface-dim: '#0f131c'
  surface-bright: '#353942'
  surface-container-lowest: '#0a0e16'
  surface-container-low: '#181c24'
  surface-container: '#1c2028'
  surface-container-high: '#262a33'
  surface-container-highest: '#31353e'
  on-surface: '#dfe2ee'
  on-surface-variant: '#c2c6d6'
  inverse-surface: '#dfe2ee'
  inverse-on-surface: '#2c3039'
  outline: '#8c909f'
  outline-variant: '#424754'
  surface-tint: '#adc6ff'
  primary: '#adc6ff'
  on-primary: '#002e6a'
  primary-container: '#4d8eff'
  on-primary-container: '#00285d'
  inverse-primary: '#005ac2'
  secondary: '#a4c9ff'
  on-secondary: '#00315d'
  secondary-container: '#0267b8'
  on-secondary-container: '#d6e5ff'
  tertiary: '#7bd0ff'
  on-tertiary: '#00354a'
  tertiary-container: '#009bd1'
  on-tertiary-container: '#002d40'
  error: '#ffb4ab'
  on-error: '#690005'
  error-container: '#93000a'
  on-error-container: '#ffdad6'
  primary-fixed: '#d8e2ff'
  primary-fixed-dim: '#adc6ff'
  on-primary-fixed: '#001a42'
  on-primary-fixed-variant: '#004395'
  secondary-fixed: '#d4e3ff'
  secondary-fixed-dim: '#a4c9ff'
  on-secondary-fixed: '#001c39'
  on-secondary-fixed-variant: '#004883'
  tertiary-fixed: '#c4e7ff'
  tertiary-fixed-dim: '#7bd0ff'
  on-tertiary-fixed: '#001e2c'
  on-tertiary-fixed-variant: '#004c69'
  background: '#0f131c'
  on-background: '#dfe2ee'
  surface-variant: '#31353e'
typography:
  headline-xl:
    fontFamily: Inter
    fontSize: 36px
    fontWeight: '700'
    lineHeight: 44px
    letterSpacing: -0.025em
  headline-xl-mobile:
    fontFamily: Inter
    fontSize: 28px
    fontWeight: '700'
    lineHeight: 36px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Inter
    fontSize: 28px
    fontWeight: '600'
    lineHeight: 36px
    letterSpacing: -0.02em
  headline-lg-mobile:
    fontFamily: Inter
    fontSize: 22px
    fontWeight: '600'
    lineHeight: 28px
    letterSpacing: -0.015em
  headline-md:
    fontFamily: Inter
    fontSize: 20px
    fontWeight: '600'
    lineHeight: 28px
    letterSpacing: -0.015em
  title-md:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '600'
    lineHeight: 24px
    letterSpacing: -0.01em
  body-lg:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
    letterSpacing: 0em
  body-md:
    fontFamily: Inter
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
    letterSpacing: 0em
  body-sm:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '400'
    lineHeight: 16px
    letterSpacing: 0.01em
  label-md:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '500'
    lineHeight: 16px
    letterSpacing: 0.02em
  label-sm:
    fontFamily: Inter
    fontSize: 11px
    fontWeight: '600'
    lineHeight: 14px
    letterSpacing: 0.04em
  code-sm:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '500'
    lineHeight: 16px
    letterSpacing: -0.01em
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  gutter: 1rem
  gutter-desktop: 1.5rem
  margin: 1rem
  margin-tablet: 1.5rem
  margin-desktop: 2rem
  space-xs: 0.25rem
  space-sm: 0.5rem
  space-md: 1rem
  space-lg: 1.5rem
  space-xl: 2rem
  space-2xl: 3rem
---

## Brand & Style

The design system projects a high-density, mission-critical workspace tailored for orchestrating autonomous AI agents, complex runtime pipelines, and systemic workflows. It communicates structural precision, high operational velocity, and technical authority. The aesthetic targets engineers, machine learning operators, and system architects who require rapid situational awareness and low optical fatigue across long working sessions.

The design philosophy combines **Technical Minimalism** with **Cybernetic Utilitarianism**. Surfaces mimic deep space and milled obsidian substrates, accented by precise, luminescent conduits of light. Visual structures leverage ultra-fine grid structures, meticulous mathematical contrast ratios, and controlled, directional radiance rather than heavy decorative skeuomorphism. The interface creates an atmosphere of deep focus, clarity, and instant feedback.

## Colors

The palette is engineered specifically for deep-field dark mode visualization, avoiding true black (#000000) to mitigate halation while using tinted obsidian and slate tones to preserve depth perception.

### Base Canvas & Surfaces
- **Canvas Base (`#0B0F17`):** The primary application canvas layer. Absorbent, low-reflectance obsidian navy.
- **Card Surface Default (`#111827`):** Base structural container level providing optical separation from the background canvas.
- **Card Surface Elevated (`#1E293B`):** Interactive containers, modals, hover states, and layered sub-panels.

### Accents & Primaries
- **Primary Electric Blue (`#3B82F6`):** The dominant action color for primary CTAs, active operational indicators, and pipeline execution flows.
- **Electric Blue Focus/Hover (`#60A5FA`):** High-energy hover tier, focused states, and luminous typography links.
- **Tertiary Cyan Glow (`#38BDF8`):** Data metrics, active telemetry streams, and dynamic compute gauges.

### Structural Borders & Dividers
- **Subtle Surface Border (`#1F2937`):** Primary panel containment border, maintaining structure without visual clutter.
- **Interactive/Hover Border (`#334155`):** Structural highlight used on hovered cards, focused inputs, and divider lines.

### Semantic Status Palette
- **Success (`#4ADE80`):** Agent operational, job completed, node healthy. Paired with alpha-tinted fill `rgba(74, 222, 128, 0.12)`.
- **Warning / Degraded (`#FBBF24`):** Memory threshold near limit, throttled rate, retry state. Paired with alpha-tinted fill `rgba(251, 191, 36, 0.12)`.
- **Critical / Failure (`#F87171`):** Execution halted, agent dead-letter, API timeout. Paired with alpha-tinted fill `rgba(248, 113, 113, 0.12)`.
- **Neutral Status / Inactive (`#94A3B8`):** Idle runtime, queued execution, disabled module. Paired with alpha-tinted fill `rgba(148, 163, 184, 0.12)`.

## Typography

The type hierarchy uses **Inter** across all functional tiers to maintain mechanical legibility across complex operational logs, node parameter sheets, and dense metric arrays.

- **Numerics & Tabular Lining:** All tabular figures, node latency counters, and token budgets must leverage `font-feature-settings: "tnum" 1, "cv05" 1` to prevent jitter during live data updates.
- **Hierarchy Rules:** High-contrast text levels (`#F8FAFC` for headlines, `#E2E8F0` for body) establish rapid scanning paths, while secondary annotations drop to `#94A3B8` and tertiary timestamps drop to `#64748B`.
- **Labels & Badges:** `label-sm` utilizes subtle tracking expansion (+0.04em) and uppercase formatting for status pills, agent operational states, and environment badges.

## Layout & Spacing

The layout model runs on a disciplined **8-point spatial grid** combined with a 4-point baseline sub-grid for compact inspector panels.

### Structural Grids
- **Desktop (≥1280px):** 12-column fluid grid with 1.5rem (`24px`) gutters and 2rem (`32px`) margins. Shell layout accommodates an iconized/expanded collapsible agent navigation tree (260px fixed width) paired with a contextual dynamic inspector drawer (360px fixed width).
- **Tablet (768px - 1279px):** 8-column layout with 1rem (`16px`) gutters and 1.5rem (`24px`) margins. Sidebar collapses to a persistent rail (64px width); inspector folds into an overlay sheet.
- **Mobile (<768px):** 4-column layout with 1rem (`16px`) gutters and 1rem (`16px`) margins. Sidebars transition to full-width bottom navigation sheets and slide-out drawers.

### Spacing Application
- Use `space-xs` (4px) and `space-sm` (8px) for internal input group grouping, badge padding, and icon-to-label separation.
- Use `space-md` (16px) for standard panel padding and internal component item separations.
- Use `space-lg` (24px) for card interiors and stacked operational groups.
- Use `space-xl` (32px) and `space-2xl` (48px) exclusively for dashboard section demarcation.

## Elevation & Depth

Visual hierarchy does not rely on ambient daylight drop-shadows. Depth is built via **tonal stacking**, **luminescent border gating**, and **directional micro-shadows**.

### Surface Elevation Levels
- **Level 0 (Canvas Base):** Surface color `#0B0F17`. Deepest operational plane; hosts empty canvas grids and workflow orchestrator graphs.
- **Level 1 (Docked Containers & Grid Cards):** Surface color `#111827`, bordered by 1px solid `#1F2937`. Base cards, code editors, and metric tiles.
- **Level 2 (Hovered Cards & Interactive Controls):** Surface color `#1E293B`, bordered by 1px solid `#334155`. Box-shadow: `0 4px 20px -2px rgba(0, 0, 0, 0.5)`.
- **Level 3 (Flyouts, Menus & Tooltips):** Surface color `#1E293B`, bordered by 1px solid `#3B82F6` (at 40% opacity). Box-shadow: `0 10px 30px -4px rgba(0, 0, 0, 0.7), 0 0 15px 0 rgba(59, 130, 246, 0.1)`.
- **Level 4 (System Overlays & Critical Prompts):** Surface color `#111827`, bordered by 1px solid `#475569`. Backdrop-filter: `blur(8px) saturate(180%)`, background-color: `rgba(11, 15, 23, 0.8)`.

### Border Lighting Technique
Cards and surfaces incorporate a top-edge ambient highlight to mimic physical hardware chamfers:
- Apply an inset linear border or simulated border gradient fading from `#334155` at the top edge to `#1F2937` at the bottom edge.
- When focused or targeted by live agent execution, the border transitions instantaneously to `#3B82F6` with a soft outer glow (`box-shadow: 0 0 12px rgba(59, 130, 246, 0.25)`).

## Shapes

The design system adopts a balanced **Rounded (`roundedness: 2`)** paradigm optimized for dense technical consoles.

- **Base Radius (0.5rem / `8px`):** Used on all standard buttons, text fields, menu containers, chips, and table line selection states.
- **Large Radius (`rounded-lg`, 1rem / `16px`):** Applied to telemetry cards, main viewport agent execution panels, workflow editor nodes, and modal containers.
- **Pill Radius (Full / `9999px`):** Reserved strictly for semantic runtime badges, live agent pulse monitors, and quick-filter tag items.
- **Sharp Edge Exceptions:** Code block wrappers, execution log terminal frames, and graph node connection ports utilize a micro-radius of 0.25rem (`4px`) to preserve structural alignment.

## Components

### Buttons
- **Primary:** Background `#3B82F6`, text `#FFFFFF`, font weight 600. Height 36px (compact) or 40px (default). Padding: 0 16px. Border radius `8px`. Hover: `#60A5FA` with soft box shadow `0 0 16px rgba(59, 130, 246, 0.35)`. Active: `#2563EB`.
- **Secondary / Outline:** Background `transparent`, border `1px solid #334155`, text `#F8FAFC`. Hover: Background `#1E293B`, border `#60A5FA`.
- **Ghost:** Background `transparent`, text `#94A3B8`. Hover: Background `rgba(30, 41, 59, 0.6)`, text `#F8FAFC`.
- **Destructive:** Background `rgba(248, 113, 113, 0.1)`, border `1px solid rgba(248, 113, 113, 0.3)`, text `#F87171`. Hover: Background `#F87171`, text `#FFFFFF`.

### Chips & Semantic Status Badges
- **Structure:** Height 24px, padding 0 10px, border-radius `9999px`. Displays `label-sm` font.
- **Active Node (Success):** Background `rgba(74, 222, 128, 0.12)`, text `#4ADE80`, border `1px solid rgba(74, 222, 128, 0.25)`. Includes 6px luminous pulsing indicator dot.
- **Processing (Running):** Background `rgba(59, 130, 246, 0.12)`, text `#60A5FA`, border `1px solid rgba(59, 130, 246, 0.3)`.
- **Warning (Bottleneck):** Background `rgba(251, 191, 36, 0.12)`, text `#FBBF24`, border `1px solid rgba(251, 191, 36, 0.3)`.
- **Error (Halted):** Background `rgba(248, 113, 113, 0.12)`, text `#F87171`, border `1px solid rgba(248, 113, 113, 0.3)`.

### Cards & Container Panels
- **Standard Card:** Background `#111827`, border `1px solid #1F2937`, border-radius `16px`, padding 24px.
- **Interactive Workspace Card:** Same as standard card, with transitions for border-color and elevation on hover: moves to border `#334155`, surface `#1E293B`, and subtle shadow `0 8px 24px rgba(0, 0, 0, 0.4)`.
- **Active Node Card:** Highlighted with a primary electric border `1px solid #3B82F6` and faint blue ambient glow.

### Input Fields & Controls
- **Text Inputs:** Background `#0B0F17`, border `1px solid #1F2937`, height 40px, border-radius `8px`, text `#F8FAFC`, placeholder `#64748B`. Focused state: Border `#3B82F6`, outline `none`, box shadow `0 0 0 1px #3B82F6`.
- **Checkboxes & Radios:** Outer box 16x16px, background `#111827`, border `1px solid #334155`, border-radius `4px` (checkbox) or `9999px` (radio). Checked state: Background `#3B82F6`, border-color `#3B82F6`, glyph checkmark `#FFFFFF`. Focus ring: `2px solid rgba(59, 130, 246, 0.4)`.

### Lists & Data Grids
- **Header:** Height 36px, background `#0B0F17`, text `#64748B`, font `label-sm`, bottom-border `1px solid #1F2937`.
- **Row:** Height 48px, background `transparent`, bottom-border `1px solid rgba(31, 41, 55, 0.6)`. Hover: Background `#111827`. Selected: Background `rgba(59, 130, 246, 0.08)`.

### Agent-Specific Components
- **Agent Pulse Dot:** An 8px status sphere containing a centered radial core and an outer looping ripple wave animation emitting semantic status color with 0 to 40% alpha decay.
- **Execution Log Terminal:** Background `#070A0F`, border `1px solid #1E293B`, monospace typography, `#E2E8F0` main log text, `#38BDF8` timestamps, and `#3B82F6` function call highlights.