# API de Produtos Decathlon

Uma API construída em **FastAPI** que permite consultar produtos da Decathlon, filtrando por marca ou categoria. Os dados são coletados via web crawling usando Python e armazenados em um banco de dados PostgreSQL. Também há suporte para atualizar preços automaticamente e manter histórico de alterações.

---

## 📁 Estrutura do projeto

TrekkingRadar/
├── api.py # Arquivo principal da API
├── atualizador_banco.py # Atualiza produtos no banco e mantém histórico de preços
├── decathlon_spider.py # Raspagem (crawler) dos produtos Decathlon
├── main.py # Testes ou inicialização (opcional)
├── requirements.txt # Dependências do projeto
├── .env # Configurações do banco de dados

## ⚙️ Requisitos

- Python 3.10+
- PostgreSQL
- Dependências Python (instalar via pip):

```bash
pip install -r requirements.txt

O arquivo .env deve conter:
DATABASE_URL=postgresql://usuario:senha@host:porta/banco

Ative o ambiente virtual (exemplo no Windows PowerShell):

.\venv\Scripts\Activate


Rode a API com uvicorn:
uvicorn api:app --reload --host 0.0.0.0 --port 8000


Acesse a documentação automática (Swagger UI):
http://127.0.0.1:8000/docs


## 📝 Endpoints
GET /produtos

Retorna os produtos da Decathlon.

Parâmetros opcionais:

Parâmetro	Tipo	Descrição
limit	int	Limite de produtos retornados (default: 50)
brand	str	Filtra produtos por marca
category	str	Filtra produtos por categoria/sub-departamento

Exemplo de requisição:

GET /produtos?limit=10&brand=Quechua

{
  "count": 10,
  "results": [
    {
      "product_id": "124720",
      "name": "Jaqueta Fleece Infantil de Trilha NH500 Quechua",
      "brand": "QUECHUA",
      "sport": "Ski e Snowboard",
      "list_price": 129.99,
      "display_price": 99.99,
      "sub_department": "/Roupas/",
      "product_link": "https://www.decathlon.com.br/jaqueta-fleece-infantil-de-trilha-nh500-quechua/p"
    }
  ]
}


##Atualização de produtos

O arquivo decathlon_spider.py coleta produtos das categorias:

Trekking

Camping

Escalada e Alpinismo

O atualizador_banco.py faz o upsert no banco e mantém o histórico de preços via trigger.

from decathlon_spider import coletar_produtos
from atualizador_banco import atualizar_produtos

produtos = coletar_produtos()
atualizar_produtos(produtos)


⚠️ Observações

O endpoint /produtos retorna apenas informações básicas: ID, nome, marca, categoria e preços.
Mais informações podem ser coletadas pelo crawler, mas é recomendado limitar o que a API expõe para melhorar desempenho.
É possível configurar rotinas automáticas (cron jobs) para atualizar os produtos diariamente ou conforme necessidade.


🔧 Tecnologias usadas

Python 3.10+
FastAPI para a API
Requests para web scraping
SQLAlchemy para integração com PostgreSQL
PostgreSQL como banco de dados




Contato para solicitar acesso 
fernando.fjas@gmail.com


