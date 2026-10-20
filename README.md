# 📊 Dashboard de Chamados de TI

Dashboard interativo de indicadores de service desk, feito em um **único arquivo HTML**, sem backend e sem etapa de build. Ele simula o acompanhamento de chamados de suporte de TI, com KPIs, filtros e gráficos que se atualizam em tempo real.

> ⚠️ Os dados usados são **fictícios**, criados apenas para demonstração.

## ✨ Funcionalidades

- **Filtro por categoria:** Rede, Hardware, Software, Acesso e Segurança (ou todas)
- **Filtro por período:** últimos 3 ou 6 meses
- **4 KPIs que recalculam a cada filtro:**
  - Total de chamados
  - SLA cumprido (%)
  - Tempo médio de atendimento (horas)
  - Chamados resolvidos no N1 (%)
- **Gráfico de linha:** evolução de chamados por mês
- **Gráfico de rosca:** distribuição de chamados por categoria
- **Tema claro/escuro automático**, de acordo com a preferência do sistema
- **Layout responsivo**, com boa visualização em celular e desktop

## 🛠️ Tecnologias

| Tecnologia | Uso |
|---|---|
| HTML5 | Estrutura da página |
| CSS3 | Layout (Grid/Flexbox), variáveis CSS e tema claro/escuro |
| JavaScript (ES6+) | Lógica dos filtros e cálculo dos indicadores |
| [Chart.js 4.4.1](https://www.chartjs.org/) | Gráficos de linha e rosca (carregado via CDN) |

## 🚀 Como executar

Não é necessário instalar nada.

1. Clone o repositório:
   ```bash
   git clone https://github.com/SEU-USUARIO/NOME-DO-REPOSITORIO.git
   ```
2. Abra o arquivo `dashboard-chamados.html` em qualquer navegador moderno.

> É necessária conexão com a internet para carregar o Chart.js pela CDN.

### Publicar com GitHub Pages (opcional)

1. Renomeie o arquivo para `index.html`.
2. No repositório, vá em **Settings → Pages**.
3. Em **Source**, escolha a branch `main` e a pasta `/ (root)`.
4. Acesse o link gerado pelo GitHub.

## 📁 Estrutura

```
.
├── dashboard-chamados.html   # Aplicação completa (HTML + CSS + JS)
└── README.md
```

## 🧮 Como os indicadores são calculados

Os dados ficam em arrays no próprio script, com 6 meses (Abr a Set) e 5 categorias.

- **Chamados:** soma dos chamados dos meses selecionados, na categoria escolhida ou em todas.
- **SLA, tempo médio e resolvidos no N1:** média simples dos meses do período selecionado.
- **Gráfico por categoria:** soma por categoria no período, sem aplicar o filtro de categoria, para manter a comparação entre elas.

## ⚙️ Personalização

Para usar seus próprios dados, edite as constantes no início do `<script>`:

```js
const meses = ["Abr","Mai","Jun","Jul","Ago","Set"];
const cats  = ["Rede","Hardware","Software","Acesso","Segurança"];
const base  = [ /* chamados por categoria, por mês */ ];
const sla   = [ /* % de SLA cumprido por mês */ ];
const tmp   = [ /* tempo médio (h) por mês */ ];
const n1    = [ /* % resolvidos no N1 por mês */ ];
```

As cores do tema ficam nas variáveis CSS em `:root` (`--bg`, `--card`, `--ac`, etc.).

## 🗺️ Próximos passos

- [ ] Carregar dados a partir de um arquivo CSV/JSON
- [ ] Integrar com uma fonte real (API do Jira, banco MySQL/SQL Server)
- [ ] Adicionar filtro por prioridade e por analista
- [ ] Exportar os indicadores para CSV/PDF
- [ ] Incluir gráfico de SLA por mês

## 👩‍💻 Autor

**Walace Fonseca**
Profissional de TI | Suporte, infraestrutura e dados

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/walace-batista-/)

## 📄 Licença

Este projeto está sob a licença MIT. Sinta-se à vontade para usar, estudar e adaptar.
