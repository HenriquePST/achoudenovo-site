# 🔥 Achou de Novo — Vitrine Pública

Site automático de ofertas, alimentado pelo ShopFit Pro.

## Como funciona

1. Você posta um produto no Instagram/Telegram pelo **ShopFit Pro**
2. O ShopFit envia os dados do produto para este repositório via **GitHub API**
3. O `products.json` é atualizado automaticamente
4. O site no **GitHub Pages** exibe o produto em segundos

## Setup

### 1. Criar repositório no GitHub
- Crie um repo público chamado `achoudenovo-site` (ou o nome que quiser)
- Faça upload de todos os arquivos deste zip

### 2. Ativar GitHub Pages
- Vá em **Settings → Pages**
- Source: **Deploy from a branch**
- Branch: **main** / pasta **/ (root)**
- Salvar — o site estará em `https://SEU_USUARIO.github.io/achoudenovo-site`

### 3. Criar GitHub Token
- Acesse: https://github.com/settings/tokens
- **Generate new token (classic)**
- Permissões: marcar `repo` (acesso total)
- Copie o token gerado

### 4. Configurar no ShopFit Pro
No painel de configurações do ShopFit, preencha:
- **GitHub Token**: token gerado acima
- **GitHub User**: seu usuário do GitHub
- **GitHub Repo**: nome do repositório (ex: `achoudenovo-site`)

### 5. Personalizar o site
Edite o `index.html`, linha com `const CONFIG`:
```js
const CONFIG = {
  dataUrl:      'https://raw.githubusercontent.com/SEU_USER/achoudenovo-site/main/products.json',
  instagramUrl: 'https://instagram.com/SEU_PERFIL',
  perfilNome:   '@SEU_PERFIL',
};
```

## Estrutura dos arquivos

```
achoudenovo-site/
├── index.html        ← Site principal
├── products.json     ← Dados dos produtos (atualizado automaticamente)
└── README.md
```

## products.json — formato

```json
{
  "updated": "2026-03-01T00:00:00Z",
  "products": [
    {
      "id": "abc123",
      "name": "Nome do Produto",
      "price": 3990,
      "originalPrice": 7990,
      "discount": 50,
      "category": "Fitness",
      "img": "https://url-da-imagem.jpg",
      "url": "https://s.shopee.com.br/link-afiliado",
      "postedAt": "2026-03-01T10:00:00Z"
    }
  ]
}
```

> Preços em **centavos** (R$ 39,90 = `3990`)
