# Vendored Upstream Boundary

This repository vendors a slice of `mlx_lm` to ensure seamless integration of the `TurboQuantKCache` and the custom streaming attention adapters without requiring users to fork `mlx_lm` themselves.

## Important Distinctions

- **The vendored tree exists for integration and compatibility:** It provides the surrounding model weight loading and text generation harnesses required to evaluate TurboQuant on Apple Silicon.
- **Presence of a model file does not imply TurboQuant support:** You will see dozens of model architecture definitions in `mlx_lm/models/`. Most of these are unmodified upstream files. Their presence simply keeps the parent library intact.
- **Only explicitly listed model families are supported for TurboQuant runtime certification:** A model is only supported if it has been expressly wired and explicitly listed in `docs/supported-surface.md`. 

Please refer to `docs/supported-surface.md` for the explicit list of officially supported architectures (currently Llama and Gemma).