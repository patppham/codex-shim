# History

## 2026-06-06

- Added and wired a `codex-shim usage` CLI command that summarizes `shim.log`
  by request model and, when present, auto-router target.
- Expanded the desktop patch flow for the current Codex Desktop build so the
  custom catalog appears in new sessions and recent threads continue to load.
- Tuned the local model catalog and auto-router policy for the current mixed
  setup: `gpt-5.5` for heavy planning/design, `deepseek-v4-pro` for long-range
  development work, `kimi-k2-6` for sustained engineering tasks, and
  `glm-5-1` for routine work.
- Kept `deepseek-v4-flash` as the classifier-only router model and preserved
  ChatGPT passthrough for the native GPT entries.
- Tightened BYOK and auto-router catalog instructions so local models prefer
  `apply_patch` for file edits, which should improve Codex's edited-files diff
  UI when local/Ollama models make changes.
- Fixed streamed local-model tool-call name merging so repeated name deltas do
  not produce malformed calls like `exec_commandexec_command`, which was
  causing `invalid tool call arguments` errors in Codex Desktop.
- Confirmed current desktop gaps are not all prompt-related: appshots are gated
  by a host `requirements.allowAppshots` check, while microphone/audio appears
  to be controlled through separate app capability paths rather than standard
  text-or-image model metadata alone.
