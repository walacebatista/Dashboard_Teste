<div align="center">

# 📊 Dashboard de Chamados de TI

**Dashboard interativo de indicadores de service desk, em um único arquivo HTML.**
Sem backend, sem build e sem instalação.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?style=for-the-badge&logo=chartdotjs&logoColor=white)

![Status](https://img.shields.io/badge/status-conclu%C3%ADdo-brightgreen?style=flat-square)
![Licença](https://img.shields.io/badge/licen%C3%A7a-MIT-blue?style=flat-square)
![Dados](https://img.shields.io/badge/dados-fict%C3%ADcios-orange?style=flat-square)

</div>

---

## 📑 Sumário

- [Sobre o projeto](#-sobre-o-projeto)
- [Prévia](#-prévia)
- [Funcionalidades](#-funcionalidades)
- [Tecnologias](#-tecnologias)
- [Como executar](#-como-executar)
- [Estrutura](#-estrutura)
- [Cálculo dos indicadores](#-cálculo-dos-indicadores)
- [Personalização](#️-personalização)
- [Próximos passos](#️-próximos-passos)
- [Autora](#-autora)
- [Licença](#-licença)

## 💡 Sobre o projeto

Este projeto simula o acompanhamento de chamados de suporte de TI (N1/N2), reunindo em uma única tela os principais indicadores de um service desk: volume de chamados, cumprimento de SLA, tempo médio de atendimento e taxa de resolução no primeiro nível.

Os filtros de **categoria** e **período** recalculam os KPIs e os gráficos em tempo real.

> ⚠️ Os dados são **fictícios**, criados apenas para demonstração.

## 🖼️ Prévia

<!-- Salve um print do dashboard em docs/preview.png e ele aparecerá aqui -->
<p align="center">
  <img src="docs/preview.png" alt="Prévia do Dashboard de Chamados de TI" width="850">
</p>

## ✨ Funcionalidades

| | Recurso | Descrição |
|---|---|---|
| 🔎 | Filtro por categoria | Rede, Hardware, Software, Acesso, Segurança ou todas |
| 📅 | Filtro por período | Últimos 3 ou 6 meses |
| 📌 | 4 KPIs dinâmicos | Total de chamados, SLA cumprido, tempo médio (h) e resolvidos no N1 |
| 📈 | Gráfico de linha | Evolução mensal de chamados |
| 🍩 | Gráfico de rosca | Distribuição por categoria |
| 🌗 | Tema automático | Claro ou escuro, conforme o sistema do usuário |
| 📱 | Responsivo | Funciona bem em celular e desktop |

## 🛠️ Tecnologias

<p align="center">
  <img src="https://skillicons.dev/icons?i=html,css,js,git,github&theme=dark" alt="Tecnologias utilizadas" />
</p>

| Tecnologia | Uso no projeto |
|---|---|
| **HTML5** | Estrutura da página |
| **CSS3** | Layout com Grid/Flexbox, variáveis CSS e tema claro/escuro |
| **JavaScript (ES6+)** | Lógica dos filtros e cálculo dos indicadores |
| **[Chart.js 4.4.1](https://www.chartjs.org/)** | Gráficos de linha e rosca, carregado via CDN |
| **Git/GitHub** | Versionamento e hospedagem do código |

## 🚀 Como executar

Não é necessário instalar nada.

```bash
# 1. Clone o repositório
git clone https://github.com/SEU-USUARIO/NOME-DO-REPOSITORIO.git

# 2. Entre na pasta
cd NOME-DO-REPOSITORIO
```

Depois, abra o arquivo `dashboard-chamados.html` em qualquer navegador moderno.

> 🌐 É necessária conexão com a internet para carregar o Chart.js pela CDN.

### Publicar online com GitHub Pages (opcional)

1. Renomeie o arquivo para `index.html`.
2. No repositório, acesse **Settings → Pages**.
3. Em **Source**, escolha a branch `main` e a pasta `/ (root)`.
4. Acesse o link gerado pelo GitHub.

## 📁 Estrutura

```
.
├── dashboard-chamados.html   # Aplicação completa (HTML + CSS + JS)
├── docs/
│   └── preview.png           # Print do dashboard usado neste README
└── README.md
```

## 🧮 Cálculo dos indicadores

Os dados ficam em arrays no próprio script, com 6 meses (Abr a Set) e 5 categorias.

| Indicador | Cálculo |
|---|---|
| **Chamados** | Soma dos meses selecionados, na categoria escolhida ou em todas |
| **SLA cumprido** | Média simples dos meses do período |
| **Tempo médio (h)** | Média simples dos meses do período |
| **Resolvidos no N1** | Média simples dos meses do período |
| **Gráfico por categoria** | Soma por categoria no período, sem aplicar o filtro de categoria, para manter a comparação |

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

- [ ] Carregar dados a partir de arquivo CSV/JSON
- [ ] Integrar com fonte real (API do Jira, MySQL ou SQL Server)
- [ ] Adicionar filtros por prioridade e por analista
- [ ] Exportar indicadores para CSV/PDF
- [ ] Incluir gráfico de SLA por mês

## 👩‍💻 Autor

**Walace Fonseca**
Profissional de TI | Suporte, infraestrutura e dados

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/walace-batista-/)

## 📄 Licença

Este projeto está sob a licença MIT. Sinta-se à vontade para usar, estudar e adaptar.

---

<div align="center">
⭐ Se este projeto te ajudou, deixe uma estrela no repositório!
</div>
