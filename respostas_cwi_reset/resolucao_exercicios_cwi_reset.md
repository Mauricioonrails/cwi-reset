<h1>Resolução dos exercicios  e desafios CWI-RESET</h1>

## <u>Módulo 1 - Testes de Software</u>

### 1. Exercício (Aula 02 - Planejamento de Testes):

1. Cite 2 exemplo de técnicas de planejamento de testes.

2. Cite 3 exemplos de artefatos/documentos possíveis para a modelagem de testes?

#### Resolução:

1. Uso de Gráfico de Pareto para a priorização dos testes e uso de mapas mentais para entendimento e organização
   
   das informações.

2. Possíveis artefatos/documentos gerados:
   
   - Casos de teste;
   
   - User story;
   
   - Tabelas;
   
   - Diagramas;
   
   - Checklists.

## <u>Módulo 2 - Níveis de Teste</u>

### 2. Exercício (Aula 01 - Níveis, técnicas e tipos de teste):

1. Cite 2 técnicas de teste de caixa preta.

2. O que você entende por testes de caixa preta e testes de caixa branca?

#### Resolução:

1. Técnicas de teste caixa preta:
   
   - Tabela de decisão;
   
   - Análise Valor Limite;
   
   - Partição de Equivalência.

2. Entendimento das técnicas:
   
   - Caixa Branca: Conjunto de testes baseados na estrutura interna de um componente ou sistema. São exemplos de testes: cobertura de comandos, condições e loops.
   - Caixa Preta: Conjunto de testes baseados no comportamento e nas regras de negócio. São exemplos de testes: Análise de Valor Limite, Partição de Equivalência e Diagrama de Estado.

### 2.1 Exercício (Aula 04 - Casos de Teste):

Elabore cenários simulando testes na funcionalidade de login do Google (exemplo da imagem abaixo).

#### Resolução:

1. Tabela de Decisão

| Variáveis | Partição     | CT-01 | CT-02 | CT-03 | CT-04 | CT-05 |
|:---------:|:------------:|:-----:|:-----:|:-----:|:-----:|:-----:|
| E-mail    | Válido       | x     | x     |       |       | x     |
|           | Inválido     |       |       | x     |       |       |
| Senha     | Válido       | x     |       |       |       |       |
|           | Inválido     |       | x     |       |       |       |
| Acesso    | Liberado     | x     |       |       |       |       |
|           | Não liberado |       | x     | x     | x     | x     |

2. Casos de Teste
   2.1 CT-01 - Acessar o sistema com um usuário válido

| Passos | Descrição                                     | Resultado esperado                   |
|:------:|:---------------------------------------------:|:------------------------------------:|
| 1      | Acessar o site                                | Ser direcionado para página de Login |
| 2      | Preencher o campo E-mail com um e-mail válido | Não ocorrer erro                     |
| 3      | Clicar no botão “Avançar”                     | Avançar para a página de senha       |
| 4      | Preencher o campo Senha com um valor válido   | Não ocorrer erro                     |
| 5      | Clicar no botão “Avançar”                     | Ser direcionado para a aplicação     |

       Gherkin:

    Cenário: Acessar o sistema com um usuário válido
    Dado que acessei a aplicação
    E fui direcionado para o login
    Quando preencho meus dados de acesso corretamente
    Então sou redirecionado para a aplicação   

     2.2 CT-02 - Acessar o sitema com e-mail válido e senha inválida

| Passos | Descrição                                     | Resultado esperado                   |
|:------:|:---------------------------------------------:|:------------------------------------:|
| 1      | Acessar o site                                | Ser direcionado para página de Login |
| 2      | Preencher o campo E-mail com um e-mail válido | Não ocorrer erro                     |
| 3      | Clicar no botão “Avançar”                     | Avançar para a página de senha       |
| 4      | Preencher o campo Senha com um valor inválido | Enviar mensagem de erro              |
| 5      | Clicar no botão “Avançar”                     | Não ser direcionado para a aplicação |

    Gherkin:

    Cenário: Acessar o sitema com e-mail válido e senha inválida
    Dado que acessei a aplicação
    E fui direcionado para o login
    Quando preencho meus dados de acesso com um e-mail válido
    E preencho meus dados de acesso com uma senha inválida
    Então não sou redirecionado para a aplicação    

     2.3 CT-03 - Acessar o sistema com e-mail inválido

| Passos | Descrição                                       | Resultado esperado                         |
|:------:|:-----------------------------------------------:|:------------------------------------------:|
| 1      | Acessar o site                                  | Ser direcionado para página de Login       |
| 2      | Preencher o campo E-mail com um e-mail inválido | Enviar mensagem de erro                    |
| 3      | Clicar no botão “Avançar”                       | Não ser direcionado para a página de senha |

     Gherkin:

    Cenário: Acessar o sistema com e-mail inválido
    Dado que acessei a aplicação
    E fui direcionado para o login
    Quando preencho meus dados de acesso com um e-mail inválido
    Então não sou redirecionado para a página de senha

    2.4 CT-04 - Acessar o sistema e não preenher o campo "E-mail"

| Passos | Descrição                    | Resultado esperado                         |
|:------:|:----------------------------:|:------------------------------------------:|
| 1      | Acessar o site               | Ser direcionado para página de Login       |
| 2      | Não preencher o campo E-mail | Enviar mensagem de erro                    |
| 3      | Clicar no botão “Avançar”    | Não ser direcionado para a página de senha |

       Gherkin:

    Cenário: Acessar o sistema e não preenher o campo "E-mail"
    Dado que acessei a aplicação
    E fui direcionado para o login
    Quando não preencho o campo "E-mail"
    Então não sou redirecionado para a página de senha

    2.5 CT-05 - Acessar o sitema com e-mail válido e não preenher o campo "Senha"

| Passos | Descrição                                     | Resultado esperado                   |
|:------:|:---------------------------------------------:|:------------------------------------:|
| 1      | Acessar o site                                | Ser direcionado para página de Login |
| 2      | Preencher o campo E-mail com um e-mail válido | Não ocorrer erro                     |
| 3      | Clicar no botão “Avançar”                     | Avançar para a página de senha       |
| 4      | Não preencher o campo Senha                   | Enviar mensagem de erro              |
| 5      | Clicar no botão “Avançar”                     | Não ser direcionado para a aplicação |

    Gherkin:

    Cenário: Acessar o sitema com e-mail válido e não preenher o campo "Senha"
    Dado que acessei a aplicação
    E fui direcionado para o login
    Quando preencho meus dados de acesso com um e-mail válido
    E não preencho o campo "Senha"
    Então não sou redirecionado para a aplicação
