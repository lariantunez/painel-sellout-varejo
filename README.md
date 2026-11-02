# Painel Vitta - Dashboard MongoDB

**[Ler o estudo de caso](https://lariantunez.github.io/painel-sellout-varejo/)** · **[Abrir a demo do painel](https://lariantunez.github.io/painel-sellout-varejo/painel/)**

![Painel Vitta com dados fictícios](assets/painel-vendas.jpg)

> **Versão de portfólio.** O painel original roda em produção, com dados reais do cliente. Esta versão usa o mesmo código, com dados e nomes fictícios.

Dashboard web desenvolvido para substituir análises manuais em planilhas dinâmicas de Excel por uma visão centralizada de vendas, estoque e performance comercial do cliente Vitta.

O painel consolida arquivos operacionais, aplica regras de tratamento e disponibiliza indicadores para leitura executiva, filtros dinâmicos e acompanhamento por período, filial, categoria, família e produto.

## Objetivo

Automatizar uma rotina que antes dependia de planilhas dinâmicas, reduzindo retrabalho e dando acesso rápido aos principais números acompanhados pela diretoria comercial.

## Principais recursos

- Importação de dados brutos de sell out em CSV/XLSX.
- Importação de tabelas De/Para de lojas e categorias.
- Dashboard com KPIs de vendas, valor vendido, estoque e evolução diária.
- Filtros por período, filial, categoria, família e produto.
- Agregações otimizadas no MongoDB para consultas mais rápidas.
- Cache controlado no backend para reduzir processamento repetido.
- Área administrativa para usuários, admins, templates e logs de importação.
- Redefinição de senha por e-mail.
- Modo somente leitura para ambientes de demonstração.

## Tecnologias

- Node.js
- Express
- MongoDB Atlas
- HTML, CSS e JavaScript puro
- Multer para upload de arquivos
- XLSX e csv-parser para leitura de planilhas
- Nodemailer para reset de senha
- Docker para deploy

## Estrutura

```text
backend/src/server.js      API, autenticacao, importacoes e consultas MongoDB
frontend/index.html        Interface principal do dashboard
frontend/reset-senha.html  Fluxo de redefinicao de senha
docs/                      Manuais de uso e manutencao
Dockerfile                 Build da aplicacao
```

## Variáveis de ambiente

Crie um arquivo `.env` local com as variáveis abaixo. O `.env` não deve ser publicado.

```env
PORT=3000
DB_NAME=vitta_dashboard
MONGODB_URI=mongodb+srv://USUARIO:SENHA@HOST/?appName=Cluster0
ADMIN_USER=usuario-admin
ADMIN_PASSWORD=senha-admin
ADMIN_EMAIL=email@dominio.com
EMAIL_USER=
EMAIL_PASS=
READ_ONLY=false
```

## Como executar

```bash
npm install
npm start
```

A aplicação sobe o backend Express e serve o frontend estático.

## Demo estática

A página inicial do GitHub Pages (`index.html`) é o estudo de caso do projeto. A demo do painel real fica em `painel/index.html` (cópia também em `docs/index.html`), criada para GitHub Pages e portfólio. Ela usa dados fictícios e uma API simulada no navegador, sem depender de MongoDB, backend ou variáveis de ambiente.

## Cuidados de portfólio

Este repositório foi preparado para portfólio. Bases reais, arquivos `.env`, uploads, CSVs e XLSX operacionais ficam fora do Git por segurança e confidencialidade.

## Status

Projeto funcional e publicado originalmente em ambiente de produção, com rotinas de importação, tratamento, consulta e administração.

---

**🇺🇸 English:** a sell-out and inventory dashboard that replaced manual Excel pivot tables. Raw sales files (CSV/XLSX) are imported with validation and store/category mapping, MongoDB aggregations use pre-computed fields and a controlled cache, and the dashboard offers KPIs and filters by period, store, category, family and product. It also has user management, import logs and password reset by e-mail. Stack: Node.js, Express, MongoDB Atlas, plain JavaScript, Docker. Portfolio version with fictional data; the original runs in production.
