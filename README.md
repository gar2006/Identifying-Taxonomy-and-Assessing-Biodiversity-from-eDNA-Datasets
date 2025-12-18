# eDNA_Classification_SIH


1.**Title**
eDNA Fish Species Classification using Deep Learning

2.**Overview**
Briefly describe the core task: classifying fish species from synthetic eDNA sequences using a multimodal transformer neural network.

Mention environmental metadata integration (e.g., water temperature, pH, dissolved oxygen, etc.).

State the end goal: provide an automated pipeline to predict species from sequence and environment data.​

3.**Dataset**
Synthetic eDNA sequences for 15 fish species, enriched with location and environmental features./generated from Gemini/chatGPT

Example columns: sampleid, sequence, species, family, location, habitat type, sampling method, collection date, read count, water temperature, pH, dissolved oxygen, conductivity, latitude, longitude, sequence length, GC content.​

4.**Model and Features**
Species embeddings for this pipeline were initially derived using DNABERT-2, and our implementation can be extended to support species-aware DNABERT-S models for improved clustering and unsupervised species identification

Custom DNA tokenizer for sequence encoding and handling IUPAC ambiguity.

Transformer-based neural network combining DNA sequence and environmental features.

Attention mechanism and multimodal fusion for high classification accuracy.

Achieved 100% validation accuracy on synthetic data (with early stopping at 16 epoch).​

5.**Training and Evaluation**
Split into train/validation/test sets.

6.**Training**: AdamW optimizer, cross-entropy loss, ReduceLROnPlateau scheduler, early stopping.

Evaluation includes classification reports, confusion matrix, and metric visualizations alongside test accuracy scores.​

7.**Results**
Model achieves near-perfect performance on test and validation splits.

Visualizations provided: species/family distribution, environmental data scatterplots, training and accuracy curves, confusion matrix.​

8.**How to Use**
Instructions for loading the model and making predictions are included in the notebook.

Example code for using the trained pipeline and for integrating external models (e.g., DNABERT-2 via Hugging Face, with Triton-free setup).​

9.**File/Component references:**

bestednaclassifier.pth: model weights

dnatokenizer.pkl: custom DNA tokenizer

labelencoder.pkl: label encoder

modelconfig.json: model configuration

traininghistory.json: training metrics

ednafishclassificationdataset.csv: source dataset

10.**Requirements**
Python 3.

11.**Required libraries**: pandas, numpy, matplotlib, seaborn, scikit-learn, PyTorch, transformers.​

12.**Example Output**
Example prediction block shows how to load model and get predicted species with confidence scores.​

13.**Extending/Deploying**
Outlines potential improvements: using pre-trained DNA models (DNABERT, NT), real-world dataset scaling, external API/database integration, additional feature engineering, active learning and uncertainty quantification.​

14.**Conclusion / Key Takeaways**
Summarizes pipeline highlights and future applicability.

15.Other Files
Consider brief descriptions for .pkl, .json, and .pth files (“Saved model weights”, “Token vocabulary”, “Label encoder mapping”, “Config/metrics for experiments”).

**If you export the notebook to a .py script, clarify its function (“Runnable training and inference pipeline”).**
