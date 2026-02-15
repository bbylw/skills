---
name: brand-guidelines
description: Applies a company's brand colors and typography to artifacts. Use it when brand colors or style guidelines, visual formatting, or company design standards apply.
license: Complete terms in LICENSE.txt
---

# Brand Styling

## Overview

Use this skill to apply brand identity and style resources in a reusable, provider-agnostic way.

**Keywords**: branding, corporate identity, visual identity, post-processing, styling, brand colors, typography, visual formatting, visual design

## Brand Guidelines

### Colors

Define a theme before styling. At minimum, specify:
- Primary foreground/background
- Secondary neutral palette
- 2-3 accent colors

If the user does not provide a brand palette, ask for one or use a clearly-labeled temporary palette.

### Typography

Define at least:
- Heading font stack
- Body font stack
- Fallback fonts available in common environments

## Features

### Smart Font Application

- Applies heading fonts to titles and large text
- Applies body fonts to paragraphs and long-form content
- Automatically falls back to broadly available system fonts
- Preserves readability across environments

### Text Styling

- Maintains clear hierarchy between headings and body text
- Uses contrast-aware color selection
- Preserves existing emphasis where possible

### Shape and Accent Colors

- Applies accent colors to non-text visual elements
- Balances consistency and variation across components
- Keeps output visually coherent and on-brand

## Technical Details

### Font Management

- Prefer system-available fonts unless custom fonts are explicitly provided
- Always include fallback fonts in CSS or style definitions
- Do not assume internet font loading is available

### Color Application

- Use exact brand color values when provided
- Keep color tokens centralized for easy updates
- Validate contrast for accessibility when practical
