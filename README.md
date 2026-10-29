# 💬 Assistente Virtual de Produtividade no Telegram (n8n, Groq & Redis)

Este projeto consiste num fluxo de automação e orquestração de Inteligência Artificial construído no **n8n**, integrado diretamente à API do **Telegram**. A solução utiliza a infraestrutura da **Groq** para inferência ultrarrápida de modelos de linguagem (LLM) e o **Redis** para a gestão persistente do histórico de conversas.

## 🎯 Problema de Negócio e Proposta de Valor
Muitas aplicações de IA falham na adoção por exigirem interfaces complexas ou novos logins. Este projeto resolve esse problema de usabilidade ao levar um agente inteligente para onde o utilizador já está: o **Telegram**. 
O fluxo atua como um assistente de produtividade pessoal ("Lumina"), capaz de apoiar em tarefas do dia a dia, sumarização de informações, rascunhos de comunicação e organização de rotinas em tempo real.

## 🛠️ Arquitetura e Tecnologias
*   **n8n:** Plataforma de orquestração visual e integração de fluxos.
*   **Telegram API & Trigger:** Recebe e responde mensagens instantaneamente via webhooks.
*   **Groq API (LLM):** Utilizada para inferência de baixíssima latência em modelos abertos de alta capacidade.
*   **Redis Chat Memory:** Armazena o contexto da conversa por `chat_id`, permitindo conversas contínuas e personalizadas.
*   **Date & Time Tool:** Ferramenta acoplada ao agente para consulta contextualizada de datas e horários em tempo real.

## 🧠 Engenharia de Prompt e Persona
A persona **Lumina** foi desenhada através de regras rigorosas de *System Prompt* para garantir respostas objetivas, amigáveis e adaptadas à interface do telemóvel:

> *"Você é uma assistente virtual inteligente, amigável e extremamente prática... Use marcadores de texto suportados pelo Telegram para tornar a leitura fluida, mantenha as respostas curtas para não poluir a tela e dê a resposta principal logo nas primeiras linhas."*

## 🔄 Fluxo de Execução
1. **Entrada (Telegram Trigger):** O utilizador envia uma mensagem ou o comando `/start`.
2. **Contextualização (Redis):** O sistema recupera a janela de histórico associada ao ID do chat.
3. **Processamento (AI Agent & Groq):** O modelo processa a solicitação, podendo acionar a ferramenta de data/hora quando necessário.
4. **Envio (Telegram Node):** A resposta formatada em Markdown é enviada de volta ao ecrã do utilizador.

## 🚀 Como importar e testar
1. Faça o download do ficheiro `Integração com Telegram.json` presente neste repositório.
2. Na sua instância do n8n, selecione **Import from File**.
3. Associe as suas credenciais para os nós: **Telegram API**, **Groq API** e **Redis**.
4. Ative o fluxo e inicie a conversa com o seu bot no Telegram.
