# AB Verifier / AB Classifier — Qwen2.5-0.5B SFT Weights

AB Runtime 项目在云端（AutoDL RTX 4090 + LLaMA-Factory 全参 SFT）训练的两个
Qwen2.5-0.5B-Instruct 下游模型原始 HF 权重（fp32 safetensors），基座为
[Qwen2.5-0.5B-Instruct](https://huggingface.co/Qwen/Qwen2.5-0.5B-Instruct)（Apache-2.0）。

## 目录结构

| 目录 | 模型 | 用途 |
| --- | --- | --- |
| `verifier/` | qwen05-verifier-full | verifier 评审模型：对 executor 候选答案做 accept/reject 判定（训练/服务同构提示词，见 AB Runtime `VERIFIER_SYSTEM_PROMPT`） |
| `cls/` | qwen05-cls-full | 任务分类模型：任务类型分类（MVP-1 专项训练分类器） |

每个目录含完整可加载的模型卡内容：`model.safetensors`、`config.json`、tokenizer 全套、
`chat_template.jinja`、训练元数据（`train_results.json` / `trainer_state.json`、loss 曲线）。

## 使用

```python
from transformers import AutoModelForCausalLM, AutoTokenizer

tok = AutoTokenizer.from_pretrained("<此仓库>/verifier")
model = AutoModelForCausalLM.from_pretrained("<此仓库>/verifier")
```

## 许可

本仓库训练产出权重以 [MPL-2.0](./LICENSE) 发布；基座模型 Qwen2.5-0.5B-Instruct
遵循其原始 Apache-2.0 许可。
