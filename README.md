# Configuração e Uso do Azure Cognitive Search

## Introdução

Este projeto faz parte de um bootcamp focado na obtenção da certificação **AI-900**, realizado na **DIO** durante o evento **Decola Teh 2025**. O objetivo deste projeto é explorar as funcionalidades e o potencial do **Azure Cognitive Search** para criar experiências de busca inteligentes e escaláveis. Ao longo deste trabalho, foram aplicados conceitos de indexação, análise linguística e integração com outras ferramentas do ecossistema Azure, demonstrando como esta tecnologia pode ser um diferencial em soluções de busca e análise de dados.


Este documento apresenta um guia passo a passo para configurar uma instância de pesquisa utilizando o Azure Cognitive Search. Além disso, serão destacados insights, as possibilidades de integração com outras ferramentas e os aprendizados adquiridos durante o processo.

## Sumário

- [Introdução](#introdução)
- [Pré-requisitos](#pré-requisitos)
- [Passo a Passo](#passo-a-passo)
  - [1. Criação do Serviço de Pesquisa](#1-criação-do-serviço-de-pesquisa)
  - [2. Definição do Índice](#2-definição-do-índice)
  - [3. Carregamento dos Dados](#3-carregamento-dos-dados)
  - [4. Configuração de Analisadores e Scoring Profiles](#4-configuração-de-analisadores-e-scoring-profiles)
  - [5. Execução de Consultas](#5-execução-de-consultas)
- [Insights e Aprendizados](#insights-e-aprendizados)
- [Possibilidades de Integração](#possibilidades-de-integração)
- [Considerações Finais](#considerações-finais)

## Introdução

O **Azure Cognitive Search** é um serviço de pesquisa baseado na nuvem que permite criar experiências de busca sofisticadas em aplicações e websites. Com ele, é possível indexar diferentes fontes de dados, realizar consultas com filtros avançados, e aplicar inteligência artificial para enriquecer os dados.

## Pré-requisitos

- Conta ativa no **Azure Portal**.
- Conhecimento básico de **REST APIs** e **JSON**.
- Dados estruturados (pode ser de um banco de dados, arquivos JSON, ou blobs no Azure Storage) para serem indexados.

## Passo a Passo

### 1. Criação do Serviço de Pesquisa

1. Acesse o [Azure Portal](https://portal.azure.com/).
2. Clique em **"Criar um recurso"** e pesquise por **"Azure Cognitive Search"**.
3. Selecione o serviço e clique em **"Criar"**.
4. Preencha as informações necessárias, como **nome do serviço**, **localização** e **camada de preço**.
5. Clique em **"Revisar + criar"** e, em seguida, em **"Criar"** para provisionar o serviço.

### 2. Definição do Índice

1. Após criar o serviço, navegue até ele e selecione a opção **"Índices"**.
2. Clique em **"Adicionar índice"**.
3. Defina o nome do índice e adicione os campos com seus respectivos tipos (por exemplo: `id` como `Edm.String`, `title` como `Edm.String`, `description` como `Edm.String`, etc.).
4. Marque os campos que serão pesquisáveis, filtráveis, ordenáveis e facetable conforme necessário.
5. Salve o índice.

### 3. Carregamento dos Dados

1. Existem diferentes métodos para carregar os dados:
   - **Push Data**: Envie os dados diretamente através da API de indexação do serviço.
   - **Data Source**: Configure uma fonte de dados (por exemplo, Azure Blob Storage, SQL Database) e crie um **Indexer** para fazer o upload automático.
2. Para o método push:
   - Utilize ferramentas como o [Postman](https://www.postman.com/) ou bibliotecas SDK (disponíveis em C#, Python, etc.) para enviar um `POST` com os documentos para o endpoint do índice.
3. Verifique se os dados foram indexados com sucesso através do dashboard do serviço.

### 4. Configuração de Analisadores e Scoring Profiles

1. **Analisadores**: Configure analisadores linguísticos para melhorar a relevância dos resultados. Você pode utilizar os analisadores pré-configurados do Azure ou definir os seus próprios.
2. **Scoring Profiles**: Crie perfis de pontuação para ajustar o ranking dos resultados baseados em critérios como popularidade, data ou outras métricas específicas.
3. Atualize as configurações do índice conforme necessário e teste as mudanças.

### 5. Execução de Consultas

1. Utilize a API de pesquisa para enviar consultas ao índice. Exemplos de parâmetros incluem:
   - `search` para a consulta de texto livre.
   - `filter` para aplicar condições de filtro.
   - `orderby` para ordenar os resultados.
2. Experimente a consulta através do [portal do Azure Cognitive Search](https://portal.azure.com/) ou via código utilizando os SDKs.
3. Analise os resultados e ajuste as configurações do índice ou as consultas conforme necessário.

## Insights e Aprendizados

- **Escalabilidade e Performance**: A possibilidade de escalar horizontalmente o serviço é ideal para aplicações com grandes volumes de dados.
- **Flexibilidade na Indexação**: A capacidade de definir campos customizados e configurá-los para serem pesquisáveis, filtráveis e ordenáveis permite adaptar o serviço a diferentes cenários de uso.
- **Integração com Outras Ferramentas**: Aprendeu-se que o Azure Cognitive Search pode ser integrado facilmente com outros serviços da Azure, como Azure Functions, Logic Apps, e Power BI, potencializando a criação de soluções robustas e interativas.
- **Uso de Analisadores Linguísticos**: A importância dos analisadores para melhorar a relevância dos resultados foi um dos principais aprendizados, demonstrando como a escolha correta pode impactar a experiência do usuário final.

## Possibilidades de Integração

- **E-commerce**: Implementação de busca de produtos com filtros dinâmicos, facetas e sugestões de auto-complete.
- **Portais de Conteúdo**: Criação de experiências de busca para artigos, blogs e documentação.
- **Aplicações Empresariais**: Integração com sistemas internos para busca de documentos, contratos e informações corporativas.
- **Inteligência Artificial**: Uso em conjunto com serviços de IA da Azure, como o Azure Cognitive Services, para enriquecer os dados indexados com análise de sentimentos, extração de entidades e tradução automática.

## Considerações Finais

O processo de configuração do Azure Cognitive Search não só simplifica a criação de experiências de busca personalizadas, como também proporciona um aprendizado valioso sobre a manipulação e indexação de dados em larga escala. A flexibilidade e a capacidade de integração com outras ferramentas do ecossistema Azure são pontos-chave que podem impulsionar o desenvolvimento de aplicações inovadoras e eficientes.

---

