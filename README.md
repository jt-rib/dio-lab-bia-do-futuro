# 🧾 Projeto BIA – Bot Inteligente de Apoio

![Forked Project](https://img.shields.io/badge/Status-Forked-blue)
![Educational Demo](https://img.shields.io/badge/Type-Educational%20Demo-green)

Este repositório é um **fork** criado para desenvolver e documentar um agente financeiro digital chamado **BIA (Bot Inteligente de Apoio)**.  
O objetivo é oferecer um protótipo funcional de chatbot que ajuda usuários a organizar suas finanças pessoais de forma simples, acessível e educativa.

---

## 🎯 Objetivo do Projeto

- Criar um **assistente financeiro digital** capaz de:
  - Monitorar gastos simulados (dados mockados).
  - Definir metas de economia personalizadas.
  - Dar dicas práticas de planejamento financeiro.
  - Responder de forma segura e consultiva, sem inventar dados.

---

## 📂 Estrutura do Projeto

docs/                # Documentação
├── 01-contexto.md  # Contexto e problema
├── 02-dados.md     # Base de dados mockada
├── 03-prompts.md   # System prompt e exemplos
├── 04-metricas.md  # Avaliação e métricas
└── 05-pitch.md     # Pitch de apresentação

src/                 # Código da aplicação
├── app.py          # Interface Streamlit
├── agente.py       # Lógica do agente
├── config.py       # Configurações
└── requirements.txt# Dependências

data/                # Dados fictícios para testes
├── transacoes.csv
├── perfil_investidor.json
├── produtos_financeiros.json
└── historico_atendimento.csv


---

## 🔄 Alterações Realizadas

- **System Prompt** definido em `docs/03-prompts.md` com regras claras para evitar alucinações.  
- **Exemplos de interação** e **edge cases** documentados para guiar o comportamento do agente.  
- **Aplicação funcional** criada em `src/` usando **Streamlit** + **Ollama**.  
- **Base de dados mockada** adicionada em `data/` para simular consultas reais.  
- **Métricas de avaliação** descritas em `docs/04-metricas.md` para medir assertividade, segurança e coerência.  
- **Pitch** estruturado em `docs/05-pitch.md` para apresentação em vídeo/slides.  

---

## 🚀 Como Rodar

```bash
# Entrar na pasta src
cd src

# Instalar dependências
pip install -r requirements.txt

# Rodar a aplicação
streamlit run app.py
 ```
📌 Observação
Este projeto é um fork e não representa um produto final.
Ele foi desenvolvido com fins educacionais e demonstrativos, utilizando dados fictícios para simulação.

📽 Pitch
Este repositório contém a apresentação da BIA (Bot Inteligente de Apoio).
📄 [Clique aqui para ver a apresentação](docs/apresentacao_bia.pdf)


✨ Conclusão
O projeto mostra como construir um agente financeiro digital passo a passo:

Definição de contexto e problema.

Criação de base de dados mockada.

Implementação de chatbot funcional.

Avaliação com métricas.

Pitch final para apresentação.
