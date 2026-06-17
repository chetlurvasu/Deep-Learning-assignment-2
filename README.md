# Deep-Learning-assignment-2

# MEG Brain-State Classification

Deep learning models that classify 248-channel MEG recordings into four cognitive states: **rest, motor, working memory, and story/math**. We compare four architectures (LF-CNN, EEGNet, CNN-LSTM, and a supervised contrastive variant) under both intra-subject and cross-subject evaluation, and select the compact **LF-CNN** as the final model.

INFOMDLR Deep Learning Project, Utrecht University.
Authors: Chetlur Vasundhara, Ravi Pogaku, Gayathri S Warrier, Ilayda Taliç.

## Data

Not included — download from the assignment link (password `123`) and unzip into a `data/` folder so you have `data/Intra/` and `data/Cross/`. Files are `.h5`, each a 248 × 35624 matrix.

## Setup

```bash
pip install -r requirements.txt
```

## Run

```bash
python train.py --setting intra   # intra-subject (5-fold CV)
python train.py --setting cross   # cross-subject (train on 2 subjects, test on 3 unseen)
```
<!-- ← adjust script names/flags to match your code -->

## Results

| Model    | Params | Intra | Cross |
|----------|--------|-------|-------|
| CNN-LSTM | ~250k  | 0.56  | 0.44  |
| EEGNet   | ~13k   | 0.84  | 0.52  |
| LF-CNN   | 4.4k   | 0.48  | 0.58  |
| SupCon   | ~13k   | 0.48  | 0.25  |

See the paper for full details.
