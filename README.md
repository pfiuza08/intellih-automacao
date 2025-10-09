
---

## 🧩 Objetivo do Funil

Ajudar pessoas e empresas a **economizarem tempo e dinheiro** automatizando tarefas repetitivas com IA e ferramentas inteligentes.

O funil gera leads qualificados e mede cada etapa do processo para otimização contínua das campanhas Meta Ads e Google Ads.

---

## 🧱 Estrutura das Páginas

### 1. **index.html** – Landing Page
- Apresenta a proposta de valor da **Intellih Tecnologia**.
- Evento do Pixel: `PageView`
- CTA → Direciona para `/diagnostico`

### 2. **diagnostico.html**
- Dispara o evento `Lead` ao ser acessada.
- Mostra tela de carregamento e redireciona para o formulário (Google Forms ou Tally).
- Tempo de espera: 2 segundos.

### 3. **thankyou.html**
- Exibida após o envio do formulário.
- Dispara o evento `CompleteRegistration`.
- Contém botão para contato direto no WhatsApp.

### 4. **consultoria.html**
- Página institucional de agendamento gratuito.
- Dispara `PageView` + `Schedule`.
- Botão de WhatsApp integrado com mensagem automática.

### 5. **consultoria-premium.html**
- Versão aprimorada visualmente da consultoria.
- Fundo com imagem, ícones e seções de benefícios.
- Dispara `Schedule` automaticamente + ao clique no CTA.
- Usada em campanhas de remarketing e autoridade.

---

## 📡 Rastreamento e Eventos Meta

| Página / Ação | Evento Meta | Objetivo |
|----------------|--------------|-----------|
| Acesso à landing | `PageView` | Medir visitas e remarketing |
| Clique em “Diagnóstico” | `Lead` | Registrar intenção inicial |
| Envio do formulário | `CompleteRegistration` | Medir leads completos |
| Agendamento de consultoria | `Schedule` | Medir conversões de alto valor |

✅ **Pixel ID:** `1467115531230271`  
✅ Todos os eventos são disparados automaticamente via script embutido.

---

## 🌐 Configuração de Rotas (vercel.json)

```json
{
  "version": 2,
  "routes": [
    { "src": "/diagnostico", "dest": "/diagnostico.html" },
    { "src": "/diagnostico/", "dest": "/diagnostico.html" },
    { "src": "/consultoria", "dest": "/consultoria.html" },
    { "src": "/consultoria/", "dest": "/consultoria.html" },
    { "src": "/consultoria-premium", "dest": "/consultoria-premium.html" },
    { "src": "/consultoria-premium/", "dest": "/consultoria-premium.html" },
    { "src": "/thankyou", "dest": "/thankyou.html" },
    { "src": "/thankyou/", "dest": "/thankyou.html" },
    { "src": "/obrigado", "dest": "/thankyou.html" },
    { "src": "/obrigado/", "dest": "/thankyou.html" },
    { "src": "/(.*)", "dest": "/index.html" }
  ]
}
