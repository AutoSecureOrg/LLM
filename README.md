# **LLM WhiteRabbitNeo Llama-3 8B v2.0 Q4_K_M**

## **Complete LLM Setup on Raspberry Pi**

### Install system dependencies

```bash
sudo apt update && sudo apt install -y build-essential cmake git python3-pip
```

---

### Clone llama.cpp and build

```bash
git clone https://github.com/ggerganov/llama.cpp.git
cd llama.cpp
cmake -B build
cmake --build build --config Release
```

---

### Download `.gguf` model

```bash
mkdir -p models
cd models
wget wget https://huggingface.co/mradermacher/Llama-3-WhiteRabbitNeo-8B-v2.0-GGUF/resolve/main/Llama-3-WhiteRabbitNeo-8B-v2.0.Q4_K_M.gguf
cd ..
```

---

### Test via C++ CLI (sanity check)

```bash
./build/bin/llama-cli -m models/Llama-3-WhiteRabbitNeo-8B-v2.0.Q4_K_M.gguf -p "Explain AI in 1 line."
```

---

### Python bindings

```bash
pip install llama-cpp-python
```

---

### Run your Python socket server (ai_server.py)

```bash
python3 ai_server.py
```

This script:
- Uses `llama_cpp`
- Streams response tokens via socket
- Caches prompts/responses in SQLite
- Loads model from your custom path with `GPU_LAYERS`, `N_CTX`, etc

---
