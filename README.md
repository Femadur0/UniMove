# UniMove

O **UniMove** é um projeto de um aplicativo de transporte voluntário de universitário para universitário, trazendo preços mais acessiveis para pessoas que tenham necessidade de deslocamento para universidades e faculdades. A ideia é fazer com que pessoas que já vão de carro para faculdade, se volutanriem para levar outros alunos, e ainda ganhar uma pequeno renda extra.


## Objetivo do Projeto

O objetivo do projeto é aplicar conceitos de desenvolvimento de aplicativos e organização de projetos, criando um aplicativo de transporte para alunos de faculdades e universidades.

Durante o desenvolvimento foram utilizados conceitos como:

* Criação de um aplicativo
* Sistema de Login e cadastro
* Organização de corridas 
* Busca de voluntários que já vão de carro para a instituição de ensino
* Controle de versão com GitHub
* Organização de tarefas com Kanban

## Tecnologias Utilizadas

* HTML5
* CSS3
* PHP
* MySQL
* Git
* GitHub
* Python

## Funcionalidades do Sistema

* Cadastro de usuários
* Login de usuários
* Possibilidade de combinar corridas
* Possibilidade de se cadastrar como motorista
* 
* Adição de produtos ao carrinho

## Metodologia

O projeto utiliza princípios de **metodologia ágil**, organizando o desenvolvimento através de:

* Histórias de usuário
* Kanban
* Organização de tarefas no GitHub Projects



```mermaid

sequenceDiagram
    participant U as Usuário (Universitário)
    participant APP as Aplicativo UniMove
    participant API as Backend (Servidor)
    participant DB as Banco de Dados
    participant M as Motorista

    %% Cadastro e Login
    U->>APP: Cadastrar novo usuário
    APP->>API: Envia dados de cadastro
    API->>DB: Salva usuário
    DB-->>API: Confirma cadastro
    API-->>APP: Cadastro realizado

    U->>APP: Login no sistema
    APP->>API: Envia credenciais
    API->>DB: Valida usuário
    DB-->>API: Dados válidos
    API-->>APP: Login autorizado

    %% Solicitação de corrida
    U->>APP: Definir ponto de encontro
    APP->>API: Envia localização
    API-->>APP: Confirma localização

    U->>APP: Buscar corrida
    APP->>API: Solicita motoristas disponíveis
    API->>DB: Consulta motoristas
    DB-->>API: Lista de motoristas
    API-->>APP: Exibe opções

    U->>APP: Solicitar carona
    APP->>API: Envia solicitação
    API-->>M: Notifica motorista

    M->>API: Aceitar/Rejeitar corrida
    API-->>APP: Retorna status

    %% Pagamento
    U->>APP: Escolher forma de pagamento
    APP->>API: Processar pagamento
    API->>DB: Registrar pagamento
    DB-->>API: Confirma pagamento
    API-->>APP: Corrida confirmada

    %% Durante a corrida
    APP-->>U: Exibir trajeto em tempo real
    API-->>APP: Atualiza localização

    %% Finalização
    API-->>APP: Corrida finalizada
    APP-->>U: Solicitar avaliação
    U->>APP: Avaliar motorista
    APP->>API: Enviar avaliação
    API->>DB: Salvar avaliação

    %% Extras
    U->>APP: Visualizar histórico de corridas
    APP->>API: Solicita histórico
    API->>DB: Busca dados
    DB-->>API: Retorna histórico
    API-->>APP: Exibe histórico

    U->>APP: Cancelar corrida
    APP->>API: Solicita cancelamento
    API-->>M: Notifica cancelamento
