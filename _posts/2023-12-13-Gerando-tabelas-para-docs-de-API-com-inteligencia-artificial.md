---
layout: post
title: "Gerando tabelas para docs de API com inteligência artificial"
author: pedroAntunes
categories: [API, Inteligência artificial]
image: assets/images/chatGpt.jpg
---

No início de 2023* eu recebi a tarefa de documentar a [root de uma API GraphQL](https://graphql.org/learn/execution/#root-fields-resolvers). Não vou entrar em detalhes técnicos, mas, em resumo, era uma API com mais de 100 campos pra documentar, mas que não são explícitos organizados na camada GraphQL.

_Esse texto foi publicado originalmente em junho de 2023 e migrado para este formato em dezembro de 2023._

O primeiro passo foi pedir socorro ao time de desenvolvimento, que me mostrou como fuçar o código da API para descobrir o nome e o tipo dos campos. Uma vez que eu tinha essas informações estruturadas, era uma questão de criar descrições para todos os campos.

Acontece que ao documentar APIs, a maior parte das informações nas descrições dos campos pode ser inferida dos nomes e tipos dos campos, dado que você tenha um mínimo de contexto do produto. A natureza contextual, tipificada e granular desse tipo de informação me fez pensar que seria uma boa oportunidade de usar inteligência artificial para agilizar o processo.

Então criei uma ferramenta que te permite inserir os nomes e tipos dos campos em uma planilha e gerar automaticamente tabelas de campos da API com descrições, geradas por IA, em Markdown ou HTML. Ela funciona para várias tabelas ao mesmo tempo se você estiver trabalhando com estruturas de dados complexas.

É necessário corrigir as descrições geradas e preencher lacunas. Ainda sim, achei que agilizou muito o processo de redação na prática.

Abaixo eu vou resumir o funcionamento dessa ferramenta e mostrar como você pode usar nas suas docs. Você também pode ver outros recursos relacionados:
- [Repositório no GitHub](https://github.com/PedroAntunesCosta/automatic-api-docs-tables)
- [Input vs. output (exemplo)](https://github.com/PedroAntunesCosta/automatic-api-docs-tables/blob/main/EXAMPLE.md)

_A documentação resultante não está mais disponível publicamente devido à evolução do produto._

## Como funciona

Eu usei [Google Apps Script](https://www.google.com/script/start/), para fazer um código em Javascript que:
1. Puxa informações de uma planilha.
2. Formata as informações em tabelas HTML ou Markdown.
3. Envia as tabelas para a [API do ChatGPT](https://platform.openai.com/docs/guides/chat).
4. Coloca a informação retornada pelo ChatGPT em um doc.

Ao implementar a ferramenta na sua planilha, você pode alterar o prompt e as configurações da chamada do ChatGPT. As configurações que funcionaram pra mim e que você encontra no repositório são as seguintes:

```
var prompt = 'Please fill in the third column of the ' + docFormat + ' table below with short objective descriptions.' + table;
    var payload = {
      'model': 'gpt-3.5-turbo',
      'temperature': 0.5,
      'messages': [
        {
        'role': 'system',
        'content': 'You are an API documentation specialist.'
        },
        {
        'role': 'user',
        'content': prompt
        }
      ]
    };
```

## Como usar

Veja abaixo como configurar e usar essa ferramenta.

_Você não precisa saber programar, mas é necessário ter uma conta "pay as you go" da Open AI. Mais detalhes abaixo._

## Configuração

Existem duas etapas para configurar e usar essa ferramenta. Primeiro, você precisa obter uma chave de API da Open AI e, em seguida, configurar o Google Apps Script.

## Obter uma chave de API da Open AI

Você precisa pagar para usar as APIs da Open AI, incluindo o ChatGPT, que é uma dependência desta ferramenta. Mas calma, é bem barato e você pode colocar um limite mensal de gastos. O modelo de conta "pay as you go" da Open AI permite que você pague por solicitação, enquanto trabalha com uma variedade de APIs, incluindo Dall-e, ChatGPT e preenchimento de texto com GPT-4.

Essa ferramenta funciona com várias tabelas ao mesmo tempo, mas chama a API do ChatGPT uma vez para cada tabela. Recomendo que você verifique os [preços da API da Open AI](https://openai.com/pricing), que podem variar se você ajustar os parâmetros. No entanto, com as configurações padrão dessa ferramenta, eu gerei dezenas de tabelas por menos de U$0,50.

Veja este artigo sobre como [criar uma conta na Open AI e obter sua chave de API](Veja este artigo sobre como criar uma conta na Open AI e obter sua chave de API.).

## Configurar o Google Apps Script

Após obter sua chave de API da Open AI, siga estas etapas para configurar o script:

1. Crie um novo documento no Google Drive. Este documento receberá as tabelas geradas pelo script.
2. Crie uma nova planilha no Google Drive.
3. Na planilha recém-criada, vá em **Extensões > Apps Script**.
4. Isso abrirá um novo projeto do Apps Script em uma nova guia. Crie os arquivos necessários e copie o código de acordo com a pasta **Google Apps Script** [deste repositório](https://github.com/PedroAntunesCosta/automatic-api-docs-tables).
5. Vá para o arquivo `Configs.gs` do seu projeto do Apps Script e preencha as variáveis ​​conforme este exemplo:
    - `OPEN_AI_KEY`: sua chave de API da Open AI.
    - `FIELDS_SHEET_ID`: ID da planilha recém-criada. Você pode obter esse ID na URL da planilha, que segue o formato: `https://docs.google.com/spreadsheets/d/+{id-da-planilha}+/edit#gid=0`.
    - `OUTPUT_DOC_ID`: ID do documento recém-criado. Você pode obter esse ID na URL do documento, que segue o formato: `https://docs.google.com/document/d/+{id-do-documento}+/edit`.
6. Salve seu projeto do Apps Script.
7. Vá para sua planilha e preencha as quatro primeiras células (A, B, C e D) da primeira linha com os seguintes valores:
    - A - Nome da tabela
    - B - Nome do campo
    - C - Tipo do campo
    - D - Formato 

Com estas configurações, você estará pronto para gerar suas tabelas.

_Saiba mais sobre [Google Apps Script](https://www.google.com/script/start/)._

## Exemplo de configuração

Considere estas URLs:
- Planilha: `https://docs.google.com/spreadsheets/d/1hPdQBb-7yDCvsd8XAqPg2345uigLKQi0Cvj1VwGoZs/edit#gid=0`
- Documento: `https://docs.google.com/document/d/1W7erIcdFKqVc33mRluih11l16CS_ZQfhC-lElfv4KGiM/edit`

E esta chave de API da Open AI:
- `sk-6H234wdfUwiTfdbCT3Blf45ZHzsj4wrev`

Seu arquivo `Configs.gs` deve ficar assim:

```
OPEN_AI_KEY = "sk-6H234wdfUwiTfdbCT3Blf45ZHzsj4wrev"
FIELDS_SHEET_ID = "1hPdQBb-7yDC9nzb4e8XAqPgvSThSLKQi0Cvj1VwGoZs"
OUTPUT_DOC_ID = "1W7erIcdFKqVc33mRgQAwl16CS_ZQfhC-lElXRlWKGiM"
```

## Usando a ferramenta

Para gerar as tabelas automáticas de documentação da sua API, siga estes passos:

1. Abra a sua planilha.
2. Insira os seus dados, onde cada linha corresponde a um campo e deve conter três características:
    - `Nome da tabela`: nome da tabela a qual o campo pertence. Este será o título no resultado final. Isso é especialmente relevante ao documentar objetos dentro de objetos.
    - `Nomes dos campos`: nome do campo.
    - `Tipo`: tipo do campo.
3. Escolha o formato da tabela na célula D2. Atualmente, Markdown e HTML estão disponíveis.
4. Acesse o menu `Generate`. Se você não conseguir ver este menu, atualize a página e tente novamente.
5. Clique em `Generate descriptions`.
6. Vá para o documento de saída.
7. Copie as tabelas geradas e utilize-as no seu documento.

_ATENÇÃO! A formatação das tabelas é “hard-coded”, mas elas passam pela API ChatGPT antes que o resultado esteja disponível, o que pode introduzir algumas inconsistências. Portanto, você deve verificar novamente a formatação das suas tabelas e revisar todas as descrições antes de publicar. Pelos testes que realizei até agora, parece improvável que o formato da tabela seja um problema, mas é muito provável que você precise editar uma pequena quantidade das descrições._