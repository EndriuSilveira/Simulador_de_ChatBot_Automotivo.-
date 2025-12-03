\# 🚗 Simulador de ChatBot Automotivo com RAG e Azure OpenAI



Este projeto consiste em um assistente virtual inteligente desenvolvido para a \*\*iAutos\*\*, um marketplace fictício de veículos. O sistema utiliza \*\*GenAI (Generative AI)\*\* para responder dúvidas sobre políticas de uso e \*\*Lógica de Roteamento\*\* para tratar regras de negócio específicas.



\## 🧠 Sobre o Projeto



O objetivo foi criar um ChatBot híbrido que não apenas consulta documentos (RAG), mas também entende o contexto para aplicar regras de negócio restritivas.



\### Principais Funcionalidades:

\* \*\*RAG (Retrieval-Augmented Generation):\*\* O bot consome um PDF de "Políticas e Uso", vetoriza o conteúdo e responde perguntas complexas sobre fraudes, regras de fotos e veículos permitidos.

\* \*\*Roteamento Inteligente (Router):\*\* Implementação de uma camada lógica que intercepta perguntas sobre "Preços" (ex: "Quanto custa um Gol?"). O bot identifica que não deve usar a IA para inventar preços, retornando uma resposta padrão de regra de negócio.

\* \*\*Memória Conversacional:\*\* O sistema mantém o contexto da conversa, permitindo perguntas de seguimento.



\## 🛠️ Tecnologias Utilizadas



\* \*\*Linguagem:\*\* Python

\* \*\*Orquestração de LLM:\*\* LangChain

\* \*\*Modelos de IA:\*\* Azure OpenAI (GPT-3.5/4 para Chat e Ada-002 para Embeddings)

\* \*\*Banco Vetorial:\*\* ChromaDB (Persistência de vetores)

\* \*\*Interface:\*\* Gradio (para testes interativos)

\* \*\*Processamento de Documentos:\*\* PyPDFLoader, RecursiveCharacterTextSplitter



\## ⚙️ Como Funciona a Pipeline



1\.  \*\*Ingestão:\*\* Download e leitura do PDF de regras da iAutos.

2\.  \*\*Chunking:\*\* Divisão do texto em fragmentos menores (chunks) para otimizar a busca.

3\.  \*\*Embedding:\*\* Conversão dos textos em vetores numéricos usando Azure OpenAI.

4\.  \*\*Armazenamento:\*\* Indexação dos vetores no ChromaDB.

5\.  \*\*Inferência:\*\*

&nbsp;   \* O usuário faz uma pergunta.

&nbsp;   \* O \*\*Roteador\*\* verifica se é uma pergunta de regra fixa (ex: Preço).

&nbsp;   \* Se não for, aciona a \*\*Chain RAG\*\*, busca os trechos relevantes no ChromaDB e gera a resposta via GPT.



\## 🚀 Como Executar



\### Pré-requisitos

\* Python 3.9+

\* Conta no Azure OpenAI (Endpoint e API Key)



\### Instalação

```bash

pip install langchain langchain-openai langchain-community chromadb pypdf gradio

---
Projeto desenvolvido por **Endriu Silveira De Sousa** como parte de portfólio em Engenharia de Dados e GenAI.
