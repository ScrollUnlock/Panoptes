# Copilot Instructions for Panoptes

## Project Overview
**Panoptes** is an open-source vulnerability management platform that correlates real software inventory with CVE intelligence. Unlike traditional vulnerability scanners that infer risk from exposed services, Panoptes observes actual system state and applies deterministic logic for vulnerability matching.

**Key Tagline:** "See Everything. Miss Nothing."

## Architecture

The Panoptes ecosystem consists of three planned components:

1. **Spectra** (Endpoint Sensor)
   - Native agent deployed on endpoints
   - Enumerates installed software, versions, patches, and configurations
   - Captures real inventory state even for dormant/unreachable software
   - Source: Part of `Panoptes-See-Everything-Miss-Nothing` GitHub organization

2. **Iris** (Correlation Engine)
   - Backend analysis system
   - Normalizes inventory data from Spectra
   - Correlates with vulnerability intelligence sources
   - Applies version range logic and vendor-specific rules for CVE matching
   - Source: Part of `Panoptes-See-Everything-Miss-Nothing` GitHub organization

3. **UI & API** (Future)
   - Planned visualization and integration interfaces
   - SOC and vulnerability workflow automation

## Repository Structure

### Current State
- **Single-page landing site** (`index.html`) presenting project vision and architecture
- No application code yet; this repo serves as the public-facing documentation site
- Related component repos live in the `Panoptes-See-Everything-Miss-Nothing` GitHub organization

### Key Files
- [index.html](../index.html) — Landing page with starfield animation, design philosophy, and architecture overview

## Design Philosophy & Conventions

### Core Principles
- **Inventory First** — Begin with complete, accurate system enumeration rather than network inference
- **Logic-Based Matching** — Use deterministic rules (version ranges, vendor logic) instead of pattern matching
- **Explainability** — Every finding must be backed by evidence: software path, version, detection logic, and references
- **No Black Boxes** — Transparent reasoning for all vulnerability assessments

### Code Patterns
The landing page uses:
- **CSS Custom Properties** for theming (dark monospace aesthetic)
- **CSS Grid** for responsive layouts
- **Canvas API** for starfield animation (3D parallax depth effect)
- **Semantic HTML** with accessibility in mind (lang attributes, meta tags)

### Styling Conventions
- Color scheme uses a dark, _technical_ palette centered on cyan (`#38bdf8`)
- JetBrains Mono monospace font for authentic developer aesthetic
- CSS Variables defined at `:root` for maintainability
- Glassmorphism effects (backdrop-filter, opacity) for modern UI depth

## Development Guidelines

### When Contributing to Landing Page
1. Preserve the monospace, technical aesthetic
2. Maintain the dark theme and cyan accent colors
3. Update architecture cards when Spectra or Iris components have significant changes
4. Keep descriptions concise—this is a public-facing technical elevator pitch

### When Contributing to Spectra or Iris
- These repos are independent; work in their respective GitHub repositories
- Coordinate architecture changes through this landing page updates
- Link to public documentation from relevant sections

### Future Interfaces
- When UI/API repos are created, document their architecture and communication patterns
- Establish clear data contracts between Spectra (inventory) → Iris (correlation) → UI/API (presentation)

## Key Cross-Component Patterns

### Data Flow
```
Spectra (inventory collection)
  ↓ [normalized inventory data]
Iris (correlation & analysis)
  ↓ [vulnerability assessments with evidence]
UI/API (user-facing interface)
```

### Inventory Data Structure
Future components should work with structured inventory including:
- Software name, version, installation path
- Patch level and configuration state
- Detection source and confidence metadata

### CVE Correlation Logic
Iris applies vendor-specific rules accounting for:
- Affected version ranges (not just single versions)
- Conditional applicability (e.g., only affects certain OS versions)
- Patch status determination

## References
- **GitHub Organization:** https://github.com/Panoptes-See-Everything-Miss-Nothing
- **Homepage:** index.html (this site)
- **License & Contribution:** Check GitHub repos for individual guidelines
