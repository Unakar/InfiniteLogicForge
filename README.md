# InfiniteLogicForge 🧩⚙️

### Programmatic Logic Puzzle Generator for LLM Reasoning Evaluation

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)

An automated pipeline for generating infinite logic puzzles with controllable difficulty and perturbation levels. Generates LLM-friendly question/answer pairs with verified solutions.

![Workflow Diagram](https://via.placeholder.com/800x400.png?text=Puzzle+Generation+Pipeline)

## Features ✨

- **Parametric Puzzle Generation**
  - Knights & Knaves variants (adjust #characters)
  - Zebra/Einstein puzzles (control #attributes)
  - River crossing problems (customize object types)
  - Balance scale puzzles (configure ball counts)
  
- **Controlled Perturbations**
  ```yaml
  name_variants: [Shakespearean, Sci-Fi, Animal]
  logical_distractors: +10-40% irrelevant info
  language_fluctuations: PassiveVoice, RunOnSentences
  error_injection: InvalidConclusions, ContradictoryPremises
  ```

- **Quality Assurance**
  - Automated logical consistency checks
  - Solution verification engine
  - Natural language polishing (GPT-4 & rule-based)

## Installation ⚙️

```bash
git clone https://github.com/yourusername/InfiniteLogicForge.git
pip install -r requirements.txt
```

## Usage 🚀

```python
from puzzle_generator import LogicForge

# Generate medium-difficulty puzzle
generator = LogicForge(
    puzzle_type="knights_and_knaves",
    difficulty=7,  # 1-10 scale
    perturbation_level=3  # 0=clean, 5=max
)

dataset = generator.generate_batch(
    num_puzzles=1000,
    output_format="json",  # json/csv/parquet
    language_localization="en"  # es/fr/zh supported
)
```

## Dataset Structure 📂

Sample JSON entry:
```json
{
  "id": "KK-7a83f2",
  "question": "You meet three individuals: Arin, possessing azure locks...",
  "solution": "Arin is a knight, Belen is a spy...",
  "metadata": {
    "logic_steps": 5,
    "distractor_count": 3,
    "perturbations": ["name_shuffle", "time_travel_context"],
    "formal_logic": "∀x(Statement(x) → Knight(x) ⊕ Knave(x))"
  }
}
```

## Supported Puzzle Types 🧠

| Category                | Variations | Difficulty Params |
|-------------------------|------------|-------------------|
| Knights & Knaves        | 25+        | Characters, Statement Depth |
| Zebra Puzzles           | 15+        | Attributes, Constraints    |
| River Crossing          | 10+        | Object Types, Boat Capacity|
| Weight Measurement      | 8+         | Weights, Measurements Count|


## License 📄

MIT License - See [LICENSE](LICENSE) for details


---

*"Logic will get you from A to B. Imagination will take you everywhere." - Einstein*
