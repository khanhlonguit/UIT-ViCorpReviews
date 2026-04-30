<div>

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/3/38/Logo_UIT_updated.jpg" alt="UIT" height="80"/>
  &nbsp;&nbsp;&nbsp;
  <img src="https://www.yuntech.edu.tw/images/mainmenu/about/yuntech_logo.jpg" alt="YunTech" height="80"/>
</p>

<h1 align="center">UIT-ViCorpReviews: A Benchmark Dataset for Multi-Dimensional Sentiment and Toxic Detection in Vietnamese Workplace Context</h1>

</div>

<p align="center">
  <img src="https://i.postimg.cc/G3Dh1BLX/our-pipeline.png" alt="UIT" height="40%"/>
</p>

This repository contains the official implementation for **UIT-ViCorpReviews** - a novel benchmark dataset curated and annotated for two tasks: Aspect-based Sentiment Analysis (ABSA) and Toxic Sequence-level Detection (TSD).

This dataset serves as a foundational benchmark to foster future research in pattern recognition and natural language understanding within the corporate domain.


## Structure

```text
├── data-raw/
│   └── data_raw.csv         # Original, unprocessed crawled data
├── data/
│   └── data_cleaned.csv     # Data after text normalization & noise removal
├── data-absa/               # Aspect-Based Sentiment Analysis (ABSA) Split
│   ├── data.csv             # Full dataset for ABSA task
│   └── file_split/
│       ├── aspects.json     # Aspect categories metadata
│       ├── aspect_cols.json # Aspect column mappings
│       ├── label2id.json    # Label to ID mappings
│       ├── train.csv        # Training set for ABSA task
│       ├── val.csv          # Validation set for ABSA task
│       └── test.csv         # Test set for ABSA task
└── data-tsd/                # Toxic Sequence-level Detection (TSD) Split
    ├── data.csv             # Full dataset for TSD task
    └── file_split/
        ├── train.csv        # Training set for TSD task
        ├── dev.csv          # Validation set for TSD task
        └── test.csv         # Evaluation set for TSD task
```

## Citation

If you use this framework or our findings in your research, please consider citing our paper.

```bibtex
@misc{long2026uitvicorpreviews,
  author    = {Khanh-Long Ho-Vuong, Nhat-Huy Dang, Bao Do, Huy To Quoc},
  title     = {UIT-ViCorpReviews: A Benchmark Dataset for Multi-Dimensional Sentiment and Toxic Detection in Vietnamese Workplace Context},
  year      = {2026},
  publisher = {},
  journal   = {},
  howpublished = {\url{https://anonymous.4open.science/r/UIT-ViCorpReviews/}},
}
```

