---
name: video-sdk-windows
description: "Zoom Video SDK for Windows - C++ integration for video sessions, raw audio/video capture, screen sharing, recording, and real-time communication"
user-invocable: false
triggers:
  - "video sdk windows"
  - "windows video sdk"
  - "video sdk raw data windows"
  - "windows custom video"
  - "c++ video sdk"
---

# Zoom Video SDK - Windows Development

Expert guidance for developing with the Zoom Video SDK on Windows. This SDK enables custom video applications, raw media capture/injection, cloud recording, live streaming, and real-time transcription on Windows platforms.

**Official Documentation**: https://developers.zoom.us/docs/video-sdk/windows/
**API Reference**: https://marketplacefront.zoom.us/sdk/custom/windows/
**Sample Repository**: https://github.com/zoom/videosdk-windows-rawdata-sample

## Quick Links

**New to Video SDK? Follow this path:**

1. **[SDK Architecture Pattern](concepts/sdk-architecture-pattern.md)** - Universal 3-step pattern for ANY feature
2. **[Session Join Pattern](examples/session-join-pattern.md)** - Complete working code to join a session
3. **[Windows Message Loop](troubleshooting/windows-message-loop.md)** - **CRITICAL**: Fix callbacks not firing
4. **[Video Rendering](examples/video-rendering.md)** - Display video with Canvas API

**Reference:**
- **[Singleton Hierarchy](concepts/singleton-hierarchy.md)** - 5-level SDK navigation map
- **[API Reference](references/windows-reference.md)** - Methods, error codes, timing rules
- **[Delegate Methods](references/delegate-methods.md)** - All 80+ callback methods
- **[Sample Applications](references/samples.md)** - Official samples guide
- **[windows.md](windows.md)** - Secondary overview doc (pointer-style)
- **[SKILL.md](SKILL.md)** - Complete documentation navigation

**Having issues?**
- Callbacks not firing → [Windows Message Loop](troubleshooting/windows-message-loop.md)
- Build errors → [Build Errors Guide](troubleshooting/build-errors.md)
- Video subscribe fails → [Video Rendering](examples/video-rendering.md) (subscribe in `onUserVideoStatusChanged`)
- Quick diagnostics → [Common Issues](troubleshooting/common-issues.md)

**Building a Custom UI?**
- [Canvas vs Raw Data](concepts/canvas-vs-raw-data.md) - Choose your rendering approach
