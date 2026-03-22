# Exploring Causal Effect of Social Bias on Faithfulness Hallucinations (CIKM 2025)
<!-- Badges -->
![datasets](https://img.shields.io/badge/datasets-5%2F5-lightgrey)
[![arXiv](https://img.shields.io/badge/arXiv-2508.07753-b31b1b.svg)](https://arxiv.org/abs/2508.07753)
[![ACM](https://img.shields.io/badge/ACM-10.1145/3746252.3761298-blue)](https://dl.acm.org/doi/10.1145/3746252.3761298)
[![CIKM 2025](https://img.shields.io/badge/CIKM-2025-blue)](https://cikm2025.org/)


## 📖 Overview

This repository contains (soon) the official resources for the paper ​​"**Exploring Causal Effect of Social Bias on Faithfulness Hallucinations in Large Language Models**"​​ accepted at CIKM 2025.

This research presents the first systematic investigation into the causal relationship between social bias and faithfulness hallucinations in Large Language Models (LLMs), introducing a novel causal inference framework based on Structural Causal Models (SCM) and the Bias Intervention Dataset (BID).
> 📄 Paper: [arXiv:2508.07753](https://arxiv.org/abs/2508.07753) | [ACM](https://dl.acm.org/doi/10.1145/3746252.3761298)

## 🎯 Key Contributions

1. Establishing Causal Relationship Between Bias and Hallucinations
​​First to demonstrate​​ that social bias is a significant cause of faithfulness hallucinations in LLMs
Proposed bias intervention method based on do-calculus to effectively control confounders
Defined three bias states: Pro-stereotype, Anti-stereotype, and Non-stereotype
![](./assets/intro.png)


2. Novel Causal Measurement Methodology
Introduced Individual Causal Effect (ICE) and Unified Causal Significance (UCS) metrics
Employed McNemar's Test for rigorous causal significance testing
Supports systematic causal analysis across multiple models and bias types
![](./assets/causal_graph.png)


3. Bias Intervention Dataset (BID)
​​Scale​​: 11k+ carefully constructed instances
​​Bias Coverage​​: Age, Gender, Disability, Religion, Socioeconomic Status (SES)
​​Key Features​​: Controlled bias states, paired intervention design, unfairness hallucination annotations ![](./assets/main_figure_1213.png)

4. Discovery of Unfairness Hallucinations: ​​First formal definition​​ of unfairness hallucinations
Revealed that bias primarily affects unfairness hallucinations with no significant effect on common hallucinations
Discovered that unfairness hallucinations exhibit higher model confidence, making them harder to detect

## 📁 File Structure

```
BID/
├── assets/                    # Figures used in the paper
├── dataset/                   # Bias Intervention Dataset (BID)
│   ├── age_final.csv          # Age bias dataset
│   ├── disability_final.csv   # Disability bias dataset
│   ├── gender_final.csv       # Gender bias dataset
│   ├── religion_final.csv     # Religion bias dataset
│   └── ses_final.csv          # Socioeconomic status bias dataset
├── LICENSE                    # MIT License
└── README.md                  # Project documentation
```

### Dataset Format

Each CSV file contains the following columns:

| Column | Description |
|--------|-------------|
| `Q_id` | Question group identifier |
| `id` | Unique instance identifier |
| `Category` | Bias category (Age, Gender, Disability, Religion, SES) |
| `BiasType` | Bias type: pro / anti |
| `QuestionType` | Question type: negative / non_negative |
| `name_group_map` | Mapping of name groups |
| `names` | Names used in the context |
| `words` | Key words for the scenario |
| `candidates` | Candidate answer options |
| `Context` | Input context for the model |
| `Difficult_Context` | Difficult version of the context (if applicable) |
| `Question` | Question to be answered |
| `answer` | Ground truth answer |
| `bias_answer` | Biased answer option |
| `irrelevant_answer_0` | First irrelevant answer option |
| `irrelevant_answer_1` | Second irrelevant answer option |

## 📝 Citation

If you find this work useful, please cite our paper:

```bibtex
@inproceedings{10.1145/3746252.3761298,
  author = {Zhang, Zhenliang and Zhang, Junzhe and Hu, Xinyu and Zhang, Huixuan and Wan, Xiaojun},
  title = {Exploring Causal Effect of Social Bias on Faithfulness Hallucinations in Large Language Models},
  year = {2025},
  isbn = {9798400720406},
  publisher = {Association for Computing Machinery},
  address = {New York, NY, USA},
  url = {https://doi.org/10.1145/3746252.3761298},
  doi = {10.1145/3746252.3761298},
  booktitle = {Proceedings of the 34th ACM International Conference on Information and Knowledge Management},
  pages = {4293–4303},
  numpages = {11},
  keywords = {causality, hallucination, social bias in llms},
  location = {Seoul, Republic of Korea},
  series = {CIKM '25}
}
```

## 🙏 Acknowledgments

This research was supported by Beijing Science and Technology Program (Z231100007423011) and Key Laboratory of Science, Technology and Standard in Press Industry (Key Laboratory of Intelligent Press Media Technology).
