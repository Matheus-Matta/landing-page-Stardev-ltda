# Stardev — Engenharia com gosto.

Este repositório contém o código-fonte da landing page estática oficial da **Stardev**, uma software house e incubadora de SaaS focada em entregar soluções de elite com arquitetura sólida, performance e design sofisticado.

## 🚀 Tecnologias Utilizadas

O projeto foi construído para ser extremamente rápido, leve e amigável para SEO, utilizando uma stack moderna e livre de dependências pesadas no navegador:

*   **HTML5 & Vanilla JavaScript**: Interatividade nativa (efeitos de digitação, acordeões e submissão de formulários) sem overhead de frameworks.
*   **CSS3 & Variáveis CSS**: Design system modular focado em um tema editorial escuro (dark theme) elegante.
*   **Tailwind CSS (CLI)**: Utilizado via Node para a compilação de classes utilitárias, garantindo consistência e rapidez no desenvolvimento.
*   **Nginx**: O projeto inclui um arquivo de configuração pronto e otimizado para deploy em produção (cache, gzip e headers de segurança).

## ✨ Principais Funcionalidades

*   **Design Premium & Responsivo**: Interface editorial escura utilizando a combinação das tipografias *Instrument Serif*, *Geist* e *JetBrains Mono*.
*   **Bento Grid Interativo**: Cards de demonstração (SaaS e Templates) com suporte a *hover effects* avançados, exibindo miniaturas responsivas desenhadas em CSS puro.
*   **Efeitos Visuais**: Efeito de *Typewriter* (digitação) implementado no banner inicial e no rodapé, acionado de forma performática via `IntersectionObserver`.
*   **Contato Inteligente**: Formulário integrado com requisições assíncronas (AJAX) enviando dados em JSON diretamente para um webhook do **n8n**, com feedback visual (Enviando, Sucesso, Erro).
*   **SEO & Social Prontos**: Tags completas (Open Graph, Twitter Cards, descrições meta) configuradas para alto ranqueamento e compartilhamento perfeito em redes sociais.

## 💻 Como rodar o projeto localmente

Como a aplicação é puramente estática (HTML/CSS/JS nativos), você pode abrir o `index.html` diretamente no navegador ou usar o plugin *Live Server* do VSCode para ter um recarregamento automático (hot-reload).

Caso você precise adicionar novas classes do **Tailwind CSS** ao arquivo HTML, você precisará instalar as dependências e rodar o compilador:

1. Instale o Tailwind (salvo no `package.json`):
   ```bash
   npm install
   ```

2. Rode o compilador em modo de observação (watch):
   ```bash
   npm run dev
   ```
   *Este comando ficará monitorando o arquivo `index.html` e atualizará o `tailwind.css` instantaneamente.*

## 🏗️ Gerando a versão de Produção

Antes de fazer o deploy no servidor de produção, é essencial minificar (comprimir) o arquivo CSS do Tailwind para garantir a máxima performance de carregamento:

```bash
npm run build
```

Este comando sobrescreve o `tailwind.css` deixando apenas os estilos utilizados em uma única linha otimizada.

## 🚀 Deploy (Nginx)

Na raiz do projeto há o arquivo `nginx.conf`. Ele contém regras de bloqueio básico de segurança (XSS, Content-Type Sniffing), Cache para arquivos estáticos de longa duração e ativação de Gzip.

1. Edite o `nginx.conf`, ajustando o `server_name` para o seu domínio (ex: `star.dev.br`) e o `root` para a localização real da pasta no seu servidor Ubuntu/Debian (ex: `/usr/share/nginx/html`).
2. Adicione este arquivo (ou mescle) à sua configuração padrão do Nginx (`/etc/nginx/sites-available/`).
3. Recarregue o Nginx (`sudo systemctl reload nginx`).

---
**Stardev Ltda.** · Rio de Janeiro, BR
