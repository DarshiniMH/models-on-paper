# Models on Paper

How research papers on arXiv turn into open models on Hugging Face.

## Team
- Aeri Lee
- Rini Khaneja
- Darshini Mysore Harishwara

## Problem statements
1. **Which research fields drive model downloads and is it concentrated in few popular fields?** how many models are built/downloaded for each arXiv category and see which specific category/field(s) is popular?
2. **How fast does research become a model?** For each paper, the time from its first arXiv version to the first Hugging Face model that cites it, is that gap shrinking from 2022 to 2026?
3. **Do papers from one field get used for a different task ?** Whether papers from one field used for a different task (computer vision to language model or vice versa) and also if a single model/paper cites from two different categories?

## Repo structure
```
models-on-paper/
├── README.md
├── requirements.txt
├── .gitignore
└── 01_hubstat_rdd.ipynb   # loads Hugging Face models from GCS, extracts arXiv IDs, saves to processed/hub_stats
```
