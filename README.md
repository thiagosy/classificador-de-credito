# Projeto 01 - Concessão de Cartões de Crédito

Este projeto consiste em desenvolver um sistema de análise de crédito para concessão de cartões de crédito. Utilizando técnicas de aprendizado de máquina, o objetivo é construir um modelo preditivo para identificar o risco de inadimplência de clientes.

## Descrição

Este notebook é semelhante ao visto em vídeo, mas contém células azuis como esta, que trazem instruções para a sua atividade. Após realizar as tarefas indicadas, você vai fazer o upload do seu arquivo no GitHub e enviar o link para a EBAC, ou alternativamente, fazer o upload do arquivo na plataforma da EBAC. Recomendamos o GitHub, pois assim você já vai montando o seu portfólio.

## Etapa 1 CRISP-DM: Entendimento do Negócio

Como primeira etapa do CRISP-DM, vamos entender do que se trata o negócio e quais os objetivos.

Este é um problema de concessão de cartões de crédito, publicado no Kaggle, uma plataforma que promove desafios de ciência de dados, oferecendo prêmios em dinheiro para os melhores colocados. O link original está [aqui](https://www.kaggle.com/).

Essa é uma base de proponentes de cartão de crédito, nosso objetivo é construir um modelo preditivo para identificar o risco de inadimplência (tipicamente definida pela ocorrência de um atraso maior ou igual a 90 dias em um horizonte de 12 meses) através de variáveis que podem ser observadas na data da avaliação do crédito (tipicamente quando o cliente solicita o cartão).

### Atividades do CRISP-DM:

- **Objetivos do Negócio**: O objetivo aqui é que o modelo sirva o mutuário (o cliente) para que avalie suas próprias decisões, e não a instituição de crédito.
- **Objetivos da Modelagem**: Desenvolver o melhor modelo preditivo de modo a auxiliar o mutuário a tomar suas próprias decisões referentes a crédito.

Nessa etapa também se avalia a situação da empresa/segmento/assunto de modo a se entender o tamanho do público, relevância, problemas presentes e todos os detalhes do processo gerador do fenômeno em questão, e portanto dos dados. Também é nessa etapa que se constrói um planejamento do projeto.

## Etapa 2 CRISP-DM: Entendimento dos Dados

A segunda etapa é o entendimento dos dados. Foram fornecidas 15 variáveis mais a variável resposta (em negrito na tabela). O significado de cada uma dessas variáveis se encontra na tabela abaixo.

### Dicionário de Dados

Os dados estão dispostos em uma tabela com uma linha para cada cliente, e uma coluna para cada variável armazenando as características desses clientes. 

| Nome da Variável          | Descrição                                                | Tipo   |
|---------------------------|----------------------------------------------------------|--------|
| sexo                      | M = 'Masculino'; F = 'Feminino'                           | M/F    |
| posse_de_veiculo          | Y = 'possui'; N = 'não possui'                            | Y/N    |
| posse_de_imovel           | Y = 'possui'; N = 'não possui'                            | Y/N    |
| qtd_filhos                | Quantidade de filhos                                      | inteiro|
| tipo_renda                | Tipo de renda (ex: assalariado, autônomo etc)             | texto  |
| educacao                  | Nível de educação (ex: secundário, superior etc)          | texto  |
| estado_civil              | Estado civil (ex: solteiro, casado etc)                   | texto  |
| tipo_residencia           | Tipo de residência (ex: casa/apartamento, com os pais etc)| texto  |
| idade                     | Idade em anos                                             | inteiro|
| tempo_de_emprego          | Tempo de emprego em anos                                  | inteiro|
| possui_celular            | Indica se possui celular (1 = sim, 0 = não)               | binária|
| possui_fone_comercial     | Indica se possui telefone comercial (1 = sim, 0 = não)    | binária|
| possui_fone               | Indica se possui telefone (1 = sim, 0 = não)              | binária|
| possui_email              | Indica se possui e-mail (1 = sim, 0 = não)                | binária|
| qt_pessoas_residencia     | Quantidade de pessoas na residência                       | inteiro|
| **mau**                   | Indicadora de mau pagador (True = mau, False = bom)       | binária|

## Estrutura do Projeto

- `data/`: Contém os conjuntos de dados utilizados no projeto.
- `notebooks/`: Notebooks Jupyter com análises e experimentos.
- `src/`: Código-fonte do projeto.
  - `preprocessing/`: Scripts para pré-processamento de dados.
  - `models/`: Scripts para construção e avaliação de modelos.
  - `utils/`: Funções utilitárias.
- `reports/`: Relatórios gerados durante o projeto.
- `README.md`: Documentação do projeto.

## Instalação

1. Clone o repositório:
    ```bash
    git clone https://github.com/thiagosy/projeto-analise-credito.git
    cd projeto-analise-credito
    ```

2. Crie um ambiente virtual e ative-o:
    ```bash
    python -m venv venv
    source venv/bin/activate  # No Windows, use `venv\Scripts\activate`
    ```

3. Instale as dependências:
    ```bash
    pip install -r requirements.txt
    ```

## Uso

1. **Pré-processamento de Dados**:
    Execute o script de pré-processamento para preparar os dados:
    ```bash
    python src/preprocessing/preprocess_data.py
    ```

2. **Treinamento de Modelos**:
    Treine os modelos utilizando o script de treinamento:
    ```bash
    python src/models/train_model.py
    ```

3. **Avaliação de Modelos**:
    Avalie a performance dos modelos:
    ```bash
    python src/models/evaluate_model.py
    ```

4. **Deploy do Modelo**:
    Implemente o modelo em produção:
    ```bash
    python src/deploy/deploy_model.py
    ```

## Contribuição

Contribuições são bem-vindas! Sinta-se à vontade para abrir um pull request ou relatar problemas no repositório.

## Licença

Este projeto está licenciado sob a Licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.
