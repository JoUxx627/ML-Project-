## Datasets

The datasets are not stored in this repository. Download each one from its original source, unzip it into a local `data/` folder (git-ignored), and keep the layout below so every notebook finds the files.

| Part | Dataset | Source | Notes |
|------|---------|--------|-------|
| A (regression) | Used Cars Price Prediction | https://www.kaggle.com/datasets/avikasliwal/used-cars-price-prediction | Use only the labeled file (the one with the `Price` column). |
| B (images) | Flowers Recognition | https://www.kaggle.com/datasets/alxmamaev/flowers-recognition | 5 classes: daisy, dandelion, rose, sunflower, tulip (4,242 images). |
| C (text) | BBC News (raw text files) | http://mlg.ucd.ie/datasets/bbc.html | 5 classes: business, entertainment, politics, sport, tech (2,225 articles). |

Expected layout after download:

```
ML_Collage_Project/
└── data/
    ├── part_a_numerical/   <- used-car file(s)
    ├── part_b_images/      <- flowers/ (one folder per class)
    └── part_c_text/        <- bbc/ (one folder per category)
└── Names/
    ├── Youssef Elyamani
    
```

**Citation (BBC News):** D. Greene and P. Cunningham, "Practical Solutions to the Problem of Diagonal Dominance in Kernel Document Clustering", Proc. ICML 2006. All rights in the original articles are owned by the BBC.
