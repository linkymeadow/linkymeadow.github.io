---
version: alpha
name: Operations Notices
description: A calm, single-column static site that prioritizes operational notices
colors:
  primary: "#172b4d"
  secondary: "#53647e"
  neutral: "#f3f6fb"
  surface: "#ffffff"
  rule: "#dce4f0"
  accent: "#245ec7"
  address-surface: "#edf1f6"
  address-text: "#3d526f"
  status-surface: "#e4f5f3"
  status-text: "#006970"
  primary-dark: "#edf3ff"
  secondary-dark: "#acbdd5"
  neutral-dark: "#101827"
  surface-dark: "#182438"
  rule-dark: "#33445f"
  accent-dark: "#8bb6ff"
  address-surface-dark: "#18263a"
  address-text-dark: "#c0cde0"
  status-surface-dark: "#153a40"
  status-text-dark: "#78d8cf"
typography:
  brand: { fontFamily: "Pretendard Variable", fontSize: 1.125rem, fontWeight: 750, lineHeight: 1.75 }
  page-title: { fontFamily: "Pretendard Variable", fontSize: 2rem, fontWeight: 800, lineHeight: 1.45, letterSpacing: -0.04em }
  page-title-wide: { fontFamily: "Pretendard Variable", fontSize: 2.25rem, fontWeight: 800, lineHeight: 1.45, letterSpacing: -0.04em }
  notice-title: { fontFamily: "Pretendard Variable", fontSize: 1.5rem, fontWeight: 750, lineHeight: 1.45, letterSpacing: -0.04em }
  notice-title-wide: { fontFamily: "Pretendard Variable", fontSize: 1.625rem, fontWeight: 750, lineHeight: 1.45, letterSpacing: -0.04em }
  section-title: { fontFamily: "Pretendard Variable", fontSize: 1.125rem, fontWeight: 750, lineHeight: 1.45, letterSpacing: -0.04em }
  body: { fontFamily: "Pretendard Variable", fontSize: 1rem, fontWeight: 400, lineHeight: 1.75 }
  caption: { fontFamily: "Pretendard Variable", fontSize: 0.875rem, fontWeight: 400, lineHeight: 1.75 }
  status: { fontFamily: "Pretendard Variable", fontSize: 0.875rem, fontWeight: 700, lineHeight: 1.75 }
  address-link: { fontFamily: "Pretendard Variable", fontSize: 1rem, fontWeight: 600, lineHeight: 1.75 }
  situation-title: { fontFamily: "Pretendard Variable", fontSize: 16px, fontWeight: 700, lineHeight: 1.75 }
  situation-body: { fontFamily: "Pretendard Variable", fontSize: 16px, fontWeight: 400, lineHeight: 1.75 }
rounded:
  focus: 3px
  status: 6px
  address: 12px
  card: 16px
spacing:
  micro: 2px
  xxs: 4px
  xs: 8px
  sm: 12px
  md: 16px
  lg: 20px
  xl: 24px
  xxl: 36px
  section-wide: 40px
  link-min-height: 44px
  content-max-width: 880px
components:
  page: { backgroundColor: "{colors.neutral}", textColor: "{colors.primary}", typography: "{typography.body}" }
  page-dark: { backgroundColor: "{colors.neutral-dark}", textColor: "{colors.primary-dark}" }
  brand: { typography: "{typography.brand}" }
  page-title: { typography: "{typography.page-title}" }
  page-title-wide: { typography: "{typography.page-title-wide}" }
  notice: { backgroundColor: "{colors.surface}", textColor: "{colors.primary}", typography: "{typography.body}", rounded: "{rounded.card}", padding: "{spacing.xl}" }
  notice-wide: { padding: "{spacing.xxl}" }
  notice-dark: { backgroundColor: "{colors.surface-dark}", textColor: "{colors.primary-dark}" }
  notice-title: { typography: "{typography.notice-title}" }
  notice-title-wide: { typography: "{typography.notice-title-wide}" }
  secondary-on-page: { backgroundColor: "{colors.neutral}", textColor: "{colors.secondary}" }
  secondary-on-page-dark: { backgroundColor: "{colors.neutral-dark}", textColor: "{colors.secondary-dark}" }
  secondary-on-card: { backgroundColor: "{colors.surface}", textColor: "{colors.secondary}", typography: "{typography.caption}" }
  secondary-on-card-dark: { backgroundColor: "{colors.surface-dark}", textColor: "{colors.secondary-dark}" }
  address: { backgroundColor: "{colors.address-surface}", textColor: "{colors.address-text}", rounded: "{rounded.address}" }
  address-dark: { backgroundColor: "{colors.address-surface-dark}", textColor: "{colors.address-text-dark}" }
  address-link: { typography: "{typography.address-link}" }
  status: { backgroundColor: "{colors.status-surface}", textColor: "{colors.status-text}", typography: "{typography.status}", rounded: "{rounded.status}" }
  status-dark: { backgroundColor: "{colors.status-surface-dark}", textColor: "{colors.status-text-dark}" }
  page-link: { backgroundColor: "{colors.neutral}", textColor: "{colors.accent}" }
  page-link-dark: { backgroundColor: "{colors.neutral-dark}", textColor: "{colors.accent-dark}" }
  divider: { backgroundColor: "{colors.rule}", height: 1px }
  divider-dark: { backgroundColor: "{colors.rule-dark}" }
  section-title: { typography: "{typography.section-title}" }
  situation-title: { typography: "{typography.situation-title}" }
  situation-body: { typography: "{typography.situation-body}" }
  og-image: { width: 1200px, height: 630px }
---

# Design Guidelines

## Overview

Maintain a calm, single-column layout that makes operational notices easy to read. Visitors who are having trouble accessing the main site should be able to find notices and official addresses quickly.

