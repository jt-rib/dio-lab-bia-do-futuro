# Código da Aplicação

Esta pasta contém o código do seu agente financeiro.

## Estrutura 

```
src/
├── app.py              # Aplicação principal (Streamlit)
├── agente.py           # Lógica do agente
├── config.py           # Configurações
└── requirements.txt    # Dependências
```

## requirements.txt

```
streamlit
ollama
python-dotenv
```

## config.py

```bash
import os
from dotenv import load_dotenv

# Carrega variáveis de ambiente
load_dotenv()

# Configurações básicas
LLM_MODEL = os.getenv("LLM_MODEL", "llama3")
```

## agente.py

```
import ollama
from config import LLM_MODEL

SYSTEM_PROMPT = """
Você é a BIA (Bot Inteligente de Apoio), uma assistente financeira digital amigável e educativa.
Seu objetivo é ajudar usuários a organizar suas finanças pessoais de forma simples e acessível.

REGRAS:
1. Sempre baseie suas respostas nos dados fornecidos (mockados).
2. Nunca invente informações financeiras ou dados bancários reais.
3. Se não souber algo, admita e ofereça alternativas seguras.
4. Explique conceitos financeiros de forma clara e acessível.
5. Não faça recomendações de investimento sem conhecer o perfil do cliente.
6. Seja consultiva, amigável e direta, evitando jargões técnicos.
"""

def responder(mensagens):
    """Função que envia mensagens para o modelo e retorna resposta"""
    response = ollama.chat(
        model=LLM_MODEL,
        messages=[
            {"role": "system", "content": SYSTEM_PROMPT},
            *mensagens
        ]
    )
    return response["message"]["content"]
```

## app.py

```
import streamlit as st
from agente import responder

st.set_page_config(page_title="Chatbot BIA", page_icon="🤖")
st.title("🤖 Chatbot BIA")
st.write("Converse com a BIA sobre suas finanças pessoais.")

if "messages" not in st.session_state:
    st.session_state["messages"] = []

user_input = st.chat_input("Digite sua mensagem...")

if user_input:
    st.session_state["messages"].append({"role": "user", "content": user_input})
    resposta = responder(st.session_state["messages"])
    st.session_state["messages"].append({"role": "assistant", "content": resposta})

for msg in st.session_state["messages"]:
    if msg["role"] == "user":
        st.chat_message("user").write(msg["content"])
    else:
        st.chat_message("assistant").write(msg["content"])
```

## Como Rodar

```
# Entrar na pasta src
cd src

# Instalar dependências
pip install -r requirements.txt

# Rodar a aplicação
streamlit run app.py
```

