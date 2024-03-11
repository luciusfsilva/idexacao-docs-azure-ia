##  Azure IA - search

## Configuração da Pesquisa

    1 - Criar um recurso no Azure IA Service
        1.1 - Seguir os passos de criação do recurso
    2 - Criar a conta de armazenamento
        2.1 - Inserindo: Assinatura, Grupo de recursos, Nome da conta de armazenamento,
              Localização, Redundância
    3 - Importar os dados
        Obs.: Pode ser usado os docs disponíveis na documentação do Azure
        3.1 - Escolher o container
        3.2 - Clicar em Upload
        3.3 - Selecionar os docs e arrastar até a tela
    4 - Criar indexação de documentos
        4.1 -  Na página Visão geral , selecione Importar dados 
        4.2 - Conectar-se aos seus dados , na lista Fonte de Dados , selecione Azure
              Blob Storage
        4.3 - Preencher as informações: Fonte de dados, Nome da fonte de dados, 
              Dados a extrair, Modo de análise, Cadeia de conexão, Autenticação de
              identidade gerenciada, Nome do contêiner, Pasta Blob, Descrição
        4.4 - Selecione Próximo: Adicionar habilidades cognitivas (opcional)
        4.5 - Na secção Anexar Serviços Cognitivos
        4.6 - Na seção Adicionar enriquecimentos
              4.6.1 - Altere o nome da qualificação
              4.6.2 - Marque a caixa de seleção Habilitar OCR e mesclar todo o texto no 
                      campo merged_content
        4.7 - O campo Dados de origem esteja configurado como "merged_content"
        4.8 - Alterar o nível de granularidade de enriquecimento para Páginas 
              (blocos de 5.000 caracteres)
        4.9 - Salvar enriquecimentos em um armazenamento de conhecimento
              4.9.1 - Projeções de imagem, Documentos, Páginas, Frases chave
                      Entidades, Detalhes da imagem, Referências de imagem
        4.10 - Selecionar projeções de blob do Azure: Documento
        4.11 - Personalizar índice de destino . Altere o nome do índice
        4.12 - Certifique-se de que a chave esteja configurada como metadata_storage_path 
               Deixe o nome do sugeridor em branco e o modo de pesquisa preenchido   
               automaticamente.
        4.12 - Selecione filtrável para todos os campos que já estão selecionados.
        Selecione Próximo: Criar um indexador .
        4.13 - Altere o nome do indexador para coffee-indexer .
        4.14 - Deixe a programação definida como Once .
        4.15 - Expanda as opções avançadas . Certifique-se de que a opção Base-64 Encode
               Keys esteja selecionada, pois as chaves de codificação podem tornar o 
               índice mais eficiente.

        4.16 - Selecione Enviar para criar a fonte de dados, o conjunto de habilidades, 
               o índice e o indexador. O indexador é executado automaticamente e executa
               o pipeline de indexação, que:
               Extrai os campos de metadados do documento e o conteúdo da fonte de dados.
               Executa o conjunto de habilidades cognitivas para gerar campos mais
               enriquecidos.
               Mapeia os campos extraídos para o índice.
        4.17 - Volte à página de recursos do Azure AI Search. No painel esquerdo, em   
               Gerenciamento de pesquisa , selecione Indexadores . Selecione o indexador 
               de café recém-criado . Espere um minuto e selecione ↻ Atualize até que o 
               Status indique sucesso.
    5 - Consultando o Índice
        5.1 - Na página Visão geral do serviço de pesquisa , selecione Explorador de
              pesquisa na parte superior da tela
        5.2 - Posso executar uma pesquisa por exemplo por: "location", "sentiment"

        fonte: https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html

        ## Insight

        Vejo a possibilidade de integração com sistemas para busca de documentos utilizando um framework como spring boot e resgatar uma análise documental de gastos ou de referenda aceitação de serviços.
