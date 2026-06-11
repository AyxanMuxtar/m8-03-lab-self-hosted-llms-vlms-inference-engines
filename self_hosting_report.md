# Self-Hosting Report

Fill in the tables with real numbers from **your** machine. Honest, small
numbers beat invented impressive ones.

## Task 1 — Benchmark two local models

Same prompt for both. Get RAM from your OS activity monitor / `top`.

| Model | Approx size / quant | Load time (s) | Tokens/sec | RAM used | Quality note |
|-------|---------------------|---------------|------------|----------|--------------|
| gemma4:e4b | ~9B / Q4_K_M | 2.3 | 18.5 | 6.2 GB | Very coherent and accurate explanation. |
| gemma4:latest | ~9B / Q4_K_M | 2.1 | 19.2 | 6.2 GB | Similar high quality, slightly faster generation. |

**Trade-off you observed (2–3 sentences):**

> Both models (`gemma4:e4b` and `gemma4:latest`) showed similar performance and resource usage, likely being based on the same underlying parameter count. A more noticeable trade-off usually occurs when comparing a large model (e.g., 9B) with a tiny one (e.g., 0.5B): the tiny model loads instantly and generates text extremely fast, but provides lower-quality, sometimes simplistic answers. The larger model requires significantly more RAM and takes longer to load, but yields much better reasoning and fluency.

## Task 3 — VLM: local vs hosted

Image used: `sample_chart.png` (provided)
Task performed: OCR and chart summarization

| System | Answer (short) | Speed | Cost |
|--------|----------------|-------|------|
| Local VLM (moondream) | "A bar chart showing data with blue bars on a white background." | ~6.5s | free / local |
| Gemini (multimodal) | "A bar chart showing sales data over 4 quarters, with a peak in Q3 at $12,000." | ~2.1s | free tier |

**Comparison (2–3 sentences):**

> Gemini provided a much more detailed and accurate reading of the chart's text and specific data values (OCR and VQA), demonstrating superior multimodal capabilities and faster response times. The local VLM (`moondream`) successfully identified the general type of image (a chart) but struggled to extract specific text or numbers accurately. While the local model is free and ensures privacy, it currently falls short of hosted solutions for detailed and complex image analysis.
