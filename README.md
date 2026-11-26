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

## Data Sources with URL, Description, Schema
### Data source A
**Title**: Hugging Face Hub Stats (Models table subset)

**Source URL**: https://huggingface.co/datasets/cfahlgren1/hub-stats

**Original Schema** : id, author, cardData, inferenceProviderMapping, lastModified, likes, trendingScore, config, downloads, downloadsAllTime, tags, pipeline_tag, library_name, siblings, createdAt, safetensors, transformersInfo, baseModels, gguf

**Schema after pre-processing** : id(e.g. 'model name/huggnig face account used to upload'), downloads, tag(processed to only contain arxiv id), pipeline_tag, createdAt

**Description** : This dataset contains information on Models on the Hugging Face Hub. The pre-processed data contains **the arxiv id** for the paper(s) the model is featured on (which we used for joining two datasets), model and the account name, how many download it has, when it was created, and what task the model does.

### Data source B
Title: arXiv Metadata snapshot
Source URL:  https://huggingface.co/datasets/librarian-bots/arxiv-metadata-snapshot



## Repo structure
```
models-on-paper/
├── README.md
├── requirements.txt
├── .gitignore
└── 01_hubstat_rdd.ipynb   # loads Hugging Face models from GCS, extracts arXiv IDs, saves to processed/hub_stats
```
