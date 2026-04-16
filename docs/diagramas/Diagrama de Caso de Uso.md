
```mermaid
graph LR
    subgraph Sistema UniMove
        UC1((Cadastrar/Login))
        UC2((Buscar Carona))
        UC3((Conversar no Chat))
        UC4((Avaliar Motorista))
        UC5((Registrar Veículo))
        UC6((Aceitar Solicitação))
        UC7((Receber Pagamento))
        UC8((Efetuar Pagamento))
    end

    Passageiro((Passageiro))
    Motorista((Motorista))

    %% Ações do Passageiro
    Passageiro --> UC1
    Passageiro --> UC2
    Passageiro --> UC3
    Passageiro --> UC4
    Passageiro --> UC8

    %% Ações do Motorista
    Motorista --> UC1
    Motorista --> UC3
    Motorista --> UC5
    Motorista --> UC6
    Motorista --> UC7
