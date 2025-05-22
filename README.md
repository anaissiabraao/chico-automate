🚚 Automação de Cálculo de Frete e Geração de Relatórios
Este projeto é um backend Flask para cálculo de custos de transporte, geração de relatórios em PDF e consulta de tabelas de frete, utilizando dados de municípios, estados, rotas e uma base de agentes. Ele foi desenvolvido para facilitar a simulação de fretes dedicados e fracionados, além de fornecer informações detalhadas sobre rotas e custos.

Funcionalidades
Cálculo de Frete Dedicado:
Estima custos por tipo de veículo com base na distância entre origem e destino, utilizando tabelas de custos e APIs de roteamento.

Cálculo de Frete Fracionado:
Calcula o valor do frete fracionado consultando diretamente uma base de agentes carregada em memória.

Consulta de Estados e Municípios:
Endpoints para listar estados e cidades disponíveis para cálculo de frete.

Geração de Relatórios em PDF:
Relatórios detalhados com informações de rota, custos, consumo estimado, emissão de CO₂ e observações.

Histórico de Pesquisas:
Armazena e permite consultar as últimas simulações realizadas.

Pré-requisitos
Python 3.8+

pip

(Opcional) virtualenv

Instalação
Clone o repositório:

bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
Instale as dependências:

bash
pip install -r requirements.txt
Adicione os arquivos de dados:

Coloque o arquivo Base_Agentes.txt na raiz do projeto.

(Opcional) Outros arquivos de dados podem ser adicionados conforme necessidade.

Como usar
Inicie o servidor Flask:

bash
python improved_chico_automate_fpdf.py
Acesse os endpoints:

POST /calcular_frete_dedicado
Calcula o frete dedicado entre duas cidades.

POST /calcular_frete_fracionado
Calcula o frete fracionado utilizando a base de agentes.

GET /estados
Lista os estados disponíveis.

GET /municipios?uf=XX
Lista os municípios de um estado.

GET /historico
Consulta o histórico de pesquisas recentes.

POST /relatorio_pdf
Gera um relatório detalhado em PDF.

Exemplo de requisição para cálculo de frete fracionado:
.json
{
  "uf": "SP",
  "cidade": "Ribeirão Preto",
  "peso": 120
}
Estrutura dos Dados
Base_Agentes.txt:
Arquivo tabulado contendo informações dos agentes de transporte, faixas de peso, valores mínimos, zonas, prazos, etc.

Personalização
Para adicionar ou atualizar agentes, edite o arquivo Base_Agentes.txt.

Para alterar as regras de cálculo, edite as funções no script principal.

Contribuição
Pull requests são bem-vindos! Para mudanças maiores, por favor abra uma issue primeiro para discutir o que você gostaria de modificar.
