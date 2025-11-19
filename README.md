# 法律智能问答系统

基于 RAG 和 Agent 技术的法律知识与案例分析系统集合。

## 项目结构

### 1. RAG4Law
基础法律知识问答系统，使用 **Contextual Retrieval** 技术进行检索增强。

**核心特性**：
- 上下文增强的文档分块
- 混合检索（BM25 + 语义向量）
- 支持多种 LLM 提供商

**主要用途**：法律条文查询、知识检索

📖 [详细文档](./RAG4Law/README.md)

---

### 2. AgenticRAG4Law  
使用 **Agent + ReAct 模式**优化的法律问答系统。

**核心特性**：
- ReAct 推理与工具调用
- 多轮迭代检索与自我优化
- Agentic 与 Non-Agentic 模式对比
- 评估框架

**主要用途**：复杂法律问题推理、多步骤信息检索

📖 [详细文档](./AgenticRAG4Law/README.md)

---

### 3. LegalAgent
基于 **CAIL 2018** 数据集的案例分析系统（方案阶段）。

**设计目标**：
- 结构化知识提取与存储
- 案例聚类与量刑因素分析
- 智能对话式案例问答
- 量刑预测参考

**技术方案**：AgenticRAG + 外部化学习 + 案例聚类

📖 [详细方案](./LegalAgent/项目方案.md)

---

## 技术栈

- **LLM**: OpenAI, Kimi, Doubao, SiliconFlow 等
- **向量数据库**: Elasticsearch / PostgreSQL+pgvector
- **机器学习**: scikit-learn, HDBSCAN
- **框架**: LangChain, FastAPI

## 快速开始

### 环境准备
```bash
# 1. 创建 conda 环境
conda create -n legal-agent python=3.10
conda activate legal-agent

# 2. 安装依赖（选择需要的项目）
cd RAG4Law  # 或 AgenticRAG4Law
pip install -r requirements.txt

# 3. 配置 API Keys
cp env.example .env
# 编辑 .env 添加 API 密钥
```

### 运行示例
```bash
# RAG4Law
cd RAG4Law
python index_local_laws_contextual.py  # 索引法律文档
python main.py  # 启动问答

# AgenticRAG4Law
cd AgenticRAG4Law
python index_local_laws.py  # 索引法律文档
python main.py --mode agentic  # Agentic 模式
python main.py --mode compare  # 对比两种模式
```

## 项目状态

| 项目 | 状态 | 说明 |
|------|------|------|
| RAG4Law | ✅ 已实现 | Contextual Retrieval 完整实现 |
| AgenticRAG4Law | ✅ 已实现 | ReAct Agent 完整实现 |
| LegalAgent | 📋 设计阶段 | 有完整技术方案，未实现代码 |

## License

Educational project for learning purposes.

