# saulogatti.com.br

Site pessoal estático: HTML + CSS, sem build. Basta servir a pasta.

```
index.html          página única (hero, sobre, projetos, contato)
assets/style.css    estilos (cores em :root, no topo)
assets/favicon.svg  ícone da aba
.nojekyll           publica os arquivos como estão, sem Jekyll
```

Publicado pelo GitHub Pages a partir da branch `main`, na raiz.

## Rodar local

```powershell
python -m http.server 8080 --bind 127.0.0.1
```

Abra http://localhost:8080.

## Editar

- **Foto:** hoje vem de `https://github.com/saulogatti.png`. Para usar outra, salve em
  `assets/foto.jpg` e troque o `src` do `<img>` no `.avatar` do `index.html`.
- **Redes:** os botões ficam na `ul.social` do `index.html`; a lista `sameAs` do JSON-LD no
  `<head>` repete os mesmos links.
- **Projetos:** os cards em `#projetos` são fixos; edite título, texto e link.
- **Apresentação:** o texto acompanha o README do perfil, em `saulogatti/saulogatti`. Mudou um,
  confira o outro.

## Publicação

Todo push na `main` publica em https://saulogatti.com.br em cerca de um minuto
(`saulogatti.github.io` e `www` redirecionam para lá). Não apague o arquivo `CNAME`.

O DNS do domínio fica na Hostinger (*Domínios → DNS / Nameservers*), com TTL 300:

- `A` em `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
- `AAAA` em `@`: `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`,
  `2606:50c0:8003::153`
- `CNAME` em `www`: `saulogatti.github.io`
- `TXT` `google-site-verification`: manter

O certificado HTTPS é emitido e renovado pelo GitHub (*Settings → Pages*, com *Enforce HTTPS*).
