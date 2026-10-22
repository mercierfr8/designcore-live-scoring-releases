---
version: alpha
name: designcore-live-scoring-design-analysis
description: |
  A broadcast-scoreboard look on a near-black ground. Anton (condensed, all-caps) carries the
  numbers and headlines; Archivo in heavy, wide-tracked caps carries labels and buttons; IBM Plex
  Mono carries clocks, versions and codes. Gold is the one interactive accent. Red and blue mean
  only the two corners (hong/chung) and nothing else. No gradients except inside the corner score
  bars, no imagery, no drop shadows except one soft lift under modals/hero panel.
---

# Extracted from ~/Downloads/designcore-live-scoring-desktop/renderer/index.html (inline styles,
# counted by frequency). No token file exists in the app; values below are the resolved literals.

colors:
  canvas: "#0B0D10"          # app ground
  surface-card: "#12151A"    # every panel/section
  hairline: "rgba(255,255,255,.07)"
  hairline-strong: "rgba(255,255,255,.12)"
  ink: "#E8EAED"             # primary text — 16.14:1 on canvas
  body: "#9BA3AE"            # secondary text — 7.64:1 canvas / 7.18:1 card
  accent: "#E8B84B"          # gold — buttons, links, active state ONLY
  on-accent: "#0B0D10"       # 10.55:1 on gold
  corner-red: "#E5484D"
  corner-red-ink: "#FF7A7F"  # red text on dark — 7.73:1
  corner-red-deep: "#C13438"
  corner-blue: "#4D8DEE"
  corner-blue-ink: "#7FB1FF" # blue text on dark — 8.93:1
  corner-blue-deep: "#2F63B8"
  # FINDING: the app's tertiary grey #6B7280 is 4.02:1 on canvas and 3.78:1 on card — it fails
  # 4.5:1 for the small (10–11px) labels it is used on. Not used here; small text uses {colors.body}.

typography:
  display-xxl: { fontFamily: Anton, fontSize: 88px, fontWeight: 400, lineHeight: 0.95, letterSpacing: .01em }
  display-lg:  { fontFamily: Anton, fontSize: 44px, fontWeight: 400, lineHeight: 1, letterSpacing: .02em }
  score:       { fontFamily: Anton, fontSize: 64px, fontWeight: 400, lineHeight: 1 }
  title-sm:    { fontFamily: Archivo, fontSize: 16px, fontWeight: 800, lineHeight: 1.3, letterSpacing: .02em }
  body-md:     { fontFamily: Archivo, fontSize: 16px, fontWeight: 400, lineHeight: 1.6 }
  label:       { fontFamily: Archivo, fontSize: 12px, fontWeight: 800, lineHeight: 1.2, letterSpacing: .14em }
  button-md:   { fontFamily: Archivo, fontSize: 13px, fontWeight: 800, lineHeight: 1, letterSpacing: .08em }
  mono:        { fontFamily: "IBM Plex Mono", fontSize: 13px, fontWeight: 500, lineHeight: 1.4 }

rounded:
  sm: 6px
  md: 8px      # buttons, inputs (most common in app: 62 uses)
  lg: 10px     # panels/cards (20 uses)
  xl: 14px     # modals / hero panel
  pill: 999px  # chips, status badges

spacing: { xxs: 4px, xs: 8px, sm: 12px, md: 16px, lg: 24px, xl: 32px, xxl: 48px, section: 96px }

components:
  button-primary:
    backgroundColor: "{colors.accent}"
    color: "{colors.on-accent}"
    typography: "{typography.button-md}"
    rounded: "{rounded.md}"
    height: 52px
    padding: 0 26px
  button-ghost:
    backgroundColor: transparent
    border: "1px solid {colors.hairline-strong}"
    color: "{colors.ink}"
    typography: "{typography.button-md}"
    rounded: "{rounded.md}"
  card:
    backgroundColor: "{colors.surface-card}"
    border: "1px solid {colors.hairline}"
    rounded: "{rounded.lg}"
    padding: "{spacing.lg}"
  chip:
    border: "1px solid {colors.hairline-strong}"
    rounded: "{rounded.pill}"
    typography: "{typography.label}"
    padding: 5px 12px
  score-bar:   # the broadcast overlay strip — the signature move
    red: "linear-gradient(90deg, {colors.corner-red-deep}, {colors.corner-red})"
    blue: "linear-gradient(90deg, {colors.corner-blue}, {colors.corner-blue-deep})"
    clock: "{colors.canvas} block, {typography.mono}, gold round label"

motion:
  popin: "scale .96→1 + fade, .25s ease — modals/hero only"
  livepulse: "1.4s opacity pulse on the red LIVE dot"
  hover: "filter brightness(1.15–1.25), no movement"
  reduced-motion: "all animation off under prefers-reduced-motion: reduce"

voice:
  Referee vocabulary (shi-jak, kal-yeo, gam-jeom), short caps labels, French first (app default).
