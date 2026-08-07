# Changelog

All notable changes to this plugin are documented in this file.

## Unreleased

- aligned the repository with the current Claude plugin structure around `.claude-plugin/plugin.json`, `skills/`, and `.mcp.json`
- added Claude-facing installation and connector documentation
- converted command-style workflows into `SKILL.md`-based workflows under `skills/`
- bundled the main Zoom MCP server configuration in `.mcp.json`
- removed the Whiteboard MCP server from the bundled plugin surface
- tightened skill metadata and reduced maintainer-facing wording in user-facing docs
- renamed 12 skill identifiers from slash-separated paths (e.g. `contact-center/android`) to flat hyphenated names (e.g. `contact-center-android`) for stable registration and namespacing
- condensed 6 `SKILL.md` files (meeting-sdk/linux, ui-toolkit, video-sdk/linux, video-sdk/web, video-sdk/windows, zoom-mcp/whiteboard) from inline reference documents into focused routing guides that link to the dedicated reference docs
- added fork `README.md` documenting the delta vs. upstream, with a Quick Start and a beginner step-by-step guide
- added a Portuguese (`pt-BR`) translation of the README
