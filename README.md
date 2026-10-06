# TV Legal 5 - CineStream Hub

Plataforma cinematográfica de streaming ao vivo com player HLS integrado, navegação por categorias, canais favoritos, painel administrativo e suporte nativo para Android TV e smartphones.

---

## 📺 Principais Funcionalidades

1. **Player HLS Integrado**:
   - Transmissões contínuas em formato HLS (.m3u8).
   - Suporte a seleção de qualidade (Auto / 720p / 1080p).
   - Modo tela cheia, modo teatro e picture-in-picture.
   - Navegação por atalhos de teclado (Espaço, F, T, M, setas).

2. **220 Canais Organizados por Categoria**:
   - Filmes, Séries VIP, TV Aberta, Esportes, Jornalismo, Animes, Infantil, Música, etc.
   - Navegação em carrosséis com visualização em Trilhos (estilo Netflix) ou Grade Completa.
   - Barra deslizante de rolagem customizada e fluida.

3. **Totalmente Responsivo para Smartphones**:
   - Logomarcas adaptativas que nunca distorcem ou cortam (`object-contain`).
   - Botões e controles com área de toque mínima de 40px.
   - Barra inferior móvel nativa com atalhos para Player, Categorias, Favoritos e Painel ADM.

4. **Android TV & APK**:
   - APK nativo compilado e assinado (`app-release.apk` e `tvlegal5.apk`).
   - Suporte ao controle remoto da TV (D-pad e botão OK).
   - Banner Leanback 16:9 oficial para a tela inicial do Android TV e Google TV.
   - Projeto nativo completo em `tv-legal-5-android-tv.zip`.

5. **Painel Administrativo Completo**:
   - Cadastro de novos canais e categorias.
   - Edição de nomes, URLs de transmissão e logomarcas.
   - Pausa e ativação instantânea de canais.
   - Backup e importação de listas em formato JSON.

---

## 🚀 Como Rodar o Projeto Localmente

### Requisitos:
- Node.js 18+ ou 20+ ou 22+
- npm

### Instalação:
```bash
# 1. Instalar dependências
npm install

# 2. Iniciar servidor de desenvolvimento
npm run dev

# 3. Compilar para produção
npm run build
```

---

## 📱 Como Instalar o APK na Android TV

### Método 1: Via ADB
```bash
adb connect IP_DA_SUA_TV:5555
adb install public/app-release.apk
```

### Método 2: Pelo app "Downloader" na TV
Digite a URL direta do arquivo APK no app Downloader da sua TV.

---

## 📁 Estrutura de Arquivos

- `src/`
  - `components/`: Navbar, VideoPlayer, HeroBanner, ChannelCard, CategoryNav, CategoryRow, AdminModal, CastModal, AndroidTVModal, Footer, etc.
  - `services/`: `supabaseClient.ts` (integração Supabase e fallback de cache local).
  - `data/`: `initialChannels.json` (banco inicial com 220 canais).
  - `types/`: `channel.ts` (definições de tipos TypeScript).
  - `hooks/`: `usePWAInstall.ts` (gerenciador de instalação PWA).
  - `App.tsx`: Componente central da aplicação.
  - `index.css`: Estilos globais Tailwind CSS e customizações visuais.
- `public/`:
  - `app-release.apk` / `tvlegal5.apk`: APK assinado para Android TV.
  - `tv-legal-5-android-tv.zip`: Projeto Gradle / Android Studio nativo.
  - `pwa-192x192.png`, `pwa-512x512.png`: Ícones do aplicativo.
  - `tv-banner-320x180.png`: Banner de TV Leanback.
