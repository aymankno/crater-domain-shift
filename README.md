# crater-domain-shift

ResNet18 trained on lunar craters yet tested on Mars, investigating why a crater detector trained on the moon fails on Mars.

## Instructions
1. Download the datasets listed below and update the folder paths in 'craters.ipynb'
2. Run all cells in order: the model trains on Moon data and evaluates on the Moon holdout set
3. To test domain shift, find the evaluation cell and replace 'test_loader' with:
   mars_loader = DataLoader(testing_set, batch_size=32, shuffle=False)
Then, rerun to see the model's accuracy on Mars.



## RESULTS:
- Moon testing accuracy - 100%
- Mars testing accuracy - 51%
- Finding: Pixel desnsities between Mars and Moon imagery differ significantly; suggesting albedo and brightness shift make it near impossible for a model trained on Moon imagery to detect Martian craters. Refer to 'craters_charts.ipynb'

## DATASETS: 
- Moon (training)
    - [LUNA 1](https://github.com/droneslab/Luna-1) - CRATERS
    - [Lunar Surface Dataset](https://www.kaggle.com/datasets/filippopelosi/lunar-surface-dataset) - NON-CRATERS
- Mars (testing)
    - [HiRISE Dataset](https://www.kaggle.com/datasets/filippopelosi/lunar-surface-dataset) — filter for labels `0` and `1` to sort.

## CITATIONS:
- Chase Jr, T. & Dantu, K. (2024). MARs: Multi-view Attention Regularizations for Patch-based Feature Recognition of Space Terrain. ECCV 2024.
- Wagstaff, K. et al. HiRISE Landmark Dataset. DOI: 10.5281/zenodo.2538136
- Pelosi, F. Lunar Surface Dataset. Kaggle.