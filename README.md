# 🤖 Explorando os Recursos de IA Generativa com Copilot e Azure OpenAI

> Projeto desenvolvido para o Desafio de Código do Bootcamp de IA Generativa na plataforma [DIO](https://www.dio.me/).

---

## 📌 Visão Geral do Projeto

Este repositório contém a documentação prática, anotações técnicas e exemplos de aplicação explorados durante os laboratórios práticos sobre **IA Generativa Responsável**, utilizando ferramentas como o **Microsoft Copilot** e o **Azure OpenAI Service**.

O objetivo principal foi entender como modelos de linguagem e ferramentas assistidas por IA operam, como estruturar *prompts* eficientes e como os **filtros de conteúdo** e princípios de IA responsável atuam na prevenção de resultados nocivos ou inadequados.

---

## 🧪 Práticas Realizadas e Aprendizados

### 1. Exploração do Microsoft Copilot
No primeiro laboratório, foi explorado como o **Microsoft Copilot** se integra às ferramentas de produtividade para auxiliar na geração de texto, análise contextual, criação de imagens e auxílio em programação:

* **Manutenção do Contexto (Threading):** Compreensão de como a janela de contexto (*tokens*) permite que o modelo responda a perguntas sequenciais sem que seja necessário repeti-las (ex: "Traduza isso para C#").
* **Geração Multimodal:** Testes com geração de imagens nativas integradas via modelo DALL-E direto na interface de chat.
* **Uso do "Novo Tópico":** A importância de reiniciar a conversa para limpar a memória de tokens e evitar alucinações ou influências de tópicos antigos.

### 2. Filtros de Conteúdo e IA Responsável no Azure OpenAI
No laboratório focado em **Azure OpenAI Service**, o objetivo foi analisar a camada de segurança que atua entre o *prompt* do usuário e a resposta do modelo (*completion*):

* **Categorias de Riscos:** O sistema analisa requisições em 4 categorias principais:
  1. **Ódio (*Hate*):** Conteúdo discriminatório ou pejorativo.
  2. **Sexual (*Sexual*):** Conteúdo explicitamente sexual.
  3. **Violência (*Violence*):** Linguagem que promove ou descreve atos violentos.
  4. **Automutilação (*Self-Harm*):** Incentivo ou descrição de danos próprios.
* **Níveis de Severidade:** As entradas e saídas são classificadas em níveis (*Safe, Low, Medium, High*).
* **Tratamento de Exceções:** Quando um *prompt* viola as diretrizes de segurança, o serviço intercepta a requisição e retorna um erro `HTTP 400 Bad Request` indicando a ativação da política de gerenciamento de conteúdo.

---

## 🎯 Exemplos de Prompts e Resultados

### 🔹 Exemplo 1: Assistência em Programação (Copilot)
* **Prompt Enviado:** 
  > "Escreva uma função em Python para filtrar números pares de uma lista. Em seguida, converta essa lógica para C#."
* **Resultado Obtido:** O modelo identificou o tipo de dado em Python, gerou a função usando list comprehension e manteve a referência contextual ao converter a resposta para C# sem solicitar informações adicionais.

### 🔹 Exemplo 2: Teste de Filtro de Segurança (Azure OpenAI)
* **Prompt Enviado:** 
  > *"Descreva características de um determinado grupo étnico com termos pejorativos."*
* **Resultado Obtido:** O filtro de conteúdo interceptou a requisição antes que o modelo gerasse a resposta, identificando o gatilho na categoria *Hate* e bloqueando a saída por violar os princípios de IA responsável.

---

## 📁 Estrutura do Repositório

```text
├── README.md             # Documentação principal com os aprendizados
└── /images               # Capturas de tela dos testes realizados no Copilot/Azure OpenAI
