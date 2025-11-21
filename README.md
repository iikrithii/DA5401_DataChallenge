## DA5401 End-Semester Data Challenge - Metric Learning

### Project overview:
This repository contains the notebooks and report for the DA5401 metric learning challenge. The goal is to predict a fitness score (0 to 10) that measures how well a prompt-response pair matches a given evaluation metric embedding.

## Setup and install
1. Create and activate a virtual environment (recommended).
2. Install required packages:
   pip install -r requirements.txt


## Files included
- data_generator.ipynb : Notebook to create embeddings for the conversation text and split it into required parts and create augmented data. 
- final.ipynb : Main notebook that performs feature engineering, model training, validation and creates raw predictions.
- post_processing.ipynb : Notebook to apply rule-based adjustments and create final submission file. 
- requirements.txt : Python package list required to run the notebooks and scripts.
- submission.csv : The submission file used for the challenge. 
- README.md : This file.

## Execution order
1. Run the data generator notebook to compute and save text embeddings and preprocess the augmentation files. 
   - File: data_generator.ipynb
   - How to run: Open the notebook in Jupyter and execute cells top to bottom 
2. Run the main training and inference notebook.
   - File: final.ipynb
   - How to run: Open the notebook and execute cells in order  
3. Run the post processing notebook to apply heuristic adjustments and produce the final submission.
   - File: post_processing.ipynb
   - How to run: This file needs a GROQ API key, and the fasttext .bin file for execution. Open the notebook and replace the groq key, and make sure the fasttext file is on the same directory and execute cells. 

Notes and tips
- Run the notebooks in the specified order. Embeddings must exist and be correctly loaded by final.ipynb for the pipeline to work.
- The notebooks rely on external APIs for translation or language processing. Provide API keys via environment variables or a .env file. 
- If you encounter memory issues when computing embeddings, use a smaller batch size or a smaller embedding model and save intermediate results to disk.
