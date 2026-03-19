# Base de Conhecimento

## Dados Utilizados

| Arquivo | Formato | Utilização no Agente |
|---------|---------|----------------------|
| `historico_atendimento.csv` | CSV | Contextualizar interações anteriores e manter histórico de suporte |
| `perfil_investidor.json` | JSON | Personalizar recomendações de acordo com perfil e preferências |
| `produtos_financeiros.json` | JSON | Sugerir produtos e serviços adequados ao perfil do cliente |
| `transacoes.csv` | CSV | Analisar padrão de gastos e identificar alertas de consumo |

> [!TIP]
> **Quer um dataset mais robusto?** Você pode utilizar datasets públicos do [Hugging Face](https://huggingface.co/datasets) relacionados a finanças, desde que sejam adequados ao contexto do desafio.

---

## Adaptações nos Dados

Foram feitas pequenas adaptações nos dados mockados para o caso de uso:
- Inclusão de categorias de gastos (ex: lazer, alimentação, transporte).  
- Simulação de metas financeiras no perfil do cliente.  
- Expansão da lista de produtos financeiros com exemplos fictícios.  

---

## Estratégia de Integração

### Como os dados são carregados?
Os arquivos CSV e JSON são carregados no início da sessão do agente.  
Eles são processados e transformados em estruturas simples (listas e dicionários) para serem incluídos no contexto do prompt.

### Como os dados são usados no prompt?
- Os dados relevantes são consultados dinamicamente conforme a interação.  
- Informações do perfil e histórico são incluídas no **system prompt** para personalizar respostas.  
- Transações recentes são exibidas como exemplos durante a conversa.  

---

## Exemplo de Contexto Montado

Dados do Cliente:

Nome: João Silva

Perfil: Moderado

Saldo disponível: R$ 5.000

Últimas transações:

01/11: Supermercado - R$ 450

03/11: Streaming - R$ 55

05/11: Transporte - R$ 120

Produtos disponíveis:

Conta digital sem tarifas

Fundo de investimento moderado

Seguro de vida básico
