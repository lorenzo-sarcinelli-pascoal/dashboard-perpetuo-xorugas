# Publicar em https://lorenzo-sarcinelli-pascoal.github.io/dashboard-perpetuo-xorugas/

Mesmo modelo do [dashboard-perpetuo](https://lorenzo-sarcinelli-pascoal.github.io/dashboard-perpetuo/): um **repositório GitHub** com o nome **`dashboard-perpetuo-xorugas`** e Pages via **GitHub Actions**.

## 1. Criar o repositório no GitHub

1. Abra [github.com/new](https://github.com/new).
2. **Repository name:** `dashboard-perpetuo-xorugas`
3. **Public**
4. **Sem** README, .gitignore ou license (evita conflito no primeiro push).
5. Create repository.

## 2. Enviar o código a partir do mono-repo `debriefings-the`

Na **raiz** do repositório que contém a pasta `dashboard-perpetuo-xorugas/`:

```bash
cd /caminho/para/debriefings-the-main

git fetch origin
git pull origin main

git subtree split -P dashboard-perpetuo-xorugas -b xorugas-github-pages

git push git@github.com:lorenzo-sarcinelli-pascoal/dashboard-perpetuo-xorugas.git xorugas-github-pages:main --force
```

(Se usar HTTPS: `https://github.com/lorenzo-sarcinelli-pascoal/dashboard-perpetuo-xorugas.git`.)

## 3. Ativar Pages

No repo **`dashboard-perpetuo-xorugas`** no GitHub:

**Settings → Pages → Build and deployment → Source:** **GitHub Actions**.

## 4. Primeiro deploy

O workflow **Deploy GitHub Pages** corre no push em `main`. Abra a aba **Actions** e confirme que terminou em verde.

## URL final

**https://lorenzo-sarcinelli-pascoal.github.io/dashboard-perpetuo-xorugas/**

---

**Manutenção:** sempre que alterar arquivos dentro de `dashboard-perpetuo-xorugas/` no mono-repo, faça commit no `debriefings-the` e volte a executar os comandos do passo 2 (subtree split + push) para atualizar o site.
