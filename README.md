# Ponderada ETL API OpenWeather
Autoestudo Semana 02: Criação de uma ETL em flask com teste de integração que leia da API OpenWeather, manipule os dados em uma tabela nova guardando as informações em 4 colunas: Data da Ingestão, Tipo, Valores, Uso


# Etapas de Preparação
Cadastro na OpenWeather API: O primeiro passo consistiu na criação de uma conta em [https://home.openweathermap.org/], onde obtive minha chave de API exclusiva: d43416cfcf2eac622f0aa8bff037693f.

**Preparação do Ambiente de Execução**: Após a obtenção da minha key, configurei o ambiente de execução. Já possuindo o Python instalado, instalei as bibliotecas necessárias para o desenvolvimento do autoestudo:
pip install Flask
pip install pandas
pip install pytest
pip install sqlalchemy 

Desenvolvimento no **VsCode**: Em seguida, criei um arquivo chamado atv.py no VsCode. Neste arquivo, desenvolvi as principais funções necessárias para extrair dados diretamente da API OpenWeather e realizar o processo completo de ETL, estabelecendo com sucesso a conexão e armazenamento dos dados.


# Configuração do Flask:

A configuração do Flask envolve essa etapa:
app = Flask(__name__)
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///weather_data.db'
app.config['SQLALCHEMY_TRACK_MODIFICATIONS'] = False
db = SQLAlchemy(app)

# ETL (Extract, Transform, Load):

1. Extração (Extract): Uma função utilizará a chave da da API OpenWeather fornecida para conseguir fazer a requisição na AAPI e obter os dados climáticos das 10 cidades selecionadas.
2. Transformação (Transform): A função vai receber os dados brutos que foram coletados da API e vai trannformar as informações importantes.
3. Carregamento (Load): A função vai inserir os dados na tabela criada com as colunas adequadas.

# Armazenamento dos Dados:

Como exigido pleo autoestudo, os dados foram armazenados em uma tabela com as informações de: id, data da ingestão, o tipo, os valores, e o uso. Dessa forma, garantindo com que fosse possivel realizar uma análise dos dados climáticos que tenham uma interação direta com o banco de dados. Isso tudo, com a ajuda do flask 
