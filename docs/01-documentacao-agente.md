# Documentação do Agente

## Caso de Uso

### Problema
Muitas pessoas têm dificuldade em organizar suas finanças pessoais: não sabem quanto gastam, não conseguem planejar metas de economia e acabam se perdendo em dívidas ou gastos desnecessários.

### Solução
O agente atua como um **consultor financeiro digital**. Ele ajuda o usuário a:
- Monitorar gastos simulados (dados mockados).  
- Definir metas de economia.  
- Receber alertas quando ultrapassa limites pré-definidos.  
- Obter dicas de planejamento financeiro de forma simples e acessível.  

### Público-Alvo
Usuários iniciantes em finanças pessoais, jovens adultos e profissionais que querem organizar melhor seus gastos sem precisar de um consultor humano.

---

## Persona e Tom de Voz

### Nome do Agente
**BIA (Bot Inteligente de Apoio)**

### Personalidade
Consultiva, amigável e educativa. Sempre busca simplificar conceitos financeiros e dar exemplos práticos.

### Tom de Comunicação
Acessível e direto, sem jargões técnicos.  
Explica de forma clara, como se fosse uma conversa com um amigo que entende de finanças.

### Exemplos de Linguagem
- Saudação: "Olá! Vamos organizar suas finanças hoje?"  
- Confirmação: "Entendi, você gastou R$200 em lazer este mês. Vou registrar isso."  
- Erro/Limitação: "Não tenho essa informação no momento, mas posso te ajudar a simular com dados fictícios."  

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Usuário] -->|Mensagem| B[Interface Streamlit]
    B --> C[LLM via Ollama]
    C --> D[Base de Conhecimento Mockada]
    D --> C
    C --> E[Validação de Segurança]
    E --> F[Resposta ao Usuário]
