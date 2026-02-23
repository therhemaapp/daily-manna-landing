# Daily Manna — Landing Page

Página de download do Daily Manna, hospedada no GitHub Pages.

Funcionalidades:
- **Detecção automática de SO** — redireciona iOS → App Store, Android → Google Play
- **Fallback para desktop** — mostra ambos os botões
- **SEO e Open Graph** — preview bonito no WhatsApp, Facebook, etc.

## Como publicar

### 1. Criar o repositório no GitHub

Na conta do projeto, crie um novo repositório **público** chamado `daily-words-landing`.

### 2. Fazer push dos arquivos

```bash
cd landing-page
git init
git add .
git commit -m "Landing page com detecção de SO"
git remote add origin https://github.com/SEU-USUARIO/daily-words-landing.git
git branch -M main
git push -u origin main
```

### 3. Ativar GitHub Pages

1. Vá em **Settings** > **Pages** no repositório
2. Em **Source**, selecione `Deploy from a branch`
3. Em **Branch**, selecione `main` e pasta `/ (root)`
4. Clique **Save**
5. Aguarde ~2min e a URL estará em: `https://SEU-USUARIO.github.io/daily-words-landing/`

### 4. Substituir os links das lojas

No `index.html`, substitua os `TODO` na seção `STORE_LINKS`:

```javascript
const STORE_LINKS = {
  ios: 'https://apps.apple.com/app/daily-manna/idXXXXXXXXXX',    // ← ID real
  android: 'https://play.google.com/store/apps/details?id=com.gustavocoutinho.dailymanna',
};
```

### 5. Substituir as meta tags OG

No `<head>` do `index.html`:
- `og:url` → URL real do GitHub Pages
- `og:image` → URL de uma imagem de preview (1200x630px recomendado)

### 6. Usar no app

Atualize o link de compartilhamento no app Flutter para usar a URL da landing page:
```dart
// Em algum serviço ou constante do app
const appDownloadUrl = 'https://SEU-USUARIO.github.io/daily-words-landing/';
```

### 7. (Opcional) Domínio personalizado

Se quiser usar um domínio como `app.dailymanna.com`:
1. Adicione um arquivo `CNAME` com o domínio
2. Configure o DNS (A ou CNAME record)
3. Ative HTTPS em Settings > Pages
