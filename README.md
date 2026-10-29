# Pro-Active Inference
This repository accompanies the paper "[Pro-Active Inference](https://arxiv.org/abs/2610.34681)."

**A note on data:** all cleaned datasets can be found in the `datasets.zip` file in our `datasets` directory . Please unzip this compressed file before running our experimental, analysis, and visualizing scripts. The `data_processing.ipynb` notebook contains our exact procedures for pre-processing and cleaning each dataset: this includes feature selection, train/test splitting, initial model fitting, and saving standardized data structures to file, as appropriate. URLs to raw dataset sources are also provided in this notebook.

**A note on compute:** all experiments in this paper were run on either one NVIDIA H100 GPU with 80 GB of VRAM or one NVIDIA RTX PRO 6000 Blackwell with 96 GB of VRAM, with any single parallelized run completing in well under one minute.

**A note on reproducibility:** all main text and appendix figures in our paper can be reproduced exactly using the code provided in this repository. For transparency, we include all of our intermediate logs, diagnostics, and summaries in the `logs`, `diagnostics`, and `summaries` directories, respectively.

**Workflow for reproducing all main text and appendix results and figures:** We assume that `datasets.zip` has been unzipped into the `datasets` directory. Alternatively, one can run all the cells in `data_processing.ipynb`.
1. Run all notebooks in `1. acs` through `7. ulb`, corresponding to the eight datasets in our numerical experiments. Note that `5. llm-evals` supports both MMLU-Pro and our concatenated BBH+GPQA+IFEval+MATH+MuSR suite. The notebooks in each folder generate results logs for PAI, Uniform, PPI, PPAT, and SAI.
2. Run `pai_ablation.ipynb` in the main directory to perform the frozen-ML PAI ablations for the non-LLM-evaluation datasets. Run `llm_evals_pai_ablation.ipynb` in the `5. llm-evals` directory to perform the frozen-ML PAI ablations for our two LLM evaluation testbeds.
3. Run `analyzer.ipynb` to generate summaries of the raw results logs.
4. Run `diagnostics.ipynb` to compute our retrospective diagnostics (e.g., IRB, ECB, and IVR).
5. Run `visualizer.ipynb` to generate all main text and appendix figures.

All scripts contain extensive comments for user understanding and clarification.

