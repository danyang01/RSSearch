# Introduction

RSSearch (RNA Similarity Search) is a deep learning method used for efficient and accurate RNA remote homology detection.

# Installation

### 1. RNA-FM preprocessing of RNA sequences

Download and process in RNA-FM environment ( reference https://github.com/ml4bio/RNA-FM ).

    git clone https://github.com/ml4bio/RNA-FM.git
    cd RNA-FM
    conda env create -f environment.yml
    conda activate RNA-FM

Processing in RNA-FM environment.

    cd ./redevelop

Preprocessing script.

    python launch/predict.py \
        --config="pretrained/extract_embedding.yml"\
        --data_path="path/to/input/file.fasta" \
        --save_dir="path/to/save/embedding"\
        --save_frequency 1\
        --save_embeddings\
        --device="cpu"

We can obtain RNA embeddings processed with RNA-FM.

### 2. RSSearch Processing RNA Embeddings

Download and process in RNA environment.

    git clone https://github.com/danyang01/RSSearch.git
    cd RSSearch
    conda env create -f environment.yml
    conda activate RNA

Processing in RNA environment.
Processing script.

    python predict.py \
        --model_path="model/model_3_1.pth" \
        --test_csv="All data/testing_data.csv" \
        --npy_path="embedding/representations/" \
        --output_csv="output/similarity.csv"

We can obtain RNA similarity through the RSSearch model.


