# BanglaDialecto: An End-to-End AI-Powered Regional Speech Standardization
<p align="center">
  <strong>Official Implementation for IEEE BigData 2024 Submission</strong>
</p>


## Abstract
This project focuses on recognizing Bangladeshi
dialects and converting diverse Bengali accents into standardized formal Bengali speech. No notable works have been done accurately in Bangla dialects due to a shortage of diverse and large datasets and relying on traditional approaches. Our approach developed a large dataset of dialectal speech signals for fine-tuning LLMs for two tasks, one
is dialect speech recognition, and the other one is translating the dialect text to standard Bangla text. Our whisper fine-tuned model achieved a CER of 0.8% and a WER of 1.5%. In the case of translation, the BanglaT5 model attained a BLEU score of 41.6% for dialect-to-standard
text translation. Finally, by utilizing AlignTTS, we completed our end-to-end pipeline for dialect standardization.

[Here is the available Noakhali Dialect Dataset(NDD)](ASRDataset)
--
### Dataset Statistics
<img width="326" alt="2024-09-10" src="https://github.com/user-attachments/assets/16e4d0d8-2b1b-4167-8b49-7d2539b88a94">
--


## Methodology
1.**Data Preprocessing:** Converting audio input signal into wav form then it undergoes the process
of noise reduction and splitting into manageable 5-second speech segments; similarly, dialect text and standard text are segmented into corresponding chunks.

2.**Fine-Tuning:** Dialect speeches and dialect texts are used to fine-tune LLM for transcript speech and other LLM has been finetuned for MT  from dialect text to standard Bangla text. Finally, AlignTTS has been used for generating standard Bangla speech signal from translated standard Bangla text.

3.**Evaluation:** Cer, wer, bleu scores are used to measure models performances. 

!<img width="648" alt="2024-09-10 (2)" src="https://github.com/user-attachments/assets/17758596-993a-455b-872c-63753c71d9d1">
<strong>Fig. 1: (a) Data preprossing [1]; (b) Fine tuning LLMs [2]; (c) End to End generation</strong>

## Result
#### Comparative evaluation of pretrained and fine-tuned models on dialect speech-to-text and dialect text to standard text translation tasks.


!<img width="658" alt="2024-09-10 (3)" src="https://github.com/user-attachments/assets/583ab084-4701-459c-93aa-7dcdbba1ae25">

### 1. Clone the Repository
```bash
git clone https://github.com/EncryptedBinary/BanglaDialecto.git
cd BanglaDialecto
```
2. Install Required Packages
Run the following commands to install the necessary libraries:
```python 
!pip install transformers 
!pip install jiwer


## 🧪 Train-Test-Split
- **Training**: 6270 samples
- **Validation**: 810 samples
- **Testing**: 120 samples

Feel free to modify the splits or experiment with different datasets based on your use case.

## 📚 Model Training

For those interested in fine-tuning the models further, we recommend checking out the `train.py` script, which includes hyperparameters and configurations for:

- **Epochs**:  All models are trained for 10 epochs, 16 batches for ASR, 25 epochs, and 6 batches for translation.
- **Loss Function**: 
- **Optimization**:
### References
[1] M. A. Al Amin, M. T. Islam, S. Kibria, and M. S. Rahman, “Continuous
bengali speech recognition based on deep neural network,” in 2019
international conference on electrical, computer and communication
engineering (ECCE). IEEE, 2019, pp. 1–6. (https://ieeexplore.ieee.org/document/8679341)
[2] S. Khan, M. Pal, J. Basu, M. S. Bepari, and R. Roy, “Assessing
performance of bengali speech recognizers under real world conditions
using gmm-hmm and dnn based methods.” in SLTU, 2018, pp. 192–196. (https://www.researchgate.net/publication/328068468_Assessing_Performance_of_Bengali_Speech_Recognizers_Under_Real_World_Conditions_using_GMM-HMM_and_DNN_based_Methods)
[3] A. M. Samin, M. H. Kobir, S. Kibria, and M. S. Rahman, “Deep
learning based large vocabulary continuous speech recognition of an
under-resourced language bangladeshi bangla,” Acoustical Science and
Technology, vol. 42, no. 5, pp. 252–260, 2021. (https://www.jstage.jst.go.jp/article/ast/42/5/42_E2079/_article/-char/ja/)
[4] P. R. Gudepu, G. P. Vadisetti, A. Niranjan, K. Saranu, R. Sarma,
M. A. B. Shaik, and P. Paramasivam, “Whisper augmented end-toend/hybrid speech recognition system-cyclegan approach.” in INTERSPEECH, 2020, pp. 2302–2306. (https://www.isca-archive.org/interspeech_2020/gudepu20_interspeech.html)


