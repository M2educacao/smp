# Sistema Médico Particular — Landing Page

Landing page estática do produto **Sistema Médico Particular** do Grupo M2, construída como arquivo HTML único (sem build step, sem dependências).

## Estrutura

```
smp-landing/
├── index.html   ← Landing page completa
└── README.md
```

Todo o CSS e o ícone-logo (SVG) estão inline no `index.html`. As únicas dependências externas são as fontes do Google Fonts (Cormorant Garamond + Inter).

## Antes de subir em produção

Abra o `index.html` e faça estas 3 trocas rápidas:

1. **URL de checkout**
   Procure por `TODO_CHECKOUT_URL` e troque `href="#"` pela URL real do checkout (Hotmart, Eduzz, Kiwify, etc).

2. **Confirmar preço à vista**
   Hoje está **R$ 5.690**. Verificar se é esse mesmo ou **R$ 5.499** (valor que aparece no deck de vendas atual).

3. **Meta tags de compartilhamento social (Open Graph / Twitter Card)**
   Quando houver uma imagem de compartilhamento (1200×630px) e a URL final do site, adicionar no `<head>`:
   ```html
   <meta property="og:title" content="Sistema Médico Particular" />
   <meta property="og:description" content="..." />
   <meta property="og:image" content="https://seudominio.com/og.jpg" />
   <meta property="og:url" content="https://seudominio.com" />
   <meta name="twitter:card" content="summary_large_image" />
   ```

## Deploy no Vercel

### Opção 1 — Via interface (mais simples)

1. Acesse [vercel.com/new](https://vercel.com/new)
2. Arraste a pasta `smp-landing/` na tela
3. Clique em **Deploy**
4. Pronto. Vercel te dá uma URL tipo `smp-landing-xxxx.vercel.app`.
5. Em seguida, em **Project Settings → Domains**, conecte um domínio próprio (ex: `sistemamedicoparticular.com.br`).

### Opção 2 — Via CLI

```bash
npm i -g vercel
cd smp-landing
vercel
```

Siga os prompts (login, nome do projeto, confirmar diretório). O Vercel detecta automaticamente que é estático.

Para publicar em produção:

```bash
vercel --prod
```

## Testar localmente

Como é HTML puro, basta abrir o `index.html` no browser. Ou rodar um servidor local:

```bash
# Python
python3 -m http.server 8000

# Node
npx serve
```

Acesse `http://localhost:8000`.

## Customização

As cores, fontes e espaçamentos estão centralizados no bloco `:root` do CSS (no topo do `<style>`). Para ajustar a paleta ou o tipográfico, edite apenas essas variáveis — o resto da página se adapta.

```css
:root {
  --navy-deep: #08162B;
  --navy: #0E2340;
  --gold: #C9A86A;
  /* ... */
}
```
