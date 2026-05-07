# Aquifer Petrignano CV Assignment

This is my notebook for the Aquifer Petrignano cross-validation exercise.

The target is `Depth_to_Groundwater_P25` (DP25). I predict each month using the values from the previous two months. The main comparison is between shuffled KFold and TimeSeriesSplit.

## Files

- `aquifer_petrignano_cv_comparison.ipynb` - notebook for the assignment
- `petrignanos.csv` - dataset
- `VIDEO_SCRIPT.md` - short outline for the recording
- `requirements.txt` - packages used

## Run It

Open the notebook and run all cells from top to bottom.

If using Colab, upload `petrignanos.csv` when the notebook asks for it.

## Current Results

Fixed model:

- Naive KFold CV R2: `0.9085`
- TimeSeriesSplit CV R2: `-0.4161`
- Independent test R2: `-0.0898`

Grid search:

- Naive KFold internal CV R2: `0.9129`
- Naive KFold test R2: `-0.0996`
- TimeSeriesSplit internal CV R2: `0.0732`
- TimeSeriesSplit test R2: `0.2059`

My takeaway: shuffled KFold gives a very high internal score, but it does not transfer well to the future test months. TimeSeriesSplit is more realistic for this type of time-ordered data.

## Colab Link

After I upload this project to GitHub, I can add the Colab badge using this format:

```markdown
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/YOUR_REPO/blob/main/aquifer_petrignano_cv_comparison.ipynb)
```
