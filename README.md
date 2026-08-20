<div align="center">

<img src="https://storage.googleapis.com/chirag-dahiya-portfolio-assets/lyre-landing-page/og-image.png" alt="Lyre, local voice dictation that runs commands on your machine" width="640" />

<h1>Lyre</h1>

<p><strong>Private, on-device push-to-talk dictation for macOS and Windows.</strong><br/>
Talk and clean text lands in any app. Then your voice does more: rewrite a selection, draft a reply, or run a command you built. Nothing ever leaves your machine.</p>

<p>
  <a href="https://lyre.chiragdahiya.com"><strong>lyre.chiragdahiya.com</strong></a>
  &nbsp;·&nbsp;
  <a href="https://github.com/chiragd03/lyre-dictation/releases/latest">Download the latest release</a>
  &nbsp;·&nbsp;
  <a href="https://github.com/chiragd03/lyre-dictation/issues/new/choose">Report an issue</a>
</p>

</div>

---

## What Lyre does

Hold a hotkey, speak, and clean text lands at your cursor in whatever app is focused. A local model fixes the grammar and drops the "ums" before a word is inserted. That's the floor, not the ceiling.

- **Dictate into any app:** Slack, your editor, an email, a terminal. Text lands at your cursor, no window switch.
- **Local AI cleanup:** grammar and punctuation fixed on-device before insertion.
- **Rewrite your selection:** highlight text anywhere and say "make this warmer," and it rewrites in place.
- **Draft to clipboard:** highlight rough notes, say "write this as an email," and a clean draft is ready to paste.
- **Ask, and read the answer in the pill:** nothing typed, nothing changed.
- **Voice commands you build:** open apps, run scripts, kick off a build. The AI can only pick a command you wrote. It can never invent one. Shell actions confirm first.
- **Bring your own model:** local by default, or point transcription and the LLM at any OpenAI-compatible endpoint (Ollama, LM Studio, Groq…).

There's a full walkthrough, with videos, on the website: **[lyre.chiragdahiya.com](https://lyre.chiragdahiya.com)**

## Download

Grab the latest build for your platform from the **[Releases page](https://github.com/chiragd03/lyre-dictation/releases/latest)**:

| Platform | File |
| --- | --- |
| macOS (Apple Silicon) | `Lyre_arm64.dmg` |
| macOS (Intel) | `Lyre_x86_64.dmg` |
| Windows | `Lyre_..._x64-setup.exe` |

macOS note: Apple Silicon is the primary, most-exercised path. Lyre needs Microphone, Input Monitoring, and Accessibility permissions to hear the hotkey and type into other apps. It walks you through granting them on first run.

## This repository

This is the home for **Lyre's releases, issues, and feature requests**. It's where you download builds, tell me what's broken, and suggest what to build next. Every issue and request here gets read.

### Report a bug or request a feature

Open an issue and pick a template: **[New issue](https://github.com/chiragd03/lyre-dictation/issues/new/choose)**

For bugs, please attach a **debug bundle** so it can be diagnosed quickly: in Lyre, go to **Settings > Diagnostics > Export logs**. The bundle contains app logs and system info only. It does **not** include your audio, your dictated text, or your API keys.

## Privacy

Lyre is built around one idea: your voice is yours. Audio and text stay on your machine by default, and transcription and the AI cleanup both run on-device. Nothing is stored unless you turn on history. Cloud endpoints are strictly opt-in and labeled every time they're used, off until you ask.

---

<div align="center">
<sub>Built by <a href="https://chiragdahiya.com">Chirag Dahiya</a>.</sub>
</div>
