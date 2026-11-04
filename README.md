# 🏭 IA Industrial focado para Embrapii

<p align="center">
  <b>Eng. Laís Araújo Mangueira</b><br/>
  <i>Engenheira Eletricista</i>
</p>

🏛️ **Contexto:** Minicurso Embrapii — Imersão em IA Industrial

## 📌 Visão geral

Minicurso prático que constrói, passo a passo, um painel de **manutenção
preditiva (PdM)** para uma fresadora industrial, usando os dados sintéticos
públicos **AI4I 2020** (UCI Machine Learning Repository) e conectando-os a uma
LLM (Groq) por meio de RAG e engenharia de prompt. O resultado final é um
sistema de monitoramento emulado, no estilo supervisório (SCADA), com um
console onde o operador conversa com a LLM sobre o estado da máquina.

## 🎯 Objetivos

### Objetivo geral

Capacitar os participantes a construir, de ponta a ponta, um assistente de
IA que integra modelos de linguagem (LLMs) a um sistema de manutenção
preditiva industrial real.

### Objetivos específicos

- Compreender os fundamentos de uma LLM e como consumi-la via API (Groq).
- Dar contexto técnico fixo à LLM (ficha técnica da máquina) como primeiro
  passo de engenharia de prompt.
- Aplicar RAG (Retrieval-Augmented Generation) para responder perguntas de
  teoria com base na documentação técnica da planta (PDFs), citando a fonte.
- Treinar e combinar modelos de IA (Random Forest, Isolation Forest) para
  detecção, classificação e explicabilidade (SHAP) de falhas.
- Implementar um sistema industrial emulado com ingestão de dados em tempo
  real e otimização automática do limiar de alarme.
- Publicar uma interface interativa (Gradio) para operar o assistente.

## 🧑‍💻 Público-alvo e pré-requisitos

### Público-alvo

Estudantes, professores, pesquisadores e profissionais de Engenharia,
Computação ou áreas afins com interesse em IA aplicada à manutenção
preditiva e a sistemas industriais.

### Pré-requisitos

- Conhecimento básico de **Python**.
- Uma chave de API da [Groq](https://console.groq.com/keys) (gratuita).
- Conta Google para rodar o notebook no Colab (não é necessário instalar
  nada localmente).

## 🗂️ Plano de aula

1. **Bloco 1 — LLM & Visão Geral**
   - Primeiro contato com o modelo de linguagem (Exemplo A)
   - Engenharia de prompt: ficha técnica da fresadora como contexto fixo
     (Exemplo B)
2. **Bloco 2 — RAG**
   - Leitura, chunking e indexação (FAISS) dos PDFs técnicos da planta
   - Consulta aos trechos relevantes e resposta citando a fonte
3. **Bloco 3 — Engenharia de Prompt & Sistema Emulado**
   - A planta: dataset sintético AI4I 2020 (UCI) no lugar da máquina real
   - Detecção (Isolation Forest), classificação (Random Forest) e
     explicabilidade (SHAP)
   - Otimização automática do limiar de alarme
   - Construção dos prompts de instrução e comparação de técnicas
   - Aplicação final: painel supervisório interativo (Gradio)

## ▶️ Como rodar (Google Colab)

### Opção 1 — link direto (mais rápido)

Clique para abrir o script direto no Colab:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/laismngueira/minicurso-embrapii/blob/main/versao_pdm/embrapii_06_nov_revisado.py)

### Opção 2 — clonando o repositório

```bash
git clone https://github.com/laismngueira/minicurso-embrapii.git
```

Depois, no Colab, vá em **Arquivo > Abrir notebook > GitHub**, cole a URL do
repositório e selecione `versao_pdm/embrapii_06_nov_revisado.py` (o repo é
público, então o clone não pede usuário nem senha).

### Rodando o script

1. Configure o segredo `GROQ_API_KEY` (ícone de chave 🔑 na barra lateral
   esquerda do Colab) — crie uma chave gratuita em
   [console.groq.com](https://console.groq.com/keys). É o único segredo
   necessário.
2. Rode as células em ordem, de cima para baixo. O Bloco 2 baixa sozinho os
   PDFs da planta direto deste repositório, e o Bloco 3 baixa o dataset
   AI4I 2020 direto da UCI (com espelho no GitHub como reserva) — nenhuma
   configuração extra é necessária.
3. Ao final do Bloco 3, o painel de monitoramento abre com um link público
   temporário, gerado automaticamente pelo Gradio.

## 📁 Arquivos de apoio necessários

Todos disponíveis em [`versao_pdm/`](versao_pdm/):

| Arquivo | Descrição |
|---|---|
| `01_planta_fresadora_FR01.pdf` | Cenário, variantes de produto, tags do painel e arquitetura de dados — base de conhecimento do RAG |
| `02_modos_de_falha_FR01.pdf` | Regras, exemplos numéricos e consistência dos rótulos de cada modo de falha — base de conhecimento do RAG |
| `03_sistema_monitoramento_PdM01.pdf` | Modelos, níveis de alarme, desempenho e procedimentos de manutenção — base de conhecimento do RAG |

O dataset **AI4I 2020 Predictive Maintenance** (10.000 ciclos, UCI Machine
Learning Repository) é baixado automaticamente pelo script — não precisa ser
enviado manualmente.

## 📂 Estrutura do repositório

```plaintext
📦 minicurso-embrapii
├── 📂 versao_pdm
│   ├── embrapii_06_nov_revisado.py     # script do minicurso (exportado do Colab)
│   ├── 01_planta_fresadora_FR01.pdf    # base de conhecimento do RAG
│   ├── 02_modos_de_falha_FR01.pdf      # base de conhecimento do RAG
│   └── 03_sistema_monitoramento_PdM01.pdf  # base de conhecimento do RAG
├── 📜 .gitignore
└── 📜 README.md
```

## 🎞️ Slides

Apresentação completa do minicurso: [baixar PDF](https://github.com/laismngueira/minicurso-embrapii/releases/download/slides-embrapii/Embrapii.aula.0611.pdf).
