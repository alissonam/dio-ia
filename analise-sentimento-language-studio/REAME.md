# 🚀 Análise de Sentimentos com Language Studio no Azure AI

Este módulo documenta o aprendizado e a prática utilizando as ferramentas **Azure Speech Studio** e **Language Studio** com foco em **análise de linguagem natural e de fala** como parte do desafio da **DIO (Digital Innovation One)**.

---

### 🔍 Análise de Texto (Text Analytics)

Permite identificar sentimentos, frases-chave, entidades nomeadas (como empresas, datas, locais) e linguagem ofensiva em um texto. É possível fazer isso usando a API de Text Analytics ou diretamente pelo Language Studio.

---

### 🤖 Serviço de Bot do Azure

Plataforma para criar, conectar e gerenciar bots inteligentes com suporte a linguagem natural. Utiliza ferramentas como o Azure Bot Framework e o Language Understanding (LUIS/CLU) para interpretar intenções e responder aos usuários.

---

### 💬 Compreensão de Linguagem Coloquial

Através do **Conversation Language Understanding (CLU)**, é possível treinar modelos para entender intenções e entidades em linguagem natural, mesmo com termos informais e coloquiais. Isso torna os bots e assistentes mais humanos e próximos do dia a dia dos usuários.

---

### 🗣️ Reconhecimento e Síntese de Fala

Com o **Azure Speech Service**, é possível:

- **Speech-to-Text**: Transforma áudio em texto;
- **Text-to-Speech**: Gera voz a partir de um texto;
- **Tradução de Fala**: Traduz áudios em tempo real;
- **Reconhecimento de Locutor**: Identifica quem está falando (útil para reuniões, call centers, etc.).

---

### 🎙️ Speech Studio - Criação de um Novo Recurso

Passo a passo:

1. Acesse: [https://speech.microsoft.com](https://speech.microsoft.com)
2. Escolha uma funcionalidade (ex: Speech-to-Text ou Custom Voice).
3. Clique em "Criar Recurso".
4. No portal Azure:
   - Tipo de recurso: **Speech**
   - Região: selecione a mais próxima
   - Plano: F0 (gratuito) ou pago
   - Grupo de recurso: novo ou existente
5. Após a criação, copie a **chave e o endpoint**.
6. Volte ao Speech Studio e associe o recurso criado.

---

### 🔄 Conversão de Fala em Texto

Com **Speech-to-Text**, é possível enviar arquivos de áudio (ou usar microfone em tempo real) e obter a transcrição.

Características:
- Pontuação automática;
- Divisão por frases;
- Detecção de idioma;
- Identificação de falantes (Speaker Diarization).

---

### 🤖 Microsoft Azure - Criação de Recurso AI + Machine Learning

1. Acesse o Portal Azure.
2. Clique em "Criar um recurso".
3. Selecione a categoria: **AI + Machine Learning**.
4. Escolha: **Language** (para texto) ou **Speech** (para voz).
5. Preencha os dados:
   - Nome do recurso
   - Grupo de recursos
   - Região
   - Plano (gratuito ou pago)
6. Após criado, use a chave e endpoint nos serviços correspondentes.

---

## 🧪 Language Studio - Sentiment and Opinion Mining Tryout

O **Language Studio** permite testar os serviços de linguagem da Microsoft de forma interativa, como:
- Análise de sentimentos;
- Extração de opiniões específicas;
- Identificação de entidades e frases-chave.

---

### 📌 Exemplo Prático:

**Texto de entrada:**

> "O atendimento ao cliente foi excelente, mas a entrega demorou muito e o produto chegou danificado."

---

### 💬 Retorno da API (JSON simplificado):

```json
{
  "sentiment": "mixed",
  "confidenceScores": {
    "positive": 0.45,
    "neutral": 0.05,
    "negative": 0.50
  },
  "sentences": [
    {
      "text": "O atendimento ao cliente foi excelente.",
      "sentiment": "positive",
      "opinions": [
        {
          "target": "atendimento ao cliente",
          "sentiment": "positive",
          "assessment": "excelente"
        }
      ]
    },
    {
      "text": "Mas a entrega demorou muito e o produto chegou danificado.",
      "sentiment": "negative",
      "opinions": [
        {
          "target": "entrega",
          "sentiment": "negative",
          "assessment": "demorou muito"
        },
        {
          "target": "produto",
          "sentiment": "negative",
          "assessment": "chegou danificado"
        }
      ]
    }
  ]
}
```

### 📝 Interpretação Rápida:
    Sentimento Geral: Misto (45% positivo / 50% negativo).

    Opiniões específicas:
        - Atendimento ao cliente → positivo (excelente);
        - Entrega → negativo (demorou muito);
        - Produto → negativo (chegou danificado).
