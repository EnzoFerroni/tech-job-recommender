# Tech Job Recommender: Applied Project III

[![Python](https://img.shields.io/badge/Python-3-3776AB?logo=python&logoColor=white)](https://www.python.org)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-TF--IDF-F7931E?logo=scikitlearn&logoColor=white)](https://scikit-learn.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)](https://jupyter.org)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

A content-based recommender that matches tech professionals to job openings using TF-IDF with n-grams and cosine similarity.

## Table of Contents

- [About](#about)
- [Method](#method)
- [Results](#results)
- [Getting Started](#getting-started)
- [Documents](#documents)
- [Team](#team)
- [License](#license)

## About

Applied Project III of the Data Science program at Universidade Presbiteriana
Mackenzie (2026). The project looks at the mismatch between the profiles of tech
professionals (skills and seniority) and the requirements of job postings, and
builds a recommender that suggests the most relevant openings for a given profile.
It extends the earlier
[ProjetoIA-RecomendacaoVagas](https://github.com/EnzoFerroni/ProjetoIA-RecomendacaoVagas).
Documents and the notebook are in Portuguese.

## Method

1. **Cleaning.** Starting from 50,000 postings in the
   [AI-Powered Job Recommendations](https://www.kaggle.com/datasets/samayashar/ai-powered-job-recommendations/data)
   dataset, filters on industry (Software, IT), title keywords and skill count reduce
   it to 1,021 highly relevant postings, removing about 98% of the noise.
2. **Feature engineering.** A combined text profile (title, experience and skills),
   lowercased, with custom HR stop words removed ("job", "position", "required"...).
3. **Vectorization.** TF-IDF with unigrams and bigrams, limited to the 500 most
   informative features.
4. **Tuning.** Two adjustments compared against the baseline: custom stop words and
   experience-level weighting (Entry 1.0, Mid 0.8, Senior 0.5).
5. **Evaluation.** Precision@5, checking whether the original posting appears in the
   top five recommendations.

## Results

The best Precision@5 came from combining the job title with bigrams. Qualitatively,
the top five suggestions for a simulated candidate (for example "Python, Machine
Learning") matched the candidate's hard skills.

## Getting Started

```bash
git clone https://github.com/EnzoFerroni/ProjetoAplicadoIII.git
cd ProjetoAplicadoIII
pip install pandas scikit-learn matplotlib seaborn jupyter
jupyter notebook notebook/AnaliseExploratoria.ipynb
```

## Documents

- Report: [`docs/ProjetoAplicadoIII.pdf`](docs/ProjetoAplicadoIII.pdf)
- Community presentation: [`docs/ApresentacaoComunidade.pdf`](docs/ApresentacaoComunidade.pdf)
- Presentation video: [YouTube](https://www.youtube.com/watch?v=6CZDkbzrX5c)

## Team

| Name | GitHub |
| --- | --- |
| Daniel dos Santos da Silva | [@Daniels-S](https://github.com/Daniels-S) |
| Enzo Ferroni | [@EnzoFerroni](https://github.com/EnzoFerroni) |
| Vinícius de Souza Sabiá | [@viniciussabia](https://github.com/viniciussabia) |

## License

Code and documents are released under the [MIT License](LICENSE). The dataset belongs
to its Kaggle author and is redistributed under its original terms.
