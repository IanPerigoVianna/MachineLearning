
# Nome do Projeto
Projeto de Análise exploratória de dados e Machine Learning com registros de plataforma de hospedagem da cidade de Nova Iorque.

## Descrição
Projeto de ciência de dados e Machine learning para o processo seletivo para a vaga de trainee.
Projeto feito entre o dia 15/02/2024 e 21/02/2024
Autor do projeto: Ian Lucas Périgo Vianna

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Profile-blue?style=flat-square&logo=linkedin&labelColor=blue)](https://www.linkedin.com/in/ianperigo)
[![E-mail](https://img.shields.io/badge/E--mail-Enviar%20E--mail-brightgreen?style=flat-square&logo=gmail&labelColor=brightgreen)](mailto:seu-ian.perigo.v@egmail.com)


## Pré-requisitos

Consultar requeriments.txt


## Instalação

1. Clone o repositório:

    ```bash
    git clone [https://github.com/seu-usuario/seu-projeto.git](https://github.com/IanPerigoVianna/MachineLearning.git)
    ```

2. Navegue até o diretório do projeto:

    ```bash
    cd seu-projeto
    ```

3. Instale as dependências:

    ```bash
    pip install -r requirements.txt
    ```

## Execução

1. Abra o notebook no Jupyter:

    ```bash
    jupyter notebook nome_do_notebook.ipynb
    ```

2. Execute as células conforme necessário.

## Carregando o Modelo Salvo

Se você deseja carregar um modelo treinado salvo com o `pickle`, siga estas etapas, pode copiar e colar nas células do seu notebook e executar:

1. Abra seu notebook.

2. Importe a biblioteca `pickle` e instale o tensorflow:

    ```python
    import pickle
    
    pip install tensorflow

    colab:
    ! pip install tensorflow
    ```

3. Carregue o modelo e o objeto de preparação de dados:

    ```python
    # Carregue o modelo
    with open('model.pkl', 'rb') as model_file:
        loaded_model = pickle.load(model_file)

    # Carregue o objeto de preparação de dados (se aplicável)
    with open('scaler.pkl', 'rb') as scaler_file:
        loaded_scaler = pickle.load(scaler_file)
    ```

4. Utilize o modelo carregado para fazer previsões:
   - Copie e cole esse código python no seu notebook
   - preencha os campos conforme indicado na documentação

    ```python
  ####### DOCUMENTAÇÃO DE INPUT DAS CHAVES PARA PREVISÃO DO PREÇO DO IMÓVEL ##########

- Room_type preencha 1  em room_type entire home/apt caso o aluguel seja do imóvel completo e 0 caso não seja.
- Room_type preencha 1  em room_type shared caso o aluguel seja de quarto compartilhado 0 caso não seja.
- Bairro_group preencha 1 para se o imóvel está localizado nesse bairro_group e 0 caso ele não esteja.
- Bairro preencha 1 caso o imóvel esteja neste bairro e 0 caso não esteja
- Disponibilidade 365_ preencha a quantidade de dias que o imóvel está disponível por ano
- Calculado host_listening_counts preencha com a quantidade de anuncios do imóvel
- Numero_de_reviews preencha com a quantidade de avaliações que o imóvel tem.

###### PREENCHA ABAIXO #######

entrada_zeros = {

    'room_type_Entire home/apt': 1,
    'bairro_group_Manhattan': 1,
    'bairro_Midtown': 1,
    'bairro_group_Queens': 0,
    'bairro_Bushwick': 0,
    'bairro_Chelsea': 0,
    'room_type_Shared room':0,
    'bairro_West Village': 0,
    "bairro_Hell's Kitchen": 0,
    'bairro_Bedford-Stuyvesant': 0,
    'disponibilidade_365': 10,
    'bairro_Tribeca': 0,
    'bairro_SoHo': 0,
    'bairro_group_Bronx': 0,
    'bairro_Upper West Side': 0,
    'bairro_East Village': 0,
    'bairro_Murray Hill': 0,
    'bairro_Greenwich Village': 0,
    'bairro_Washington Heights': 0,
    'bairro_Upper East Side': 0,
    'bairro_Harlem': 0,
    'bairro_Ridgewood': 0,
    'bairro_Flatbush': 0,
    'bairro_NoHo': 0,
    'bairro_Financial District': 0,
    'bairro_Crown Heights': 0,
    'bairro_Astoria': 0,
    'bairro_East Flatbush': 0,
    'bairro_Kips Bay': 0,
    'calculado_host_listings_count': 2,
    'bairro_Sunnyside': 0,
    'bairro_Flatiron District': 0,
    'bairro_Flushing': 0,
    'bairro_Gramercy': 0,
    'bairro_Elmhurst': 0,
    'bairro_Nolita': 0,
    'bairro_Borough Park': 0,
    'numero_de_reviews': 10,
    'bairro_Theater District': 0,
    'bairro_Prospect-Lefferts Gardens': 0,
    'bairro_Woodside': 0,
    'bairro_group_Staten Island': 0,
    'bairro_Jackson Heights': 0,
    'bairro_East New York': 0,
    'bairro_Inwood': 0,
    'bairro_Ditmars Steinway': 0
}

 - Sequência das Colunas
   
sequencia_colunas = ['room_type_Entire home/apt', 'bairro_group_Manhattan', 'bairro_Midtown', 'bairro_group_Queens', 'bairro_Bushwick', 'bairro_Chelsea', 'bairro_West Village', 'room_type_Shared room', "bairro_Hell's Kitchen", 'bairro_Bedford-Stuyvesant', 'disponibilidade_365', 'bairro_Tribeca', 'bairro_SoHo', 'bairro_group_Bronx', 'bairro_Upper West Side', 'bairro_East Village', 'bairro_Murray Hill', 'bairro_Greenwich Village', 'bairro_Washington Heights', 'bairro_Upper East Side', 'bairro_Harlem', 'bairro_Ridgewood', 'bairro_Flatbush', 'bairro_NoHo', 'bairro_Financial District', 'bairro_Crown Heights', 'bairro_Astoria', 'bairro_East Flatbush', 'bairro_Kips Bay', 'calculado_host_listings_count', 'bairro_Sunnyside', 'bairro_Flatiron District', 'bairro_Flushing', 'bairro_Gramercy', 'bairro_Elmhurst', 'bairro_Nolita', 'bairro_Borough Park', 'numero_de_reviews', 'bairro_Theater District', 'bairro_Prospect-Lefferts Gardens', 'bairro_Woodside', 'bairro_group_Staten Island', 'bairro_Jackson Heights', 'bairro_East New York', 'bairro_Inwood', 'bairro_Ditmars Steinway']

 
entrada_zeros_df = pd.DataFrame([entrada_zeros], columns=sequencia_colunas)


## Transforme as entradas, faça a predição com a entrada normalizada, faça o inversta a normalização de y para imprimir o valor do preço:

entrada_normalizada = scaler_X_carregado.transform(entrada_zeros_df)


previsao_preco_scaled = modelo_carregado.predict(entrada_normalizada)


previsao_preco = scaler_y_carregado.inverse_transform(previsao_preco_scaled)


print(f"Sugestão de preço original: ${previsao_preco[0][0]:.2f}")
    ```


### Dúvidas, contribuições e correções podem entrar em contato pelos canais disponibilizados acima.


