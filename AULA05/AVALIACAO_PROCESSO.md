Cenário:

1. Nome do Processo
# Conciliação Bancária Diária via ERP
2. É viável para RPA? (Sim / Não)
  Sim
3. Justificativa baseada nos 4 critérios essenciais (Repetitividade, Regras de Negócio, Tipo de Dados, Volume).
- Repetitividade: Alta. O processo é executado diariamente, seguindo sempre o mesmo ciclo de abrir o banco, extrair o arquivo, abrir o ERP e cruzar as informações.
- Regras de Negócio: Fixas e bem definidas. A tomada de decisão do robô é baseada em critérios objetivos e lógicos (validação exata de CNPJ e valor), sem necessidade de julgamento humano ou análise subjetiva.
- Tipo de Dados: Estruturados. Tanto o arquivo do extrato bancário (.csv) quanto os dados armazenados no sistema ERP possuem campos delimitados, previsíveis e de fácil leitura para um software (tabelas, colunas de texto e números).
- Volume: Normalmente médio a alto. Por ser uma atividade diária, o acúmulo de transações justifica o investimento no robô, eliminando o esforço manual de conferência linha por linha.
4. Mapeamento Passo a Passo das Ações do Robô
- 1 Acessar o Internet Banking: O robô abre o navegador, acessa o portal do banco e realiza o login (usando credenciais seguras ou certificado digital).
- 2 Baixar o Extrato: Navega até a área de extratos, seleciona o período (D-1 ou dia atual) e faz o download do arquivo no formato .csv.
- 3 Ler e Tratar o Arquivo: O robô lê o .csv internamente, padronizando os formatos de data, valores e CNPJ (removendo pontos, barras e traços).
- 4 Acessar o ERP: Abre o sistema ERP da empresa (via Web, Desktop ou SAP) e realiza a autenticação de usuário.
- 5 Extrair Dados do ERP: Acessa o módulo financeiro / contas a receber e gera o relatório de baixas ou lançamentos do dia correspondente.
- 6 Executar o Cruzamento (Conciliação):
     Para cada linha do extrato bancário, o robô busca uma linha correspondente no ERP onde o CNPJ e o Valor sejam idênticos.
- 7 Efetuar a Baixa/Conciliação no Sistema:
     Se houver correspondência: O robô marca o lançamento como "Conciliado" no ERP.
     Se NÃO houver correspondência: O robô pula a linha e a insere em um relatório de exceções.
- 8 Enviar Relatório de Fechamento: O robô encerra as sessões dos sistemas e envia um e-mail para a equipe financeira com o resumo da execução (ex: "50 transações conciliadas com sucesso, 3 pendências para análise manual" anexando a lista de exceções).