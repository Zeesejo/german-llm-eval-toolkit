# German LLM Evaluation Toolkit

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)

**Evaluation toolkit for German language models** - perplexity metrics, benchmark datasets, and quality assessment tools for [Occiglot](https://github.com/occiglot) and other multilingual LLMs.

## 🎯 Purpose

This toolkit is designed to support the evaluation of German language models, specifically for the [Occiglot project](https://occiglot.eu/) - an open-source research collective building European multilingual LLMs.

## ✨ Features

- **Perplexity Evaluation**: Calculate perplexity scores on German text corpora
- **Benchmark Datasets**: Curated German language benchmarks
  - News articles (Tagesschau, DW)
  - Wikipedia excerpts  
  - Social media text
  - Technical documentation
- **Quality Metrics**:
  - Token-level accuracy
  - Sentence fluency scoring
  - Named Entity Recognition evaluation
  - Grammatical correctness checks
- **Comparative Analysis**: Compare multiple models side-by-side

## 📦 Installation

```bash
# Clone the repository
git clone https://github.com/Zeesejo/german-llm-eval-toolkit.git
cd german-llm-eval-toolkit

# Install dependencies
pip install -r requirements.txt
```

## 🚀 Quick Start

```python
from german_eval import GermanEvaluator

# Initialize evaluator
evaluator = GermanEvaluator(model_name="occiglot-7b-de")

# Run perplexity evaluation
results = evaluator.evaluate_perplexity(
    dataset="news",
    samples=1000
)

print(f"Perplexity: {results['perplexity']:.2f}")
print(f"Token accuracy: {results['accuracy']:.2%}")
```

## 📊 Supported Models

- Occiglot-7B-de
- Occiglot-7B-eu5
- Llama-3-German-8B
- GPT-2-German
- Custom models (via Hugging Face)

## 🎓 Use Cases

### For Occiglot Contributors
Evaluate your fine-tuned models before submitting PRs:
```bash
python evaluate.py --model your-model-path --benchmark german-news
```

### For Researchers
Compare multiple German LLMs:
```python
from german_eval import ModelComparator

comparator = ModelComparator([
    "occiglot-7b-de",
    "llama3-german-8b"
])

results = comparator.run_benchmark_suite()
comparator.plot_results(save_path="comparison.png")
```

## 🗂️ Dataset Details

| Dataset | Size | Domain | Source |
|---------|------|--------|--------|
| German News | 10K | News | Tagesschau, DW |
| Wikipedia-DE | 5K | Encyclopedia | Wikipedia |
| Social Media | 3K | Informal | Twitter/X |
| Technical Docs | 2K | Technical | Open source docs |

## 🤝 Contributing to Occiglot

This toolkit is specifically designed to support [Occiglot](https://occiglot.eu/) contributions:

1. Evaluate your German model improvements
2. Generate metrics for your pull requests
3. Compare with baseline Occiglot models
4. Join the [Occiglot Discord](https://discord.com/invite/wUpvYs4XvM)

## 📈 Example Results

```
Model: Occiglot-7B-de
Dataset: German News (1000 samples)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Perplexity:        12.45
Token Accuracy:    87.3%
Fluency Score:     4.2/5.0
NER F1:            0.91
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

## 🛠️ Technical Details

**Technologies:**
- Python 3.8+
- PyTorch
- Transformers (Hugging Face)
- NumPy, Pandas
- Matplotlib for visualizations

**Metrics Implementation:**
- Perplexity: Standard language model perplexity calculation
- Fluency: Fine-tuned German BERT classifier
- NER: spaCy German model

## 📝 Citation

If you use this toolkit in your research, please cite:

```bibtex
@misc{german-llm-eval-toolkit,
  author = {Zeeshan Modi},
  title = {German LLM Evaluation Toolkit},
  year = {2026},
  publisher = {GitHub},
  url = {https://github.com/Zeesejo/german-llm-eval-toolkit}
}
```

## 🔗 Related Projects

- [Occiglot](https://github.com/occiglot) - European multilingual language models
- [Occiglot Evaluation Harness](https://github.com/occiglot/euro-lm-evaluation-harness)
- [German BERT](https://github.com/dbmdz/german-bert)

## 📄 License

MIT License - see LICENSE file for details

## 👤 Author

**Zeeshan Modi**
- GitHub: [@Zeesejo](https://github.com/Zeesejo)
- LinkedIn: [zeesejo](https://linkedin.com/in/zeesejo)
- Email: zeemaokik@gmail.com

M.Sc. AIIS student at University of Bremen, specializing in NLP and Computer Vision.

## 🙏 Acknowledgments

- [Occiglot team](https://occiglot.eu/) for the open-source multilingual LLM initiative
- DFKI and Hessian.AI for supporting European AI research
- University of Bremen AICOR Institute

---

**Status**: 🚧 Active Development | Contributions Welcome!

For questions or collaboration, join the [Occiglot Discord](https://discord.com/invite/wUpvYs4XvM) or open an issue.
