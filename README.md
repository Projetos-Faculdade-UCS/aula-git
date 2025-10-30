# Projeto de Teste de Pipelines

Este repositório serve para testar pipelines e o uso de deploys manuais em duas plataformas diferentes:

- Branch `main`: deploy manual/CI pelo Netlify
- Branch `develop`: deploy no Vercel

## Acesso aos sites (por branch)

- main: [https://teste-pipeline.netlify.app/](https://teste-pipeline.netlify.app/)
- develop: [https://aula-git-ten.vercel.app/](https://aula-git-ten.vercel.app/)

## Objetivo

O objetivo deste projeto é fornecer um repositório simples para validar configurações de pipeline e demonstrar como realizar deploys manuais e contínuos nas duas plataformas (Netlify e Vercel).

## Como funciona

- A workflow do GitHub Actions para a branch `main` (arquivo: `.github/workflows/main.yml`) usa o CLI do Netlify para realizar o deploy manual/automático para o site configurado.
- A branch `develop` está configurada para deploy no Vercel (normalmente via integração do Vercel com o repositório ou via Vercel CLI).

## Deploy manual — Netlify (branch main)

Exemplo de comando usado na workflow para deploy manual com Netlify CLI:

```bash
netlify deploy --site=${{ secrets.NETLIFY_SITE_ID }} --auth=${{ secrets.NETLIFY_AUTH_TOKEN }} --dir="." --prod
```

Também é possível realizar deploys manuais pelo painel do Netlify (Dashboard) apontando para o mesmo diretório/branch.

## Deploy manual — Vercel (branch develop)

Para deploy manual com Vercel CLI, use algo como:

```bash
vercel --prod
```

Ou acesse o painel do Vercel e faça um deploy a partir da branch `develop`.

## Observações

- Certifique-se de que os secrets (por exemplo, `NETLIFY_SITE_ID` e `NETLIFY_AUTH_TOKEN`) estão corretamente configurados nas configurações do repositório para que o workflow consiga autenticar e publicar.
- Este repositório contém apenas um arquivo `index.html` para fins de demonstração de deploy.

## Contato

Para dúvidas sobre a configuração das pipelines, abra uma issue neste repositório.
