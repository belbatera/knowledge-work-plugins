---
name: ui-toolkit-web
description: "Reference skill for Zoom Video SDK UI Toolkit. Use after routing to a web video workflow when you want prebuilt React UI instead of building a fully custom Video SDK interface."
user-invocable: false
triggers:
  - "ui toolkit"
  - "zoom ui"
  - "prebuilt video ui"
  - "video conferencing ui"
  - "zoom video ui toolkit"
  - "uitoolkit"
  - "ready-made zoom ui"
---

# Zoom Video SDK UI Toolkit

Background reference for the prebuilt Zoom Video SDK UI Toolkit on web. Prefer `choose-zoom-approach` first when the user might still need Meeting SDK instead.

**Official Documentation**: https://developers.zoom.us/docs/video-sdk/web/ui-toolkit/
**API Reference**: https://marketplacefront.zoom.us/sdk/uitoolkit/web/
**NPM Package**: https://www.npmjs.com/package/@zoom/videosdk-zoom-ui-toolkit
**Live Demo**: https://sdk.zoom.com/videosdk-uitoolkit

## Quick Links

**New to UI Toolkit? Follow this path:**

1. **Quick Start** - Get running in 5 minutes (see below)
2. **JWT Authentication** - Server-side token generation (required)
3. **Composite vs Components** - Choose your approach  
4. **Framework Integration** - React, Vue, Angular, Next.js patterns
5. **Integrated Index** - see the section below in this file

**Having issues?**
- Session not joining → Check JWT Authentication (most common issue)
- React 18 peer dependency error → See Installation section
- CSS not loading → See [Troubleshooting](troubleshooting/common-issues.md)
- Components not showing → Check Component Lifecycle
- Start with preflight checks → [5-Minute Runbook](RUNBOOK.md)

## Overview

The Zoom Video SDK UI Toolkit is a **pre-built video UI library** that renders complete video conferencing experiences with minimal code. Unlike the raw Video SDK, the UI Toolkit provides:

- ✅ **Ready-to-use UI** - Professional video interface out of the box
