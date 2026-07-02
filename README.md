# Arte & Alma — Loja + Painel Administrativo

Duas páginas separadas, prontas para hospedar no GitHub Pages:

- **`index.html`** → link para o cliente (a loja, catálogo, carrinho, checkout via WhatsApp)
- **`admin.html`** → link só seu (cadastro de obras/prints, número do WhatsApp), protegido por senha

## Como subir no GitHub Pages

1. Crie um repositório (ex: `arte-alma`) e envie os dois arquivos (`index.html` e `admin.html`) para a raiz.
2. **Settings → Pages → Source** → branch `main`, pasta `/ (root)` → salvar.
3. Em 1–2 minutos:
   - Link do cliente: `https://SEU-USUARIO.github.io/arte-alma/`
   - Link do admin: `https://SEU-USUARIO.github.io/arte-alma/admin.html`

Envie só o primeiro link para os clientes. Guarde o segundo para você.

## Primeiro uso do painel admin

1. Abra `admin.html`.
2. Na primeira vez, ele vai pedir para você **criar uma senha** (mínimo 4 caracteres) — isso protege o painel nesse navegador.
3. Depois de entrar, cadastre seu número de WhatsApp na barra do topo (formato: `55` + DDD + número, só dígitos — ex: `5511987654321`).
4. Cadastre suas obras e prints preenchendo o formulário.

## Como funciona o pedido

1. O cliente entra em `index.html`, escolhe a obra, tamanho e moldura, adiciona ao carrinho.
2. No checkout, ele preenche nome, telefone e endereço — o frete é calculado automaticamente pelo CEP (via ViaCEP).
3. Ao clicar em "Enviar pedido pelo WhatsApp", abre o WhatsApp já com uma mensagem pronta contendo: itens escolhidos, subtotal, frete, total e o endereço completo — indo direto para o **seu número**, configurado no admin.

## ⚠️ Limitação importante (como combinamos)

Este site **não tem banco de dados** — tudo fica salvo no `localStorage` do navegador de cada pessoa:

- As obras que você cadastrar em `admin.html` só aparecem em `index.html` **se forem abertos no mesmo navegador/aparelho**.
- Se você cadastrar as obras no seu computador e mandar o link `index.html` para um cliente no celular dele, **ele não vai ver o catálogo** (vai aparecer "Nenhuma obra cadastrada").

**Isso funciona bem para:**
- Testar o site e mostrar para você mesmo.
- Usar em um único dispositivo (ex: um tablet fixo numa loja física, onde o cliente escolhe ali mesmo).

**Não funciona para:**
- Divulgar o link `index.html` para clientes em outros dispositivos e esperar que vejam o catálogo que você cadastrou.

Se no futuro você quiser que o catálogo apareça igual para todo mundo (o cenário mais comum para vender online), me avisa — dá pra evoluir isso conectando a um banco de dados gratuito (Firebase), sem precisar saber programar, só criar uma conta grátis no Google e colar uma chave de configuração.

## Segurança da senha do admin

O bloqueio por senha em `admin.html` é uma trava simples (roda só no navegador) — serve para impedir que um cliente casual mexa no painel, mas não é uma segurança de nível bancário, já que o código roda no próprio navegador. Para o uso pretendido (você mesmo cadastrando produtos), é suficiente.
