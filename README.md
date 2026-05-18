# [Time-Aware Complex Attention Space for Temporal Knowledge Graph Completion](https://github.com/AAristotle/TACAS)

This repository contains the implementation of **TACAS**, a Time-Aware Complex Attention Space model for temporal knowledge graph completion.

TACAS directly incorporates temporal information into entity representations and uses an attention mechanism in complex space to enhance the interaction among entities, relations, and timestamps.

## Installation

Create a conda environment with PyTorch and required packages:

```bash
conda create --name tacas_env python=3.8
conda activate tacas_env
conda install pytorch cudatoolkit -c pytorch
pip install numpy scikit-learn tqdm


Datasets
The raw datasets are placed under the src_data/ folder.

Before training, preprocess the datasets by running:

python process_icews.py
python process_timegran.py --tr 100 --dataset yago11k
python process_timegran.py --tr 1 --dataset wikidata12k
This will create the processed files in the data/ folder, which are required for training and evaluation.

Reproducing Results of TACAS
To reproduce the results of TACAS, run the following commands:

python learner.py --dataset ICEWS14 --model TACAS --rank 2000 --max_epochs 200 --learning_rate 0.1 --emb_reg 0.0075 --time_reg 0.2

python learner.py --dataset ICEWS05-15 --model TACAS --rank 2000 --max_epochs 200 --learning_rate 0.1 --emb_reg 0.004 --time_reg 0.5

python learner.py --dataset wikidata12k --model TACAS --rank 2000 --max_epochs 200 --learning_rate 0.1 --emb_reg 0.05 --time_reg 0.0025
The results and saved models will be stored under the results/ folder.

Citation
If you use this code, please cite the following paper:

@inproceedings{geng2025time,
  title={Time-Aware Complex Attention Space for Temporal Knowledge Graph Completion},
  author={Geng, Rushan and Luo, Cuicui},
  booktitle={Proceedings of the Pacific-Asia Conference on Knowledge Discovery and Data Mining},
  year={2025}
}
Acknowledgement
This implementation refers to previous temporal knowledge graph completion models such as TComplEx and TeLM. Thanks to the authors for their contributions to this research area.
