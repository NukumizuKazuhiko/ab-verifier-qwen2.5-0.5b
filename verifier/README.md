---
library_name: transformers
license: other
base_model: /root/autodl-tmp/models/Qwen2.5-0.5B-Instruct
tags:
- llama-factory
- full
- generated_from_trainer
model-index:
- name: qwen05-verifier-full
  results: []
---

<!-- This model card has been generated automatically according to the information the Trainer had access to. You
should probably proofread and complete it, then remove this comment. -->

# qwen05-verifier-full

This model is a fine-tuned version of [/root/autodl-tmp/models/Qwen2.5-0.5B-Instruct](https://huggingface.co//root/autodl-tmp/models/Qwen2.5-0.5B-Instruct) on the ab_ver_train dataset.
It achieves the following results on the evaluation set:
- Loss: 0.0494

## Model description

More information needed

## Intended uses & limitations

More information needed

## Training and evaluation data

More information needed

## Training procedure

### Training hyperparameters

The following hyperparameters were used during training:
- learning_rate: 1e-05
- train_batch_size: 8
- eval_batch_size: 8
- seed: 42
- gradient_accumulation_steps: 2
- total_train_batch_size: 16
- optimizer: Use OptimizerNames.ADAMW_TORCH with betas=(0.9,0.999) and epsilon=1e-08 and optimizer_args=No additional optimizer arguments
- lr_scheduler_type: cosine
- lr_scheduler_warmup_steps: 0.05
- num_epochs: 3

### Training results

| Training Loss | Epoch | Step | Validation Loss |
|:-------------:|:-----:|:----:|:---------------:|
| 0.0805        | 0.5   | 20   | 0.1079          |
| 0.0768        | 1.0   | 40   | 0.0790          |
| 0.0364        | 1.5   | 60   | 0.0679          |
| 0.0303        | 2.0   | 80   | 0.0559          |
| 0.0176        | 2.5   | 100  | 0.0513          |
| 0.0247        | 3.0   | 120  | 0.0494          |


### Framework versions

- Transformers 5.8.0
- Pytorch 2.5.1+cu124
- Datasets 4.0.0
- Tokenizers 0.22.2
