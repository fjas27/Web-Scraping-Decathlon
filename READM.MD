# 🛰️ TrekkingRadar API — Inteligência de Dados e Automação

**TrekkingRadar API** é uma aplicação backend desenvolvida em **Python**, projetada para coletar, tratar e disponibilizar informações atualizadas sobre produtos, promoções e dados de múltiplas fontes online.  
Com foco em performance, segurança e escalabilidade, o projeto oferece endpoints otimizados para uso em aplicações web, integrações ou análises de dados.

---

## 🚀 Principais Funcionalidades

- 🔎 **Raspagem de dados inteligente** (web scraping) Loja Decathlon.
- 🧠 **Tratamento e padronização automática** dos dados coletados.
- 💾 **Armazenamento em banco de dados PostgreSQL** para consultas rápidas.
- 🌐 **API RESTful** desenvolvida em **FastAPI**.
- ⚙️ **Atualização automática** dos dados (diariamente ou sob demanda).
- 🧩 **Filtros personalizados** por loja, preço, categoria e marca.
- 🧾 **Retorno no formato JSON**, ideal para integração com outros sistemas.

---

## 📦 Exemplo de Retorno (JSON)

```json
{
  "count": 50,
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


🧩 Endpoints Disponíveis
Método	Rota	Descrição
GET	/produtos	Retorna a lista de produtos disponíveis
GET	/produtos?limit=10	Retorna apenas os primeiros 10 produtos
GET	/produtos?loja=Decathlon	Filtra produtos por loja
GET	/status	Verifica o status da API

⚙️ Como Funciona

O backend coleta dados diretamente das fontes originais, realiza o tratamento e armazena as informações em um banco PostgreSQL.
A API serve esses dados sob demanda, garantindo alta disponibilidade e baixa latência para o cliente final.


💡 Possíveis Aplicações

Comparadores de preços
Bots de promoções em WhatsApp ou Telegram
Dashboards de inteligência de mercado
Ferramentas de monitoramento de estoque ou descontos
Integrações com plataformas de e-commerce

🧠 Tecnologias Utilizadas
Python 3.11+
FastAPI
PostgreSQL
Psycopg2
Dotenv
Requests / BeautifulSoup
Uvicorn

🔒 Acesso e Licenciamento

Este repositório contém apenas a documentação pública do projeto.
O código-fonte da API é privado e acessível somente mediante solicitação.
🚫 Código e endpoints privados — acesso apenas para parceiros autorizados.
Para solicitar acesso comercial, entre em contato:

📧 fernando.fjas@gmail.com