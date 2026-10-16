# Appcast tools, pinned

What the `appcast` job of `mac-release.yml` runs in the one step that holds
`SPARKLE_ED_PRIVATE_KEY`: copies of `macos/release/appcast.py`,
`macos/winzapp_mac/provenance.py` and `macos/winzapp_mac/sparkle_policy.py`
from gabrielhhaber/WinZapp_Python, kept on this branch so that step never runs
code from the tag it publishes (the tag is read as data only: its changelogs
and `language_map.json`). Sparkle's `sign_update` comes from the official
Sparkle 2.10.0 release, pinned by SHA-256 in the workflow.

These copies are kept equal to the newest official upstream release's by
the release watchdog on the maintainer's Mac (one commit on this branch
whenever they differ, before it dispatches a build). The appcast items they
write must stay what that release's `sparkle_policy.decide()` accepts.
