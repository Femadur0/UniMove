
```mermaid
stateDiagram-v2
    [*] --> Solicitada: Passageiro busca carona
    
    Solicitada --> Pendente: Aguardando aceite do motorista
    
    Pendente --> Cancelada: Passageiro desistiu
    Pendente --> Aceita: Motorista confirmou a carona
    Pendente --> Rejeitada: Motorista recusou a solicitação
    
    Rejeitada --> Solicitada: Sistema busca novo motorista
    
    Aceita --> EmAndamento: Motorista iniciou o trajeto
    
    EmAndamento --> Finalizada: Destino atingido
    
    Finalizada --> Avaliada: Passageiro enviou feedback
    
    Avaliada --> [*]
    Cancelada --> [*]
