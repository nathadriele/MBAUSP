# Repositório criado para armazenar os códigos do Trabalho de Conclusão de Curso do MBA de Data Science e Analytics da USP & ESALQ

![image](https://github.com/user-attachments/assets/e1dd42db-e2b6-4910-a3b2-7e545fb949e5)

## ACMR: AI de Consulta de Medicamentos da RENAME

Me. Nathalia Adriele de Lima

Orientador.: Dr. Felipe Pinto da Silva

[RAG Avaliacao de um sistema de recuperacao da informação de medicamentos.pdf](https://github.com/user-attachments/files/20104570/RAG.Avaliacao.de.um.sistema.de.recuperacao.da.informacao.de.medicamentos.pdf)

![image](https://github.com/user-attachments/assets/8ec12d96-d1ef-4a06-ab96-1d0644b9ee2a)


### Resumo

Este projeto de TCC apresenta o desenvolvimento do sistema ACMR – AI de Consulta de Medicamentos RENAME, um protótipo baseado em LLMs e Retrieval-Augmented Generation (RAG) para responder dúvidas sobre medicamentos da lista RENAME, usada pelo SUS. A base de dados foi processada, vetorizada e conectada a uma arquitetura com LangChain, Pinecone e Groq APIs, possibilitando buscas semânticas com contextualização e precisão. A avaliação do sistema foi feita por meio do framework RAGAS, utilizando métricas como fidelidade, relevância da resposta, recall de contexto e precisão de contexto.

### Abstract

This final project presents the development of ACMR – AI for RENAME Medication Queries, a prototype based on LLMs and Retrieval-Augmented Generation (RAG) for answering questions about medications listed in Brazil’s essential medicine list (RENAME). The dataset was structured and vectorized, and the system was built using LangChain, Pinecone, and Groq APIs to enable semantic, contextualized queries. Evaluation was conducted using the RAGAS framework, focusing on faithfulness, answer relevance, context recall, and context precision.

### Objetivo

Investigar e validar a eficácia de sistemas RAG no domínio da saúde pública, promovendo acesso rápido e contextualizado a informações críticas sobre medicamentos essenciais. A aplicação visa mitigar falhas comuns de acesso em documentos extensos e semiestruturados (ex: PDF da RENAME).

### Tecnologias Utilizadas

| Categoria       | Ferramentas                       |
| --------------- | --------------------------------- |
| LLMs            | Mixtral-8x7B, Gemma-2-9B, LLaMA 3 |
| Embeddings      | all-MiniLM-L6-v2                  |
| Frameworks      | LangChain, RAGAS                  |
| Vetores         | Pinecone                          |
| API de LLM      | Groq                              |
| Interface       | Streamlit                         |
| Armazenamento   | PostgreSQL                        |
| Desenvolvimento | Python, Jupyter, VSCode, Colab    |

### Metodologia (Resumo das Etapas)

1. Aquisição e estruturação da base RENAME
2. Limpeza, chunking e vetorização dos textos
3. Criação do índice vetorial e integração via Pinecone
4. Desenvolvimento do sistema ACMR em Python/Streamlit
5. Integração com LLMs e APIs de inferência
6. Avaliação com framework RAGAS usando métricas padronizadas

### Resultados

O sistema obteve altos níveis de precisão e recall de contexto (acima de 85%), fidelidade factual consistente e relevância aceitável das respostas. A abordagem se mostrou promissora para sistemas de consulta médica sensível baseada em IA generativa, destacando a importância de curadoria humana e refinamento contínuo.

![image](https://github.com/user-attachments/assets/6dc476ff-8be9-442c-94e4-05e596374197)


