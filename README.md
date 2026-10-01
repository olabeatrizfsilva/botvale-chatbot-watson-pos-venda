# 🤖 botVale - Chatbot de Pós-Venda (IBM Watson Assistant)

Chatbot de pós-venda criado no **IBM Watson Assistant** para registrar solicitações de assistência técnica e troca de produtos de forma automatizada.

## 📌 Funcionalidades

- Saudação inicial ao cliente
- Reconhecimento da intenção `#agendar_assistencia`
- Coleta de dados por **slots**:
  - `@pedido` → número do pedido
  - `@cpf` → CPF do cliente
  - `@produto` → produto envolvido
  - `@motivo_troca` → motivo da troca/problema
- Mensagem final de confirmação com resumo da solicitação

## 🔄 Fluxograma da conversa

```mermaid
flowchart TD
    A([INÍCIO DA CONVERSA<br>#iniciar_saudacao]) --> B[MENSAGEM DE SAUDAÇÃO<br>'Eu sou o botVale, estou aqui para te ajudar!']
    B --> C{RECONHECIMENTO DE INTENÇÃO<br>#agendar_assistencia}
    C --> D[ENTRADA NO NÓ DE AGENDAMENTO<br>Início da Assistência via Slots]
    
    D --> E1[SLOT 1<br>Check: @pedido<br>Save: $pedido]
    D --> E2[SLOT 2<br>Check: @cpf<br>Save: $cpf]
    D --> E3[SLOT 3<br>Check: @produto<br>Save: $produto]
    D --> E4[SLOT 4<br>Check: @motivo_troca / input.text<br>Save: $motivo_troca]
    
    E1 --> F{Todos os 4 Slots<br>preenchidos?}
    E2 --> F
    E3 --> F
    E4 --> F
    
    F -->|Sim| G["RESPOSTA FINAL DE CONFIRMAÇÃO<br>'Solicitação registrada com sucesso!<br>Resumo: Pedido: $pedido - CPF: $cpf<br>Produto: $produto - Problema: $motivo_troca - Em breve você receberá as instruções por e-mail.'"]
    G --> H([FIM DO FLUXO])

    style A fill:#4A90E2,stroke:#1C3D5A,color:#fff
    style H fill:#4A90E2,stroke:#1C3D5A,color:#fff
    style D fill:#f9f9f9,stroke:#333,stroke-width:2px
    style G fill:#2ECC71,stroke:#27AE60,color:#fff
```

## 🛠️ Tecnologias

- IBM Watson Assistant
- Mermaid (documentação do fluxo)

## 👨‍💻 Autor

Beatriz Fernandes - Curso de Análise e Desenvolvimento de Sistemas (ADS)
