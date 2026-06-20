# Photoday — Site Audit

Audit project for the **Photoday** Webflow site. The site is built with a mix of
**Finsweet** and **Lumos** component frameworks. This repo collects the audit
findings and (once added) the local source/export to audit against.

## Contents

| File / folder | Purpose |
|---|---|
| `photoday_audit_tabs.html` | Self-contained component-audit report. Open it directly in a browser. |
| `source/` | Drop the Photoday site export / source code here to audit against (not yet added). |

## How to view the report

Double-click `photoday_audit_tabs.html`, or open it in your browser. It's fully
self-contained — no server or build step needed.

## Audit summary (component inventory)

- **32 components** catalogued across **2 frameworks** (Finsweet + Lumos).
- **Lumos components are clean** — every Lumos component scores 10/10.
- **The issues are concentrated in the Finsweet / legacy layer.**

### Flagged components (< 10/10)

| Component | Framework | Instances | Health | Issue |
|---|---|---|---|---|
| Footer (primary) | Finsweet | 86 | **6/10** | Mixed naming patterns; multiple versions of the same class |
| Testimonials – Carousel | Finsweet | 2 | 7/10 | Rebuild with Swiper or the Lumos slider |
| NavBar_Global_Sticky (Starts Light) | Finsweet | 39 | 8.5/10 | Mixed naming; should reuse Section Custom |
| NavBar_Global_Sticky | Finsweet | 29 | 9/10 | Minor mixed naming patterns |

### Duplicate components (consolidation opportunities)

Two main clusters of duplication, both Finsweet:

- **Navigation** — 7 overlapping nav components: `NavBar_Global_Sticky`,
  `NavBar_Global_Sticky (Starts Light)`, `nav-main`, `nav-main_component`,
  `NavBar_Blog`, `NavBar_New_Black`, `Nav_main - V2`. Several have 0 instances
  (dead) and should be removed; the rest should be consolidated.
- **Global styles** — `Global Styles` (11) and `global-styles` (66) are
  duplicate style sources with inconsistent naming.

## Recommended next steps

1. **Footer** is the highest-priority fix — 86 instances on a 6/10 component.
2. Delete dead nav components (0 instances) and consolidate the rest to one system.
3. Merge the two `global-styles` sources into one.
4. Rebuild the testimonials carousel on Swiper / Lumos slider.

## Audit access

- **Method:** local codebase (Webflow export / source dropped into `source/`).
