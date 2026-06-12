#  RelatórioAI

Gerador inteligente de relatórios profissionais — **gratuito, open source e 100% client-side**.

Nenhum dado é enviado para servidor. Tudo roda direto no navegador do usuário.

---

##  Funcionalidades

- **5 modelos prontos** — Relatório Simples, Estágio, Empresarial, Técnico e Mensal
- **Seções personalizáveis** — ative/desative e reordene arrastando
- **Perguntas personalizadas** — adicione suas próprias seções
- **Pré-visualização em tempo real** — painel lateral mostra como o documento ficará
- **Barra de progresso** — indica o quanto do relatório já foi preenchido
- **Melhorar texto com IA** — integração com a API da Anthropic (Claude Haiku); o usuário usa a própria chave, que nunca é salva em nenhum servidor
- **Exportação PDF** — documento formatado com tipografia profissional, idêntico ao preview
- **Exportação CSV** — compatível com Excel (UTF-8 BOM)
- **Tema claro / escuro**
- **Responsivo** — funciona em mobile e desktop

---

##  Como hospedar

É um único arquivo HTML estático. Não precisa de backend, banco de dados ou Node.js.

### Opção 1 — GitHub Pages (gratuito)

```bash
# 1. Crie um repositório no GitHub
# 2. Faça upload do arquivo relatorio-ai.html renomeando para index.html
# 3. Vá em Settings → Pages → Source: main / root
# 4. Pronto — seu site estará em https://seu-usuario.github.io/nome-do-repo
```

### Opção 2 — Netlify / Vercel (gratuito)

```
1. Acesse netlify.com ou vercel.com
2. Arraste a pasta com o index.html para o painel de deploy
3. Pronto — URL gerada automaticamente
```

### Opção 3 — cPanel / Hospedagem tradicional

```
1. Renomeie relatorio-ai.html para index.html
2. Faça upload via Gerenciador de Arquivos ou FTP para public_html/
3. Acesse pelo domínio normalmente
```

---

##  Funcionalidade de IA (opcional)

O botão ** Melhorar Texto** usa a API da Anthropic (modelo `claude-haiku`).

- O usuário informa a própria chave de API no momento do uso
- A chave fica **apenas na memória da aba** — nunca é salva em localStorage, cookie ou servidor
- Ao fechar a aba, a chave é apagada automaticamente
- Para obter uma chave: [console.anthropic.com](https://console.anthropic.com)

Se preferir remover essa funcionalidade, basta apagar o botão `✨` e as funções `openImproveModal`, `doImprove` e `applyImproved` no HTML.

---

## 🛠 Tecnologias utilizadas

| Tecnologia | Uso | CDN |
|---|---|---|
| [jsPDF 2.5.1](https://github.com/parallax/jsPDF) | Geração de PDF | cdnjs.cloudflare.com |
| [Google Fonts](https://fonts.google.com) | Inter, Sora, JetBrains Mono | fonts.googleapis.com |
| [Anthropic API](https://docs.anthropic.com) | Melhoria de texto com IA | api.anthropic.com |

Nenhuma dependência de build. Sem npm, sem Webpack, sem framework.

---

##  Estrutura do projeto

```
relatorio-ai.html   ← arquivo único, tudo incluso (HTML + CSS + JS)
README.md
```

---

##  Privacidade e segurança

- **Sem cookies**, sem rastreamento, sem analytics
- **Sem localStorage** — nenhum dado do usuário é persistido entre sessões
- Todos os inputs passam por sanitização (`escHtml` + `sanitizeText`) antes de serem usados no DOM
- Campos têm `maxlength` para evitar payloads abusivos
- A chave de API Anthropic nunca sai do JavaScript em memória

---

##  Licença

MIT — use, modifique e distribua livremente.

---

##  Contribuindo

Pull requests são bem-vindos! Para mudanças maiores, abra uma issue primeiro descrevendo o que deseja alterar.

---

Feito com  — funciona em qualquer navegador moderno sem instalação.
