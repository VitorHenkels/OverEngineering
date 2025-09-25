Título: OverEngineering

descrição: projeto educacional para aplicação de ensinamentos do dia a dia corporativo

objetivo: Simular sistema de banco, com funções como: sacara, depositar, entre outros. Em primeiro momento será desenvolvido somente através de terminal, através de Java e Maven.
As funções a serem implementadas estão em : [modelagem](modeling/main.readme)

```mermaid
flowchart LR
    %% Fluxo left-to-right
    A([Inicio]) --> B[Autenticar Operador]
    B --> C{Autorizacao valida?}
    C -- Nao --> Z[Exibir mensagem de erro] --> F([Fim])
    C -- Sim --> D[Selecionar funcao Carregar Dinheiro]
    D --> E[Abrir compartimento de cedulas]
    E --> G[Inserir valor e quantidade de cedulas]
    G --> H{Valores corretos?}
    H -- Nao --> I[Solicitar correcao] --> G
    H -- Sim --> J[Confirmar operacao]
    J --> K[Atualizar saldo no sistema]
    K --> L[Emitir comprovante]
    L --> M[Fechar compartimento e encerrar sessao]
    M --> F([Fim])
