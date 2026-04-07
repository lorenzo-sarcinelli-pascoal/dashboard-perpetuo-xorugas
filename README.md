# dashboard-perpetuo-xorugas

Use esta pasta como **raiz de um repositório Git** separado (ex.: `git init` aqui e push para `github.com/.../dashboard-perpetuo-xorugas`).

Cópia do dashboard perpétuo com **Google Sheets** (API Key + Spreadsheet ID + nomes das abas), alinhada ao `dashboard-perpetuo.html` do repositório THE (pasta `dashboards/perpetuo/`). Se este for um clone isolado, ignore o link relativo no histórico do mono-repo.

## Conteúdo

| Caminho | Descrição |
|---------|-----------|
| `docs/index.html` | Dashboard (entrada para GitHub Pages) |
| `docs/manifest.webmanifest` | PWA |
| `docs/icons/` | Favicon e ícones THE |

Configuração fica no **localStorage** do navegador (`the_perpetuo_xorugas_dashboard_config`), separada do dashboard “Ju”.

## Google Sheets

1. No [Google Cloud Console](https://console.cloud.google.com/), crie um projeto (ou use um existente), ative a **Google Sheets API** e crie uma **API key** (restrita à Sheets, se possível).
2. Compartilhe a planilha (ou torne-a legível conforme sua política) para que a API key possa ler os dados.
3. No dashboard, preencha **API Key**, **Spreadsheet ID** (trecho da URL entre `/d/` e `/edit`), **nome exato da aba de vendas** e **nome exato da aba Meta**.
4. **Salvar e carregar**.

As abas devem ter **cabeçalho na primeira linha** com as colunas esperadas pelo motor do perpétuo (export Hubla + `metaads_daily`).

## GitHub Pages

1. Envie este diretório para um repositório; branch padrão `main`.
2. **Settings → Pages → Build and deployment**: escolha **GitHub Actions**.
3. O workflow [`.github/workflows/pages.yml`](.github/workflows/pages.yml) publica a pasta `docs/` a cada push em `main`.
4. Acesse o site em `https://lorenzo-sarcinelli-pascoal.github.io/dashboard-perpetuo-xorugas/` (após o workflow “Deploy GitHub Pages” concluir com sucesso).

Teste local: na pasta `docs/`, `python3 -m http.server 8080` e abra `http://localhost:8080/index.html`.

## Ofertas

O mapa padrão de categorias de oferta está vazio; após o primeiro carregamento, classifique cada `offer_name` no painel **Categorização de ofertas**.

## Marca

Ícones: ver `docs/icons/README.md` (Tracking HighEnd).