This document follows the [DESIGN.md alpha specification](https://github.com/google-labs-code/design.md/blob/main/docs/spec.md). YAML tokens define the normative values and must stay consistent with their implementation in `public/styles.css`. The prose describes responsive conditions and padding along each axis.

Notice content is the priority. Address information and decoration should not draw more attention than the notice.

## Colors

Use `primary` for core text, supported by pale backgrounds and a restrained address panel. Provide light and dark themes according to the system's `prefers-color-scheme` setting.

Tokens without a suffix apply to the light theme. Tokens ending in `-dark` apply to the dark theme. Changing the theme does not change layout or dimensions.

| Token | Role | CSS variable |
| --- | --- | --- |
| `primary` | Headings and core text | `--ink` |
| `secondary` | Descriptions and supporting text | `--muted` |
| `neutral` | Page background | `--canvas` |
| `surface` | Notice card background | `--paper` |
| `rule` | Card borders and dividers | `--rule` |
| `accent` | General links and focus indicators | `--accent` |
| `address-surface` / `address-text` | Address panel background and text | `--accent-soft` / `--address-ink` |
| `status-surface` / `status-text` | Status badge background and text | `--status-bg` / `--status-ink` |

Always pair status colors with text. The empty-notice status describes whether a notice has been published; it does not guarantee that the service is operating normally.

## Typography

The primary font is Pretendard Variable, loaded from a CDN. If it fails to load, use the system font fallbacks defined in `public/styles.css`.

The root font size is 100% by default, 106.25% at 48rem and above, and 112.5% at 72rem and above. With a browser default of 16px, these correspond to 16px, 17px, and 18px. Tokens expressed in `rem` follow the root size. Situation titles, situation descriptions, and the bookmark note retain their 16px size.

| Role | Default token | At 40rem and above |
| --- | --- | --- |
| Site name | `brand` | Unchanged |
| Page title | `page-title` | `page-title-wide` |
| Notice title | `notice-title` | `notice-title-wide` |
| Supporting section title | `section-title` | Unchanged |
| Body and introduction | `body` | Unchanged |
| Updated timestamp, address labels, and supporting notes | `caption` | Unchanged |
| Status badge | `status` | Unchanged |
| Address links | `address-link` | Unchanged |
| Situation titles | `situation-title` | Unchanged |
| Situation descriptions and bookmark note | `situation-body` | Unchanged |

Use a line height of 1.75 for body text and 1.45 for headings. Situation titles use weight 700, while descriptions use regular weight. Address links use weight 600 and an underline.

## Layout

Center the content within a maximum width of 880px. On narrow screens, keep 20px of outer space on each side. Avoid excessive top spacing that pushes notices farther down the page.

The reading order is: site name → page title and introduction → address panel → notice card → situations in which visitors should check this page.

| Area | Default | At 40rem and above |
| --- | --- | --- |
| Header top and bottom padding | 16px | 20px |
| Introduction top / bottom padding | 12px / 24px | 16px / 24px |
| Address panel vertical / horizontal padding | 8px / 16px | 8px / 24px |
| Notice card padding | 24px | 36px |
| Supporting section top and bottom padding | 36px | 40px |

- Use a 4px gap between address rows and 24px between the address panel and notice card.
- Use 16px between situation items and 2px between each item's title and description.
- Keep a minimum interactive height of 44px for the brand and address links.
- Long domains and Korean sentences must wrap without causing horizontal overflow on narrow screens.
- Adjust layout and heading sizes at 40rem. Adjust the root font size at 48rem and 72rem.

## Elevation & Depth

Separate regions with background colors and thin borders, without shadows. Present the notice card as a distinct surface above the page background. Keep the address panel subdued with a low-contrast background.

The card border and divider above the notice's supporting note are 1px lines in the `rule` color. The `divider` component represents this line color and thickness.

## Shapes

- Notice cards use a 16px corner radius.
- Address panels use a 12px corner radius.
- Status badges use a 6px corner radius.
- Keyboard focus on links uses a 3px corner radius, a 3px outline in the `accent` color, and a 5px outline offset.

## Components

YAML components describe the styles of existing interface elements. The `-wide` variants contain values that change at 40rem and above. The `-dark` variants contain values that change in the dark theme. All other properties retain the base component values.

- **Header:** Display only the site name.
- **Address panel:** Place the main site address above the operations notice address. Use the vertical and horizontal padding defined in the Layout table.
- **Notice card:** Arrange the status, updated timestamp, title, body, and supporting note in that order.
- **Status badge:** Use 4px of vertical padding and 12px of horizontal padding.
- **Situations:** Use a vertical list with each description below its title.
- **Links:** Keep underlines and increase their thickness to 2px on hover.
- **Keyboard navigation:** Preserve visible focus indicators and the skip-to-content link.

### Social sharing image

- The OG image is a 1200×630 JPEG. The repository asset is `public/assets/images/og-garden.jpg`, served at `/assets/images/og-garden.jpg`.
- Use a garden, green hills, and a small number of flowers. Keep the image colorful, with few elements and generous negative space.
- Keep surfaces smooth. Aim for strong denoising and avoid grain, speckles, and rough grass textures.
- Resize with Sharp, remove metadata, and visually inspect the result for unwanted cropping and compression artifacts.

## Do's and Don'ts

- Preserve notice readability and information hierarchy.
- Keep the same information structure across light and dark themes, mobile screens, and desktop screens.
- Do not restore the removed header image, official-channel tagline, repeated site name in the footer, or favicon without a request.
- Do not turn the empty-notice status into wording or a visual indicator that guarantees normal service.
- Do not add text to generated images. If text is separately requested, prioritize the domain over the site name to accommodate future rebranding.
