# Local LLM Chat Demo

Run Microsoft's Phi-3-mini language model locally on your CPU with an interactive chat interface!

## Features

- **Fast CPU Performance**: Uses GGUF Q4_K_M quantization for 2-3x faster inference
- **Lightweight**: Only ~2.4GB model size
- **Interactive Chat**: Beautiful Jupyter notebook interface with conversation history
- **No GPU Required**: Optimized for CPU-only environments
- **GitHub Codespaces Ready**: One-click deployment with full environment setup

## Quick Start

### Option 1: GitHub Codespaces (Easiest)

1. Click the "Code" button above and select "Create codespace on main"
2. Wait for the environment to set up (2-3 minutes)
3. Open `chat_demo_phi3.ipynb` in the file explorer
4. Run all cells and start chatting!

### Option 2: Local Installation

#### Prerequisites
- Python 3.11 or higher
- 4GB+ RAM available
- ~3GB disk space for model storage

#### Setup

1. Clone the repository:
```bash
git clone https://github.com/SDWIS-Applications/llm-chat-demo.git
cd llm-chat-demo
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Launch Jupyter and open the notebook:
```bash
jupyter notebook chat_demo_phi3.ipynb
```

4. Run all cells - the model will download automatically on first run

## Using the Chat Interface

1. **Run all cells** in the notebook to load the model
2. **Type your message** in the text box at the bottom
3. **Press Send** or hit Enter to get a response
4. **Adjust settings**:
   - Temperature: Controls creativity (0.1 = focused, 1.0 = creative)
   - Max Tokens: Maximum response length

## Performance Tips

- First model download takes 2-3 minutes
- First response may be slower as model loads into memory
- Subsequent responses are much faster (~5-10 tokens/second on modern CPUs)
- The model uses all available CPU cores automatically

## Model Details

- **Model**: Microsoft Phi-3-mini-4k-instruct
- **Quantization**: Q4_K_M (4-bit quantization)
- **Size**: ~2.4GB
- **Context**: 4096 tokens
- **License**: MIT

## Troubleshooting

**Slow responses?**
- Ensure no other heavy processes are running
- Check that the notebook is using all CPU threads (shown in output)

**Installation issues?**
- Make sure you have Python 3.11+
- On Linux/Mac, you may need to install build tools: `sudo apt-get install build-essential` (Ubuntu) or `xcode-select --install` (Mac)

**Out of memory?**
- Close other applications
- The model needs about 3-4GB of RAM

## Project Structure

```
llm-chat-demo/
├── chat_demo_phi3.ipynb  # Main notebook with chat interface
├── requirements.txt      # Python dependencies
├── pyproject.toml        # Project configuration (for uv package manager)
├── .devcontainer/        # GitHub Codespaces configuration
└── README.md            # This file
```

## Contributing

Feel free to open issues or submit pull requests! Some ideas:
- Add support for other GGUF models
- Implement conversation export/import
- Add system prompt customization
- Create a Gradio or Streamlit interface

## License

MIT - Feel free to use this for any purpose!

## Acknowledgments

- Microsoft for the excellent Phi-3 model
- llama-cpp-python community for GGUF support
- Hugging Face for model hosting