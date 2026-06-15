# uri2voice


## AI Cost Tracking

![PyPI](https://img.shields.io/badge/pypi-costs-blue) ![Version](https://img.shields.io/badge/version-0.1.31-blue) ![Python](https://img.shields.io/badge/python-3.9+-blue) ![License](https://img.shields.io/badge/license-Apache--2.0-green)
![AI Cost](https://img.shields.io/badge/AI%20Cost-$0.00-orange) ![Human Time](https://img.shields.io/badge/Human%20Time-1.0h-blue) ![Model](https://img.shields.io/badge/Model-openrouter%2Fqwen%2Fqwen3--coder--next-lightgrey)

- 🤖 **LLM usage:** $0.0001 (1 commits)
- 👤 **Human dev:** ~$100 (1.0h @ $100/h, 30min dedup)

Generated on 2026-06-15 using [openrouter/qwen/qwen3-coder-next](https://openrouter.ai/qwen/qwen3-coder-next)

---

Execution layer for voice-related URI schemes. Capability manifests stay in `touri`
(or example packs under `examples/21_touri_voice/`).

## Schemes

```txt
stt://...    speech-to-text
tts://...    text-to-speech (artifact output)
voice://...  voice command → nl2uri compact flow
```

## Handlers (mock MVP)

| URI | Handler |
|-----|---------|
| `stt://mock/transcribe` | `uri2voice.stt:transcribe` |
| `tts://mock/speak` | `uri2voice.tts:speak` |
| `voice://command/from-text` | `uri2voice.voice_command:plan_voice_command` |

## Usage via touri

```bash
touri call stt://mock/transcribe \
  --registry examples/21_touri_voice \
  --payload '{"text":"otwórz Chrome i sprawdź health"}'
```

See [`examples/21_touri_voice/`](../../examples/21_touri_voice/) and [`docs/VOICE_WITH_TOURI.md`](../../docs/VOICE_WITH_TOURI.md).
