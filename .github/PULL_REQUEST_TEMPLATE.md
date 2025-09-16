## Summary

- What does this PR change and why?

## Changes

- [ ] Fix tokenizer padding ids to avoid invalid index on pad
- [ ] CPU-safe demo/inference (no device_map, eager attention fallback)
- [ ] Dependency tweaks (add soundfile, dedupe librosa)
- [ ] CI workflow with ruff format check and import smoke tests
- [ ] README updates (CPU quickstart, corrected examples)

## Testing

- [ ] `pip install -e .` succeeds
- [ ] `python -c "import vibevoice; import vibevoice.modular.modeling_vibevoice_inference"` succeeds
- [ ] Gradio demo launches on CPU: `python demo/gradio_demo.py --device cpu --model_path microsoft/VibeVoice-1.5B`

## Notes

- FlashAttention remains optional; on CPU, scripts use `attn_implementation=eager`.
- Torch 2.8 is heavy in CI; we only run import tests, not model execution.
