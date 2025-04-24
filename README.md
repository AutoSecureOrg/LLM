# LLM

### Install dependencies

```bash
sudo apt update && sudo apt install -y build-essential cmake git python3-pip
```

---

### Clone llama.cpp

```bash
git clone https://github.com/ggerganov/llama.cpp.git
cd llama.cpp
```

---

### Build it

```bash
cmake -B build
cmake --build build --config Release
```

---

### Download model

```bash
mkdir -p models
cd models
wget https://huggingface.co/TheBloke/Llama-3-8B-GGUF/resolve/main/Llama-3-WhiteRabbitNeo-8B-v2.0.Q4_K_M.gguf
cd ..
```

### Run a test

```bash
./build/bin/llama-cli -m models/Llama-3-WhiteRabbitNeo-8B-v2.0.Q4_K_M.gguf -p "Explain AI in 1 line."
```

---
