# gpt2-lora-qa
基于GPT2 + LoRA实现的轻量级问答系统微调项目
本项目基于 Huggingface Transformers 和 PEFT 框架，使用 GPT2 模型结合 LoRA（Low-Rank Adaptation）方法，完成了一个轻量级问答系统的微调流程。该项目支持自定义问答对训练、模型推理生成、训练参数调优，适合用于学习大模型下游任务微调的实践应用。

---

## 📁 项目结构

```
gpt2-lora-qa/
├── train.py                # 主训练脚本（加载模型+LoRA+训练）
├── infer.py                # 推理测试脚本（输入问题生成回答）
├── data/
│   └── qa_train_50.jsonl   # 训练数据：50条问答对
├── requirements.txt        # 所需依赖库
└── README.md               # 项目说明文档
```

---

## 🧠 技术栈

- Transformers（Huggingface）
- PEFT / LoRA 微调（参数高效微调）
- PyTorch
- Google Colab（可选）

---

## 🚀 使用方法

### 1️⃣ 安装依赖

```bash
pip install transformers datasets peft accelerate
```

### 2️⃣ 准备数据

训练数据位于 `data/qa_train_50.jsonl`，格式如下：

```json
{"text": "Q: What is AI?\nA: AI stands for Artificial Intelligence."}
```

你可以自行替换为更多问答数据。

### 3️⃣ 启动训练

```bash
python train.py
```

### 4️⃣ 推理测试

```bash
python infer.py
```

示例输出：

```
Q: Who developed GPT-2?
A: GPT-2 was developed by OpenAI.
```

---

## ⚙️ 训练参数推荐

```python
TrainingArguments(
    num_train_epochs=10,
    per_device_train_batch_size=2,
    learning_rate=5e-5,
    gradient_accumulation_steps=2,
)
```

---

## ✨ 项目亮点

- 使用 LoRA 技术实现轻量级微调，仅需较小显存即可训练
- 支持自定义训练数据，适用于特定领域问答微调
- 可作为大模型调优、实习面试、科研学习的完整 DEMO 项目

---

## 📌 后续可拓展

- 多轮问答支持
- RAG 检索增强生成（搭配向量数据库）
- 中文模型（Qwen/ChatGLM）替换
- Web 页面部署

---

## 📎 联系方式

作者：（kaneziki442）  
GitHub: https://github.com/kaneziki442
