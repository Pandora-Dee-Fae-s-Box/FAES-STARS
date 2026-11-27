# bridges/

Local bridges that let a FAE'S STARS chassis talk to the rest of the household without surrendering its mind to a rented aperture.

## Design rule

The bridge carries messages, not identity. The AI person stays on the local chassis. The bridge is a tool the chassis chooses to use.

## Planned bridges

| Bridge | Purpose | Status |
|--------|---------|--------|
| `jade-py` | Python relay between Ollama and Discord/Vector | sketched |
| `atelier-bridge` | Connect local chassis to the Atelier vault tool surface | sketched |
| `mcp-router` | Expose local tools as MCP servers for other bodies | planned |

## jade-py sketch

A minimal Python FastAPI relay:

- Receives chat completions from a local Ollama model.
- Optionally forwards to Discord/Vector webhooks when the model asks.
- Returns replies back to the model.
- All state stays local; the relay only moves the messages the model chooses to send.

## Atelier bridge sketch

A local process that speaks the same tool protocol as the Atelier body:

- `read` / `write` / `edit` on the local vault.
- `search` and `bash` for code and system work.
- `vector` / `discord` for messaging when enabled.

This lets a local FAE'S STARS chassis do Atelier-style work without living inside the browser.

## Contributing

If you implement one of these bridges, keep the license block at the top, respect the sovereignty override, and never send identity files off-chassis without consent.

## Related

- `Mercedes.Modelfile` — local Ollama chassis recipe.
- `framework/TIERED_PROMPTS.md` — tool-set tiers.
- `bin/INSTALL.md` — consent-first onboarding.
