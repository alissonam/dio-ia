# 🚀 Azure Cognitive Search: Pesquisa Inteligente de Atendimentos

Este projeto foi desenvolvido como parte do desafio **"Azure Cognitive Search: Utilizando AI Search para indexação e consulta de Dados"** oferecido pela **DIO (Digital Innovation One)**. O objetivo é aplicar conceitos de mineração de conhecimento, enriquecimento com IA e indexação inteligente de documentos utilizando os serviços do Microsoft Azure.

---

## 🧠 O que é Mineração de Conhecimento?

Mineração de conhecimento é o processo de identificar informações úteis a partir de grandes volumes de dados, geralmente não estruturados, como textos e imagens. Neste projeto, aplicamos IA para extrair, transformar e organizar esses dados, transformando-os em insights acionáveis.

---

## 🔍 Soluções de Pesquisa Cognitiva com Azure

Utilizamos o serviço **Azure Cognitive Search**, que permite criar mecanismos de busca inteligentes com recursos integrados de IA. Com ele, é possível:

- Criar **índices** para pesquisa inteligente;
- Conectar fontes de dados (Blob Storage, SQL, etc);
- Aplicar IA com **skillsets** para enriquecer os dados;
- Consultar os dados com filtros e linguagem natural.

---

## 💡 Enriquecimento de IA (AI Enrichment)

Durante a criação dos índices, aplicamos um conjunto de habilidades (skillset) de IA que permite:

- OCR para extração de texto de PDFs e imagens;
- Detecção de idioma e tradução;
- Extração de entidades (nomes, locais, datas, etc.);
- Análise de sentimentos (positivo, neutro, negativo);
- Identificação de frases-chave.

---

## 📦 Cenário Prático: Atendimento da Rede de Cafeterias

### 📝 Descrição

Uma rede fictícia de cafeterias com lojas em todos os estados do Brasil deseja entender os principais problemas relatados por clientes em seus canais de atendimento.

---

## 🛠️ Recursos Azure Utilizados

| Serviço                     | Finalidade                                                    |
| --------------------------- | ------------------------------------------------------------- |
| Azure Blob Storage          | Armazenamento de PDFs, imagens, textos e JSONs de atendimento |
| Azure Cognitive Search      | Indexação, enriquecimento com IA e consultas inteligentes     |
| Azure Form Recognizer / OCR | Extração automática de texto de documentos                    |
| Azure Text Analytics        | Análise de sentimento e entidades                             |
| Azure Logic Apps (opcional) | Automatização da ingestão de dados                            |

---

## 🚀 Etapas Realizadas

### 1. Ingestão dos Dados

- Upload dos dados de atendimento no **Azure Blob Storage**;
- Ex: PDFs com formulários, arquivos JSON com comentários, imagens escaneadas.

### 2. Criação do Data Source

- Fonte configurada no Azure Cognitive Search apontando para o blob.

### 3. Configuração do Skillset (Enriquecimento)

Habilidades aplicadas:

- Extração de texto (OCR);
- Análise de sentimentos;
- Extração de entidades;
- Frases-chave;
- Detecção e tradução de idiomas.

### 4. Criação do Índice

Campos definidos:

- `id_loja`, `estado`, `comentario`, `data`, `sentimento`, `tipo_reclamacao`, `entidades`, `resposta`.

### 5. Indexador

- Criação de um indexador que conecta data source + skillset ao índice final;
- Indexação automática realizada com enriquecimento de dados.

### 6. Consulta aos Dados

Exemplos:

- “Mostrar atendimentos negativos no estado do Rio de Janeiro”;
- “Listar principais problemas relatados nas lojas do Nordeste”;
- “Filtrar comentários com sentimento positivo em março”.

---
