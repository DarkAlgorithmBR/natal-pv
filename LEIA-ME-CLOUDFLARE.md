# Correção do deploy Cloudflare Workers

O repositório local estava em natal-pv/natal-pv, contendo somente .gitattributes; os arquivos do site estavam fora dele. O comando npx wrangler deploy não encontrava arquivos estáticos nem configuração.

Esta pasta contém uma versão já compilada. Não exige npm install nem build React para publicar.

## Configuração do painel

- Diretório raiz: a raiz do repositório, onde está wrangler.jsonc.
- Build command: deixe vazio.
- Deploy command: npx wrangler deploy.
- O campo name no wrangler.jsonc deve corresponder ao nome do Worker no painel; está como natal-pv.

Envie wrangler.jsonc e a pasta public completa ao repositório conectado ao Cloudflare, depois execute novamente o deploy.

Não envie somente index.html. public/assets contém o JavaScript, CSS, fontes e imagens necessários.

O index.html original continua abrindo localmente. Para ajustar o checkout da versão publicada, edite public/config.js e envie essa alteração ao repositório.

Fonte: https://developers.cloudflare.com/workers/static-assets/binding/
