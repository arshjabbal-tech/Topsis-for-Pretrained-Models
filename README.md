# TOPSIS for Pretrained Models (Text Generation)

## Project Overview

This project applies the TOPSIS (Technique for Order Preference by Similarity to Ideal Solution) method to select the best pretrained model for text generation based on multiple evaluation criteria.

The analysis was performed using my own Python package:

**Topsis-Arshdeep-102303561**, 
which was developed and uploaded to TestPyPI.

---

## Objective

- Evaluate pretrained text generation models.
- Compare models using multiple criteria.
- Apply TOPSIS algorithm for ranking.
- Identify the best model based on TOPSIS score.

---

## Dataset

The dataset was prepared in CSV format and contains different pretrained models evaluated on multiple performance metrics.

| Model         | Perplexity | Time (sec) | Size (MB) | BLEU Score |
|--------------|-----------|-----------|-----------|-----------|
| gpt2         | 20        | 0.8       | 500       | 32        |
| distilgpt2   | 25        | 0.5       | 300       | 29        |
| gpt-neo-125M | 18        | 1.2       | 750       | 35        |
| opt-350m     | 22        | 0.9       | 700       | 33        |

### Criteria Explanation

- Perplexity → Lower is better (cost criteria)
- Time → Lower is better (cost criteria)
- Size → Lower is better (cost criteria)
- BLEU Score → Higher is better (benefit criteria)

---

## Installation

Install the TOPSIS package:
pip install Topsis-Arshdeep-102303561

---

## Usage

Run TOPSIS analysis using the package:
python3 -m topsis_arshdeep.main models_data.csv "1,1,1,1" "-,-,-,+" result.csv


Parameters:

- Input CSV file
- Weights
- Impacts
- Output result file

---

## Output

The output file `result.csv` contains:

- TOPSIS score
- Ranking of models
- 
| Model        | Perplexity | Time (sec) | Size (MB) | BLEU | TOPSIS Score | Rank |
|--------------|------------|------------|-----------|------|--------------|------|
| gpt2         | 20         | 0.8        | 500       | 32   | 0.5735       | 2    |
| distilgpt2   | 25         | 0.5        | 300       | 29   | 0.7449       | 1    |
| gpt-neo-125M | 18         | 1.2        | 750       | 35   | 0.2551       | 4    |
| opt-350m     | 22         | 0.9        | 700       | 33   | 0.3209       | 3    |


The model with the highest TOPSIS score is selected as the best pretrained model.

### Best Model According to TOPSIS

Based on the TOPSIS ranking, **distilgpt2** is selected as the best pretrained
text generation model, as it achieves the highest TOPSIS score (Rank 1) while
maintaining low inference time and smaller model size.
---

## Tools Used

- Python
- Pandas
- TOPSIS Algorithm (Custom Package)

---

## License

© 2026 Arshdeep Kaur

This reopsitory is licensed under MIT License. See LICENSE for details.
