# Playbook de Operação · Google Ads Webmotors

Playbook online e contínuo para o time de performance da Webmotors.
Elaborado pelo time de auditoria e diagnóstico da **Caliber 3135** · Setembro de 2026.

## Estrutura

```
index.html      Página publicada (arquivo único, autocontido)
vercel.json     Força o Vercel a servir a página como HTML (evita download)
README.md       Este arquivo
source/         Arquivos editáveis que geram o index.html
```

## Deploy no Vercel

1. Suba o conteúdo desta pasta na raiz do repositório.
2. Vercel → Settings → Build & Deployment: Framework Preset **Other**, sem Build Command, Output Directory vazio.
3. Redeploy.

Conferência: `curl -I <url>` deve retornar `content-type: text/html; charset=utf-8`.

## Deploy no GitHub Pages

Settings → Pages → Deploy from a branch → `main` / `(root)`.

## Manutenção

O conteúdo vem de `source/playbook-google-ads-webmotors.md`. Ao atualizar o playbook (status, itens, testes), a página deve ser regenerada a partir do MD e o `index.html` substituído.
