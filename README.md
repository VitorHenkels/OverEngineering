Título: OverEngineering

descrição: projeto educacional para aplicação de ensinamentos do dia a dia corporativo

objetivo: Simular sistema de banco, com funções como: sacara, depositar, entre outros. Em primeiro momento será desenvolvido somente através de terminal, através de Java e Maven.
As funções a serem implementadas estão em : [modelagem](modeling/main.readme)

```mermaid
flowchart LR
    %% Direção Left to Right para ficar horizontal
    A([Início]) --> B[Autenticar Operador]
    B --> C{Autorização válida?}
    C -- Não --> Z[Exibir mensagem de erro] --> F([Fim])
    C -- Sim --> D[Selecionar função "Carregar Dinheiro"]
    D --> E[Abrir compartimento de cédulas]
    E --> G[Inserir valor e quantidade de cédulas]
    G --> H{Valores corretos?}
    H -- Não --> I[Solicitar correção] --> G
    H -- Sim --> J[Confirmar operação]
    J --> K[Atualizar saldo no sistema]
    K --> L[Emitir comprovante]
    L --> M[Fechar compartimento e encerrar sessão]
    M --> F([Fim])
