# Natural ou Fake Natty? Como Vencer na Era das IAs Generativas

## 🚀 Introdução

> Woooow! Look at this 👀

Olá pessoal, Mariana aqui! Inspirado na hype _"Natty or Not"_ do fisiculturismo, este Lab da DIO te convida a conhecer o mundo das IAs Generativas, explorando o potencial dessas tendências tecnológicas incríveis!

## 🎯 Bora Pro Desafio!? Você Já Venceu 💪🤓

### Objetivos

1. **Explorar IAs Generativas**: Utilize essas tecnologias para criar conteúdos que sejam o mais realista possível. Seja criativo! Você pode produzir imagens, textos, áudios, vídeos ou combinações de tudo isso!
1. **Potfólio de Projetos**:
    1. Faça o "fork" deste repositório, criando uma cópia em seu GitHub pessoal;
    2. Edite seu README com os detalhes do seu projeto, siga nosso [Template](#template) (é só copiar, colar e preencher);
    3. Submeta o link do seu repositório na plataforma da DIO. Pronto, você acabou de fortalecer seu portfólio de projetos nos perfis do GitHub e DIO 🚀
1. **Efeito de Rede**: Compartilhe seus resultados nas redes sociais com a hashtag **#LabDIONattyOrNot**. Não esqueça de nos marcar: [DIO](https://www.linkedin.com/school/dio-makethechange) e [falvojr](https://www.linkedin.com/in/falvojr).

### Template

# IA Generativa da AWS - PartyRock e Bedrock

## 📒 Descrição
Este projeto é um assistente de atendimento ao cliente (chatbot) para um site de e-commerce fictício. O objetivo é usar IA Generativa para responder dúvidas comuns de clientes 24/7 (ex: "Qual o status do meu pedido?", "Qual sua política de devolução?") de forma precisa e contextualizada, melhorando a experiência do usuário.

## 🤖 Tecnologias Utilizadas
* **IA Generativa (Modelos):** Anthropic Claude 3 Sonnet (via Amazon Bedrock).
* **Plataforma de IA:**
    * **PartyRock:** Usado para a fase de prototipagem rápida e prova de conceito (PoC).
    * **Amazon Bedrock:** Usado para a aplicação final em produção, fornecendo a API para o modelo.
* **Outras Ferramentas AWS (para a versão de produção):**
    * **AWS Lambda:** Para rodar o código backend (em Python) que recebe a pergunta do usuário e chama a API do Bedrock.
    * **Amazon API Gateway:** Para expor a função Lambda como uma API REST segura que o frontend do site pode consumir.

## 🧐 Processo de Criação
O processo foi dividido em duas fases:

1.  **Fase 1: Prototipagem (PartyRock)**
    * Primeiro, acessei o PartyRock para validar a ideia sem escrever código.
    * Criei um app simples arrastando e soltando componentes: um "User Input" para a pergunta do cliente e um "Chatbot" para a resposta da IA.
    * No *prompt* do widget de Chatbot, instruí o modelo a "agir como um assistente de atendimento ao cliente de uma loja online".
    * Em 10 minutos, eu já tinha um protótipo funcional para testar diferentes perguntas e ver se o modelo genérico conseguia lidar com elas. Isso validou a ideia.

2.  **Fase 2: Produção (Bedrock + Lambda)**
    * Com a ideia validada, passei para a arquitetura de produção na AWS.
    * Criei uma função AWS Lambda. O código Python dessa função usa o SDK `boto3` para fazer uma chamada `invoke_model` para a API do **Amazon Bedrock**.
    * Na chamada, especifiquei o `modelId` (ex: `anthropic.claude-3-sonnet-v1:0`).
    * O *prompt* enviado ao Bedrock foi muito mais detalhado, incluindo "conhecimento de base" (como a política de devolução exata da loja), para que as respostas fossem precisas e não genéricas.
    * Por fim, usei o API Gateway para criar um endpoint HTTPS que o frontend do site de e-commerce pode chamar via JavaScript para interagir com o chatbot.

## 🚀 Resultados
* **Protótipo (PartyRock):** Um chatbot de prova de conceito funcional em **menos de 15 minutos**, que serviu para alinhar expectativas com a equipe sem gastar tempo de desenvolvimento.
* **Aplicação Final (Bedrock):** Um assistente de IA **escalável, seguro e serverless**. O maior resultado é a flexibilidade: se quisermos testar o Llama 3 ou o Titan, basta mudar o `modelId` na função Lambda, sem alterar o resto da arquitetura. O cliente final recebe respostas instantâneas e precisas, 24/7.

