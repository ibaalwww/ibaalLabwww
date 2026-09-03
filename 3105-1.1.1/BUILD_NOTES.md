# 3105 optimized rebuild notes

This rebuild uses the available 1.1.1 Xcode source as the editable baseline and the supplied 2.0 beta 3 unsigned IPA as a binary/reference artifact.

## Performance changes

- Added a short-lived discovery cache for expensive app-bundle metadata, MCM class-2 identifiers, and LaunchServices candidates.
- Container UUID paths are never persisted by the cache, avoiding stale-container failures after reinstall/restore.
- App-bundle metadata and filesystem container enumeration are started concurrently during App Data Browser discovery.
- Existing progressive MHA resolution remains intact so the UI can show preliminary results before the full candidate pass finishes.

## Credit

Added `iBaal` to Settings → Credits with Telegram `@MEUGOM`.

## Version

Source project bumped to 1.1.2 / build 8.

## Important

The supplied 2.0 beta 3 IPA contains additional features not present in the 1.1.1 source archive (including Repository and Dialer-related UI strings). Those compiled-only features cannot be safely reconstructed as source code from the IPA alone. This source rebuild therefore does not claim to reproduce every 2.0 beta 3 feature.
