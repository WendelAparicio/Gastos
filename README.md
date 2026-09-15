# Meus Gastos — PWA

App de controle financeiro pessoal (gastos por categoria, parcelas ativas e comparativo mensal), pensado pra rodar instalado no celular como um app.

## Publicar no GitHub Pages (gratuito)

1. Acesse **github.com/new** → dê um nome (ex: `meus-gastos`) → marque **Public** → **Create repository**
2. Na página do repositório, clique em **"uploading an existing file"** e arraste todos os arquivos desta pasta (`index.html`, `manifest.json`, `sw.js` e a pasta `icons/`) — mantenha eles na **raiz** do repositório, não dentro de uma subpasta
3. Vá em **Settings → Pages** → em Source escolha **"Deploy from a branch"** → Branch: `main` → **Save**
4. Espere ~1 minuto. Seu app estará em:
   ```
   https://SEU-USUARIO.github.io/meus-gastos/
   ```

## Instalar no celular

**Android (Chrome)**
1. Abra o link no navegador
2. Toque nos 3 pontinhos → **"Adicionar à tela inicial"** ou **"Instalar app"**

**iPhone (Safari, obrigatório no iOS)**
1. Abra o link no Safari
2. Toque no ícone de compartilhar → **"Adicionar à Tela de Início"**

## Próximo passo: dados reais

Hoje o app usa dados de exemplo, gerados pela função `getMockData()` dentro do `index.html`. Para puxar seus dados reais:

1. Conecte suas contas bancárias em **meu.pluggy.ai** (gratuito, sem prazo de expiração para uso pessoal)
2. Pegue suas credenciais de API no Dashboard de desenvolvedor da Pluggy
3. Troque `getMockData()` por uma função que busca as transações via API da Pluggy e monta os mesmos formatos de `categorias`, `parcelas` e `meses` que o app já espera

Isso pode ser feito direto no `index.html` (chamada `fetch` para a API) ou, se preferir manter as credenciais fora do código público do GitHub, com um backend simples (Supabase Edge Function, por exemplo — você já tem experiência com Supabase) que guarda as chaves e só devolve os dados prontos pro app.
