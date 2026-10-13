<div align="center">

# MedAD-R1

### Consistency-Reinforced Policy Optimization for Interpretable Medical Anomaly Detection

<p>
  <a href="https://arxiv.org/abs/2602.01081"><img src="https://img.shields.io/badge/arXiv-2602.01081-b31b1b?logo=arxiv&logoColor=white" alt="arXiv" /></a>
  <a href="https://github.com/zhtstar/MedAD-R1"><img src="https://img.shields.io/badge/GitHub-Code-181717?logo=github&logoColor=white" alt="GitHub" /></a>
  <a href="https://huggingface.co/datasets/zhtstar/MedAD-38K"><img src="https://img.shields.io/badge/Hugging%20Face-Dataset-FFD21E?logo=huggingface&logoColor=black" alt="Hugging Face dataset" /></a>
  <a href="https://modelscope.cn/datasets/zhtstar/MedAD-38K"><img src="https://img.shields.io/badge/ModelScope-Dataset-624AFF" alt="ModelScope dataset" /></a>
  <a href="https://huggingface.co/zhtstar/MedAD-R1"><img src="https://img.shields.io/badge/Hugging%20Face-Model-FFD21E?logo=huggingface&logoColor=black" alt="Hugging Face model" /></a>
  <a href="https://modelscope.cn/models/zhtstar/MedAD-R1"><img src="https://img.shields.io/badge/ModelScope-Model-624AFF" alt="ModelScope model" /></a>
</p>

</div>

> **Release status.** The model and dataset are currently available through access requests while the paper is under review. We plan to make the project resources openly available after acceptance, subject to the licenses and redistribution terms of the source datasets.

## Overview

Medical anomaly detection needs more than a correct prediction: an interpretable system should ground its reasoning in visible image evidence and keep that reasoning consistent with the final answer. **MedAD-R1** addresses this goal with a two-stage training framework built on **MedAD-38K**, a medical-image visual question answering benchmark with quality-controlled diagnostic reasoning annotations.

- **MedAD-38K** contains **38,422 medical images** and **130,146 VQA instances**.
- **Cognitive Injection** uses supervised fine-tuning to inject domain knowledge and establish a structured `<think>...</think><answer>...</answer>` response format.
- **Con-GRPO** reinforces answer correctness together with visually grounded, relevant, supportive, non-hallucinatory, and logically consistent reasoning.

<div align="center">
  <img src="https://raw.githubusercontent.com/zhtstar/MedAD-R1/main/framework.png" alt="MedAD-38K construction and the MedAD-R1 training framework" width="900" />
  <br />
  <em>Overview of the dataset construction and the two-stage MedAD-R1 framework.</em>
</div>

## Benchmark and results

<div align="center">
  <img src="https://raw.githubusercontent.com/zhtstar/MedAD-R1/main/dataset-tasks.png" alt="Examples of MedAD-38K medical VQA tasks" width="780" />
</div>

Results reported in the paper are shown below (%, higher is better):

| Model / training | Parameters | MedAD-38K accuracy | Reasoning-answer consistency | External accuracy |
| :-- | --: | --: | --: | --: |
| Qwen3.5, zero-shot | 0.8B | 76.43 | 92.12 | 68.12 |
| Qwen3.5, SFT only | 0.8B | 90.89 | 94.35 | 88.36 |
| Qwen3.6, fine-tuned on our training split | 27B | 92.75 | 92.10 | 84.27 |
| **MedAD-R1 (SFT + Con-GRPO)** | **0.8B** | **95.12** | **97.26** | **90.09** |

Please refer to the paper and supplementary material for the complete experimental setup, baseline comparisons, and evaluation protocol.

## Resources

| Resource | Hugging Face | ModelScope | Other |
| :-- | :-- | :-- | :-- |
| Paper | - | - | [arXiv:2602.01081](https://arxiv.org/abs/2602.01081) |
| Code | - | - | [GitHub: zhtstar/MedAD-R1](https://github.com/zhtstar/MedAD-R1) |
| Dataset: MedAD-38K | [Download / request access](https://huggingface.co/datasets/zhtstar/MedAD-38K) | [Download / request access](https://modelscope.cn/datasets/zhtstar/MedAD-38K) | - |
| Model: MedAD-R1 | [Download / request access](https://huggingface.co/zhtstar/MedAD-R1) | [Download / request access](https://modelscope.cn/models/zhtstar/MedAD-R1) | - |

## Citation

If you find this work useful, please cite:

```bibtex
@article{zhang2026medadr1,
  title   = {MedAD-R1: Consistency-Reinforced Policy Optimization for Interpretable Medical Anomaly Detection},
  author  = {Zhang, Haitao and Wang, Yingying and Wang, Jiaxiang and Xu, Haote and Zhang, Hongyang and Chen, Yirong and Huang, Yue and Ding, Xinghao},
  journal = {arXiv preprint arXiv:2602.01081},
  year    = {2026}
}
```
