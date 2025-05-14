# ACMR – IA de Consulta de Medicamentos da RENAME

Trabalho de Conclusão de Curso – MBA USP/ESALQ (Data Science & Analytics)  •  Domínio: Saúde Pública / Medicamentos Essenciais  •  Última atualização: maio 2025

## Visão Geral

ACMR é um protótipo de Generation‑Augmented Retrieval (RAG) que responde perguntas sobre os 534 medicamentos presentes na Relação Nacional de Medicamentos Essenciais (RENAME) do SUS, combinando LLMs de código aberto com busca vetorial para oferecer respostas rápidas, contextualizadas e transparentes. O pipeline captura o PDF oficial da RENAME, extrai, limpa e fragmenta o texto, gera vetores semânticos e disponibiliza consulta via chat construído em Streamlit.

![image](https://github.com/user-attachments/assets/b0428587-0cb8-4d39-afe7-7b830db93e8e)

**Figura: Fluxograma de representação do sistema RAG de medicamentos RENAME.**

## Objetivos

1. Investigar a eficácia de arquiteturas RAG na recuperação de informações médicas não estruturadas.

2. Facilitar o acesso de pacientes, estudantes e profissionais a dados críticos de medicamentos, reduzindo barreiras do documento PDF extenso e semiestruturado.

3. Avaliar o sistema com o framework RAGAS, usando as métricas context_precision, context_recall, faithfulness e answer_relevancy.

## Tecnologias Principais

| Camadas       | Ferramentas                       |
| --------------- | --------------------------------- |
| Modelos de Linguagem            | Mixtral‑8x7B · Gemma‑2‑9B · Llama 3 |
| Embeddings      | all-MiniLM-L6-v2                  |
| Banco Vetorial      | LangChain, RAGAS                  |
| Frameworks         | Pinecone                          |
| API de Inferência   | Groq Cloud APIs                  |
| Interface       | Streamlit                         |
| Armazenamento   | PostgreSQL                        |
| Ambiente de Dev | Python 3.10 · VS Code · Jupyter/Colab   |

## Pipeline de Cinco Etapas

1. **Formação do dataset:** obtenção e organização do PDF RENAME.

2. **Limpeza & padronização:** revisão de textos e normalização de bulas e lista.

3. **Vetorização & armazenamento:** criação de ~16 k chunks e indexação com métrica de cosseno no Pinecone.

4. **Recuperação & geração:** montagem do fluxo LangChain que reformula perguntas (Gemma‑2‑9B), recupera contexto e gera respostas (Mixtral‑8x7B).

5. **Avaliação:** aplicação do RAGAS sobre conjunto sintético de perguntas/respostas.

## Resultados de Avaliação

| Métrica       | Pontuação Média                       |
| --------------- | --------------------------------- |
| Precisão do Contexto | 0,93 |
| Recall do Contexto | 0,87 |
| Fidelidade | 0,83 |
| Relevância da Resposta | 0,63 |

As métricas indicam alta precisão e recall de contexto, sugerindo boa capacidade de localizar trechos relevantes. A fidelidade mantém consistência factual; já a relevância das respostas revela espaço para refinamentos no modelo gerador.

![image](https://github.com/user-attachments/assets/8e9bfb82-f504-4403-9af0-7642a90f4b86)

**Figura: Avaliação das métricas para várias perguntas geradas no sistema.**

## Como Executar Localmente

### 1. Clone o repositório
```
$ git clone git@github.com:nathadriele/acmr-rag-rename-mbausp.git
```

### 2. Crie o ambiente
```
$ python -m venv .venv && source .venv/bin/activate
```

```
$ pip install -r requirements.txt
```

### 3. Configure suas credenciais
```
$ export PINECONE_API_KEY=SEU_TOKEN
```

```
$ export GROQ_API_KEY=SEU_TOKEN
```

### 4. Execute a interface

![image](https://github.com/user-attachments/assets/931db66c-19f5-49d0-a72e-07843d4b7683)

**Figura: Interface de usuário do sistema de consulta de medicamentos RENAME.**

--------------------------------------------------------

![image](https://github.com/user-attachments/assets/9b03e901-850b-4850-841f-970670767a4c)

**Figura: Interface do usuário com pergunta, reformulação da pergunta e resposta.**

```
$ streamlit run src/app_streamlit.py
```

Obs: a primeira execução fará a vetorização e pode levar alguns minutos.

## Autoria & Orientação

Me. Nathalia Adriele de Lima – MBA em Data Science & Analytics, USP/ESALQ

Dr. Felipe Pinto da Silva – Orientador

**Caso utilize este trabalho em pesquisas acadêmicas, cite da seguinte forma:**

```
@misc{lima2024rag,
  title  = {RAG: Avaliação de um sistema de recuperação da informação de medicamentos RENAME baseado em LLMs},
  author = {Lima, Nathalia Adriele de and Silva, Felipe Pinto da},
  year   = {2024},
  note   = {MBA USP/ESALQ, Trabalho de Conclusão de Curso}
}
```
