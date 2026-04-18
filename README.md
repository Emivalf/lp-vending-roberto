# LP de Captação — Treinamento Vending Machines Roberto Araújo

Landing page de captação para o Treinamento Gratuito de 3 aulas (06, 07 e 08 de maio).

## Estrutura

```
.
├── index.html              # Página principal
├── images/                 # Imagens da LP
│   ├── hero-maquina.jpg   # Máquina no hero (dobra 1)
│   ├── maquina-hospital.jpg
│   ├── instalacao-maquina.jpg
│   ├── roberto-araujo.jpg  # Foto do Roberto (dobra 8)
│   └── logo.png
└── README.md
```

## Como publicar no GitHub Pages (5 minutos)

### Opção A — Pelo site do GitHub (mais fácil)

1. Acessa https://github.com/new
2. Cria um repositório novo. Sugestão de nome: `lp-vending-roberto`
3. Marca **Public** (obrigatório para GitHub Pages grátis)
4. Clica em **Create repository**
5. Na tela do repositório vazio, clica em **"uploading an existing file"**
6. Arrasta **todos os arquivos e a pasta `images/`** juntos
7. Escreve uma mensagem de commit (ex: "primeira versão da LP") e clica em **Commit changes**
8. Vai em **Settings** (no topo do repositório) → **Pages** (menu lateral)
9. Em "Source", seleciona **Deploy from a branch**
10. Em "Branch", seleciona **main** e pasta **/ (root)** → clica em **Save**
11. Aguarda 1-2 minutos e a URL pública aparece no topo da página:
    `https://seu-usuario.github.io/lp-vending-roberto/`

### Opção B — Via Git (terminal)

```bash
# No terminal, dentro da pasta do projeto:
git init
git add .
git commit -m "Primeira versão da LP"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/lp-vending-roberto.git
git push -u origin main

# Depois ativar GitHub Pages em Settings → Pages (passo 8-10 acima)
```

## Domínio customizado (opcional)

Se quiser usar domínio próprio (ex: `captacao.vendingmachines.com.br`):

1. No Settings → Pages, em "Custom domain", digita o domínio
2. No painel do seu registrador (Registro.br, GoDaddy, etc), adiciona um registro CNAME:
   - Nome: `captacao` (ou o subdomínio escolhido)
   - Valor: `seu-usuario.github.io`
3. GitHub valida automaticamente (pode demorar até 24h) e ativa HTTPS

## Antes de subir em produção — checklist

- [ ] Trocar o formulário mockup pela integração real (RD Station, ActiveCampaign, Mailchimp, ou o que o time já usa)
- [ ] Adicionar pixel do Meta (Facebook) no `<head>`
- [ ] Adicionar Google Tag Manager ou Google Analytics no `<head>`
- [ ] Testar em diferentes navegadores (Chrome, Safari, Firefox, Edge)
- [ ] Testar em dispositivos móveis reais (iOS e Android)
- [ ] Validar se os links de CTA (`#inscricao`) estão rolando suavemente até o form
- [ ] Revisar texto final com o cliente antes de publicar
- [ ] Conferir se os horários (19h) e datas (06, 07, 08 de maio) estão corretos em todas as menções

## Pontos de edição rápida

**Mudar data/hora das aulas:** busque por "06, 07 e 08 de maio" e "19h" no HTML

**Mudar número de faturamento:** busque por "770k" ou "700" no HTML

**Trocar imagem:** substitua o arquivo correspondente dentro de `images/` mantendo o mesmo nome

**Adicionar pixel do Meta:** abra `index.html`, procure por `</head>` e cole o pixel logo antes dessa tag

## Formulário — como conectar

O formulário atual é um mockup que mostra uma mensagem de sucesso ao submeter. Para plugar num provedor real:

### Exemplo com RD Station

```html
<!-- Substituir o <form onsubmit="..."> por: -->
<form action="https://api.rd.services/platform/conversions?api_key=SUA_KEY" method="POST">
```

### Exemplo com ActiveCampaign

```html
<form action="https://SUA-CONTA.activehosted.com/proc.php" method="POST">
<input type="hidden" name="u" value="SEU_FORMULARIO_ID">
<input type="hidden" name="f" value="SEU_FORMULARIO_ID">
```

### Exemplo com webhook genérico (Zapier, Make, n8n)

```html
<form action="https://hooks.zapier.com/hooks/catch/SEU-HOOK" method="POST">
```

Os campos devem manter os `name=` corretos:
- Nome: `name="nome"` ou o que o provedor espera
- E-mail: `name="email"`  
- WhatsApp: `name="phone"` ou `telefone`

## Suporte

Qualquer ajuste visual, de copy ou de integração, me chame.
