<div align="center">

# Master Thesis
## Improving Cross-Lingual Representations by Distilling Multilingual Encoders into Monolingual Components

<a href="https://pytorch.org/get-started/locally/"><img alt="PyTorch" src="https://img.shields.io/badge/PyTorch-ee4c2c?logo=pytorch&logoColor=white"></a>
<a href="https://pytorchlightning.ai/"><img alt="Lightning" src="https://img.shields.io/badge/-Lightning-792ee5?logo=pytorchlightning&logoColor=white"></a>
<a href="https://hydra.cc/"><img alt="Config: Hydra" src="https://img.shields.io/badge/Config-Hydra-89b8cd"></a>
<a href="https://github.com/ashleve/lightning-hydra-template"><img alt="Template" src="https://img.shields.io/badge/-Lightning--Hydra--Template-017F2F?style=flat&logo=github&labelColor=gray"></a><br>

</div>

## 📌&nbsp;&nbsp;Introduction
This thesis explores how one can alleviate the issues of big multilingual transformers for low-resource languages, especially the curse of multilinguality. Specifically, our two main objectives are: (1) Improving the cross-lingual alignment for low-resource languages and (2) improving cross-lingual downstream task performance for low-resource languages. We utilize Knowledge Distillation (KD) by distilling the multilingual model into language-specialized (also called monolingual) language models.

This Github repository carries the code used throughout the thesis. The code is split into three projects: (1) Cross-Lingual Knowledge Distillation, (2) Trident, and (3) Trident-Xtreme:

- **[Cross-Lingual Knowledge Distillation (clkd)](https://github.com/MinhDucBui/clkd):** This project contains all distillation done throughout the thesis. Furthermore, the project is set up to use any distillation loss easily, any number of students, and languages per student. The project also allows to change the teacher and student architecture and to choose between monolingual, bilingual, or multilingual distillation setup. Furthermore, we constructed config files for each distillation loss and each setup used in this thesis. Each hyperparameter can be adjusted by changing the respective config file.

- **[Trident (trident)](https://github.com/MinhDucBui/trident):** This project is a generic framework to train and evaluate (deep learning) models. We adjusted the implementation from the original [trident](https://github.com/fdschmidt93/trident) to accompany our needs of multiple students that interact with each other during training. \medskip

- **[Trident-Xtreme (trident-xtreme)](https://github.com/MinhDucBui/trident-xtreme).** Trident-Xtreme is a project implementing a modular deep learning stack to train and evaluate models with Trident. We adjust the implementation from the original [trident-xtreme](https://github.com/fdschmidt93/trident-xtreme) to allow us to train and evaluate our students on XNLI, XCOPA, NER, and the retrieval task. 


## 🚀&nbsp;&nbsp;Project Pipeline

The pipeline is constructed as follows:

1. Train general-purpose students with the [clkd repository](https://github.com/MinhDucBui/clkd).
2. Fine-tune and evaluate (either zero- or few-shot) with the [trident-xtreme repository](https://github.com/MinhDucBui/trident-xtreme).

Please find the documentation inside each respective repository. 

## ℹ️&nbsp;&nbsp;Project Structure
The directory structure of new project looks like this:
```

├── clkd                 <- clkd repository
│
├── trident              <- trident repository
│
└── trident-xtreme       <- trident-xtreme repository
```
<br>
