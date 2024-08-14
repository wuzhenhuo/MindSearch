<div id="top"></div>

<div align="center">

<img src="assets/logo.svg" style="width: 50%; height: auto;">

[🌐 Project Page](https://mindsearch.netlify.app/) | [📃 Paper](https://arxiv.org/abs/2407.20183) | [💻 Playground](https://mindsearch.openxlab.org.cn/)

English | [简体中文](README_zh-CN.md)

<https://github.com/user-attachments/assets/44ffe4b9-be26-4b93-a77b-02fed16e33fe>

</div>
</p>

## ✨ MindSearch: Mimicking Human Minds Elicits Deep AI Searcher

MindSearch is an open-source AI Search Engine Framework designed to deliver performance on par with Perplexity.ai Pro. It supports both closed-source LLMs (e.g., GPT, Claude) and open-source models. For optimal results, we recommend using models from the InternLM2_5 series, such as [InternLM2_5-20b-chat](https://huggingface.co/internlm/internlm2_5-20b-chat) and [InternLM2_5-7b-chat](https://huggingface.co/internlm/internlm2_5-7b-chat), which are specifically optimized to provide superior performance within the MindSearch framework. It owns following features:

- 🤔 **Ask everything you want to know**: MindSearch is designed to solve any question in your life and use web knowledge.
- 📚 **In-depth Knowledge Discovery**: MindSearch browses hundreds of web pages to answer your question, providing deeper and wider knowledge base answer.
- 🔍 **Detailed Solution Path**: MindSearch exposes all details, allowing users to check everything they want. This greatly improves the credibility of its final response as well as usability.
- 💻 **Optimized UI Experience**: Providing all kinds of interfaces for users, including React, Gradio, Streamlit and Terminal. Choose any type based on your need.
- 🧠 **Dynamic Graph Construction Process**: MindSearch decomposes the user query into atomic sub-questions as nodes in the graph and progressively extends the graph based on the search result from WebSearcher.

<div align="center">

<img src="assets/teaser.gif">

</div>

## ⚡️ MindSearch vs other AI Search Engines

Comparison on human preference based on depth, breadth, factuality of the response generated by ChatGPT-Web, Perplexity.ai (Pro), and MindSearch. Results are obtained on 100 human-crafted real-world questions and evaluated by 5 human experts\*.

<div align="center">
<img src="assets/mindsearch_openset.png" width="90%">
</div>
* All experiments are done before July.7 2024.

## ⚽️ Build Your Own MindSearch

### Step1: Dependencies Installation

```bash
git clone https://github.com/InternLM/MindSearch
cd MindSearch
pip install -r requirements.txt
```

### Step2: Setup MindSearch API

Setup FastAPI Server.

```bash
python -m mindsearch.app --lang en --model_format internlm_server
```

- `--lang`: language of the model, `en` for English and `cn` for Chinese.
- `--model_format`: format of the model.
  - `internlm_server` for InternLM2.5-7b-chat with local server. (InternLM2.5-7b-chat has been better optimized for Chinese.)
  - `gpt4` for GPT4.
    if you want to use other models, please modify [models](./mindsearch/agent/models.py)

### Step3: Setup MindSearch Frontend

Providing following frontend interfaces,

- React

```bash
# Install Node.js and npm
# for Ubuntu
sudo apt install nodejs npm

# for windows
# download from https://nodejs.org/zh-cn/download/prebuilt-installer

# Install dependencies

cd frontend/React
npm install
npm start
```

Details can be found in [React](./frontend/React/README.md)

- Gradio

```bash
python frontend/mindsearch_gradio.py
```

- Streamlit

```bash
streamlit run frontend/mindsearch_streamlit.py
```

## 🐞 Debug Locally

```bash
python -m mindsearch.terminal
```

## 📝 License

This project is released under the [Apache 2.0 license](LICENSE).

## Citation

If you find this project useful in your research, please consider cite:

```
@article{chen2024mindsearch,
  title={MindSearch: Mimicking Human Minds Elicits Deep AI Searcher},
  author={Chen, Zehui and Liu, Kuikun and Wang, Qiuchen and Liu, Jiangning and Zhang, Wenwei and Chen, Kai and Zhao, Feng},
  journal={arXiv preprint arXiv:2407.20183},
  year={2024}
}
```

## Our Projects

Explore our additional research on large language models, focusing on LLM agents.

- [Lagent](https://github.com/InternLM/lagent): A lightweight framework for building LLM-based agents
- [AgentFLAN](https://github.com/InternLM/Agent-FLAN): An innovative approach for constructing and training with high-quality agent datasets (ACL 2024 Findings)
- [T-Eval](https://github.com/open-compass/T-Eval): A Fine-grained tool utilization evaluation benchmark (ACL 2024)
