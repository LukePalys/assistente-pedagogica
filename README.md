# 🍎 Assistente Pedagógica Infantil - Pronta para Deploy

## 📦 Conteúdo da Pasta

Esta pasta contém todos os arquivos necessários para publicar a plataforma em um servidor web:

- **index.html** - Arquivo principal da aplicação
- **index.js** - Bundle JavaScript do servidor
- **public/** - Pasta com assets (CSS, JavaScript, imagens)
  - **assets/** - Todos os arquivos compilados e otimizados

## 🚀 Como Usar

### ⚠️ IMPORTANTE: Descompactar Assets

Antes de publicar, você PRECISA descompactar o arquivo `public-assets.tar.gz`:

```bash
tar -xzf public-assets.tar.gz
```

Isso criará a pasta `public/` com todos os assets necessários.

## 🚀 Como Publicar

### Opção 1: Vercel (Recomendado - Gratuito)
```bash
npm i -g vercel
vercel
```

### Opção 2: Netlify (Gratuito)
1. Acesse https://app.netlify.com
2. Faça login com GitHub
3. Arraste a pasta `assistente-pedagogica-infantil-deploy` para publicar

### Opção 3: GitHub Pages
```bash
git init
git add .
git commit -m "Deploy Assistente Pedagógica"
git branch -M main
git remote add origin https://github.com/seu-usuario/seu-repo.git
git push -u origin main
```

### Opção 4: Seu Próprio Servidor
1. Faça upload de todos os arquivos para o servidor
2. Configure o servidor para servir `index.html` como fallback
3. Certifique-se de que o servidor suporta HTTPS

## 🔧 Configuração do Servidor

### Nginx
```nginx
server {
    listen 80;
    server_name seu-dominio.com;
    
    root /var/www/assistente-pedagogica;
    index index.html;
    
    location / {
        try_files $uri $uri/ /index.html;
    }
}
```

### Apache
```apache
<Directory /var/www/assistente-pedagogica>
    RewriteEngine On
    RewriteBase /
    RewriteRule ^index\.html$ - [L]
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteRule . /index.html [L]
</Directory>
```

## 🔐 Variáveis de Ambiente Necessárias

A aplicação usa as seguintes variáveis de ambiente (já configuradas):

- `OPENROUTER_API_KEY` - Chave da API OpenRouter (já configurada)
- `VITE_APP_TITLE` - Título da aplicação
- `VITE_APP_LOGO` - Logo da aplicação
- `VITE_OAUTH_PORTAL_URL` - URL do portal OAuth
- `VITE_FRONTEND_FORGE_API_URL` - URL da API Forge

## 📋 Checklist de Deploy

- [ ] Todos os arquivos foram copiados
- [ ] Servidor está configurado corretamente
- [ ] HTTPS está ativado
- [ ] Domínio está apontando para o servidor
- [ ] Testes de funcionalidade realizados

## 🎯 Funcionalidades Incluídas

✅ Chat interativo com IA OpenRouter
✅ Geração de documentos BNCC formatados
✅ Exportação PDF/DOCX
✅ Upload para S3
✅ Histórico de conversas
✅ Modo escuro/claro
✅ Autenticação OAuth
✅ Notificações em tempo real

## 📞 Suporte

Para problemas com a publicação, consulte:
- Documentação Vercel: https://vercel.com/docs
- Documentação Netlify: https://docs.netlify.com
- Documentação Capacitor: https://capacitorjs.com/docs

---

**Desenvolvido com ❤️ para educadores**
