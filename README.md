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
  `assets/foto.jpg` e troque o `src` do `<img>` no `.avatar` do `index.html` (e o `og:image`).
- **Instagram:** o link está comentado no `index.html`; troque `SEU_USUARIO` e descomente.
- **Projetos:** os cards em `#projetos` são fixos; edite título, texto e link.

## Publicação

Todo push na `main` publica em https://saulogatti.github.io em cerca de um minuto.

### Ligar o domínio saulogatti.com.br

1. No DNS de `saulogatti.com.br` (onde o domínio estiver registrado):
   - `A` em `@` para `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME` em `www` para `saulogatti.github.io`
   - Apagar os registros `A`/`CNAME` antigos de `@` e `www` que apontam para a Hostinger
     (não mexa em `MX`/`TXT` de e-mail).
2. Em *Settings → Pages → Custom domain*, informar `saulogatti.com.br` e salvar. O GitHub
   cria o arquivo `CNAME` na `main` (dê `git pull` depois).
3. Quando o certificado sair, marcar *Enforce HTTPS* na mesma tela.
