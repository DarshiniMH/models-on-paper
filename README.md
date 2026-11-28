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
├── 01_hubstat_rdd.ipynb   # loads Hugging Face models from GCS, extracts arXiv IDs, saves to processed/hub_stats
└── 01_arxiv_rdd.ipynb     # loads arXiv metadata from GCS, cleans categories and dates, saves to processed/arxiv
```

### Data source B
- **Title**: arXiv Metadata Snapshot
- **Source URL**: https://huggingface.co/datasets/librarian-bots/arxiv-metadata-snapshot
- **Data description**: This dataset has metadata for 3,224,635 arXiv papers. The pre-processed data contains **the arxiv id** (used for joining the two datasets), the paper title, its research categories, and the date and year the paper was first published. Raw data is stored in `gs://modelsonpaper/arxiv/` and the pre-processed output in `gs://modelsonpaper/processed/arxiv/`.
- **Original Schema** : id, submitter, authors, title, comments, journal-ref, doi, report-no, categories, license, abstract, versions, update_date, authors_parsed
- **Schema after pre-processing** : id(arXiv id, e.g. '0905.0034'), title, primary_category(e.g. 'math.RT'), categories, first_version_date, year
