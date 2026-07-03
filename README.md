# Baobá Studio — Quadros & Prints

Loja virtual de quadros com checkout via WhatsApp e painel administrativo protegido por PIN.

## Arquivos

- `index.html` — vitrine da loja (catálogo, carrinho, checkout)
- `admin.html` — painel administrativo (cadastro de obras, encomendas, PIN, WhatsApp)

## Como publicar no GitHub Pages

1. Crie um repositório novo no GitHub (ex: `baoba-studio`)
2. Dentro desta pasta, rode:
   ```bash
   git init
   git add .
   git commit -m "Primeira versão da loja"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/baoba-studio.git
   git push -u origin main
   ```
3. No GitHub: **Settings → Pages → Source → Branch: main / (root)** → Save
4. O site fica disponível em `https://SEU_USUARIO.github.io/baoba-studio/`
   - A loja: `.../index.html` (ou só a raiz, se `index.html` for a home)
   - O admin: `.../admin.html`

## ⚠️ Importante: limitação atual

Os dados (obras, encomendas, PIN, número de WhatsApp) ficam salvos no **localStorage do navegador**. Isso significa:

- O que você cadastrar no `admin.html` só aparece no `index.html` **no mesmo navegador/dispositivo**.
- Clientes acessando de outros celulares/computadores **não verão** os produtos cadastrados.

Isso é aceitável para teste ou uso 100% local, mas para a loja funcionar de verdade para clientes reais, o próximo passo é migrar o armazenamento para um backend compartilhado (ex: **Firebase Firestore**, que é gratuito no plano básico e fácil de integrar).

## Segurança do PIN

O PIN do admin também fica salvo no localStorage do navegador — não é uma autenticação segura de verdade (qualquer pessoa com acesso ao DevTools do navegador consegue ver). Bom o suficiente para afastar curiosos, não para proteger dados sensíveis.
