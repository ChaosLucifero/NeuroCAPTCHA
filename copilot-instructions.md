# Copilot Instructions for NeuroCAPTCHA

## Project
PyTorch-based end-to-end CAPTCHA solver. Perception → Reasoning → Execution pipeline.

## Code Style
- Use OOP for all major components (Perception, Reasoning, Execution as classes).
- Use type hints on all public functions and methods.
- Use `@dataclass` for configs and data containers, not raw dicts.
- Prefer `pathlib.Path` over string paths.
- Import `torch.nn.functional as F` and reference activations/losses as `F.xxx`.
- Write docstrings with Args, Returns, and Raises for every public function.
- Use helper functions for non-trivial logic; do not inline complex preprocessing.

## Architecture
- Perception: `PerceptionModule` (screenshot → visual features / ROI).
- Reasoning: `ReasoningModule` (features → action logits or action sequence).
- Execution: `ExecutionModule` (actions → browser mouse/keyboard events via Playwright).
- Each module should be independently testable with mock inputs.
