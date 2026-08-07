---
name: video-sdk-web
description: "Zoom Video SDK for Web - JavaScript/TypeScript integration for browser-based video sessions, real-time communication, screen sharing, recording, and live transcription"
user-invocable: false
triggers:
  - "video sdk web"
  - "custom video web"
  - "attachvideo"
  - "peer-video-state-change"
  - "web videosdk"
---

# Zoom Video SDK - Web Development

Expert guidance for developing with the Zoom Video SDK on Web. This SDK enables custom video applications in the browser with real-time video/audio, screen sharing, cloud recording, live streaming, chat, and live transcription.

This skill is for **custom video sessions**, not embedded Zoom meetings.
If the user wants a custom UI for a real Zoom meeting, route to
[../../meeting-sdk/web/component-view/SKILL.md](../../meeting-sdk/web/component-view/SKILL.md).

**Official Documentation**: https://developers.zoom.us/docs/video-sdk/web/
**API Reference**: https://marketplacefront.zoom.us/sdk/custom/web/modules.html
**Sample Repository**: https://github.com/zoom/videosdk-web-sample

## Quick Links

**New to Video SDK? Follow this path:**

1. **[SDK Architecture Pattern](concepts/sdk-architecture-pattern.md)** - Universal 3-step pattern for ANY feature
2. **[Session Join Pattern](examples/session-join-pattern.md)** - Complete working code to join a session
3. **[Video Rendering](examples/video-rendering.md)** - Display video with attachVideo()
4. **[Event Handling](examples/event-handling.md)** - Required events for video/audio

**Reference:**
- **[Singleton Hierarchy](concepts/singleton-hierarchy.md)** - 4-level SDK navigation map
- **[API Reference](references/web-reference.md)** - Methods, events, error codes
- **[SKILL.md](SKILL.md)** - Complete documentation navigation
- **[../../probe-sdk/SKILL.md](../../probe-sdk/SKILL.md)** - Optional browser/device/network readiness diagnostics before join

**Having issues?**
- Video not showing → [Video Rendering](examples/video-rendering.md) (use attachVideo, not renderVideo)
