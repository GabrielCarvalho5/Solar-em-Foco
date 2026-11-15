# Solar em Foco — versão 1.0

Portal jornalístico estático, responsivo e gratuito, com editor local.

## Arquivos
- `index.html`: portal, busca, editorias e páginas de matérias via `?materia=ID`.
- `admin.html`: editor local (sem autenticação e sem publicação automática).
- `articles.json`: matérias exibidas publicamente.
- `style.css`, `app.js`, `editor.js`: estilos e funcionalidades.

## Testar no computador
O site usa `fetch()` para ler `articles.json`, portanto não abra `index.html` diretamente por `file://`.

Com Python 3 instalado, dentro desta pasta execute:

```bash
python3 -m http.server 8000
```

Acesse `http://localhost:8000` e `http://localhost:8000/admin.html`.

## Publicar grátis
1. Crie uma conta gratuita no GitHub, se necessário.
2. Crie um repositório público para o portal e envie os arquivos desta pasta (não apenas o ZIP).
3. Em **Settings → Pages**, selecione **Deploy from a branch**, branch `main`, pasta `/ (root)` e salve.
4. Aguarde a implantação. O endereço costuma seguir `https://USUARIO.github.io/REPOSITORIO/`.
5. O editor (`admin.html`) é **público** na hospedagem estática: não é um painel protegido. Qualquer pessoa pode abri-lo, mas os rascunhos ficam apenas no navegador de quem o usa, e ninguém publica no seu repositório sem permissão de escrita no GitHub.

## Fluxo de publicação sem custo
1. Abra `admin.html` no seu navegador habitual.
2. Antes de editar, importe o `articles.json` atual se os dados locais ainda não estiverem sincronizados.
3. Crie ou altere a matéria, salve o rascunho e clique em **Exportar articles.json**.
4. No repositório GitHub, substitua o arquivo `articles.json` pelo exportado e confirme a alteração.
5. Aguarde o GitHub Pages atualizar. A matéria aparecerá no portal.

**Importante:** exportar substitui a coleção inteira de matérias. Para não apagar publicações anteriores, importe o JSON atual antes de exportar. Faça cópias de segurança do JSON. Rascunhos em `localStorage` podem ser apagados ao limpar os dados do navegador ou trocar de dispositivo.

## Cuidados editoriais
As três matérias incluídas são exemplos educativos, não notícias recentes verificadas. Antes de publicar notícias reais, cheque fatos, datas, autoria, fontes e direitos de imagem. Conteúdo patrocinado deve ser identificado. A marca Solarprime aparece apenas no espaço de patrocínio.

## Limites atuais
Sem login real, sem banco de dados, sem upload de imagens, sem publicação automática e sem sincronização entre dispositivos. Essas funções exigem uma etapa posterior de integração. O GitHub Pages oferece hospedagem gratuita sujeita às regras e limites do serviço.
