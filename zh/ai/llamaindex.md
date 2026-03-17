---
sidebar_position: 13
---

# LlamaIndex

## 安装

### 1.1. 安装依赖

安装基本依赖：
```bash
sudo apt update
sudo apt install python3-venv python3-dev libffi-dev libssl-dev pkg-config libjpeg-dev zlib1g-dev libtiff-dev libfreetype6-dev liblcms2-dev libwebp-dev
```

安装rust：
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y --default-toolchain stable
source ~/.cargo/env
rustc --version
```

有如下打印说明安装成功：
![](../static/rust-install.png)

### 1.2. 安装langchain
 
```bash
python3 -m venv ./llamaindex_venv
source llamaindex_venv/bin/activate
pip install llama-index
```

## 使用

```bash
source llamaindex_venv/bin/activate
python -c "from llama_index.core import VectorStoreIndex, SimpleDirectoryReader; print('llama-index  导入成功！')"
```

![](../static/llamaindex-demo.png)