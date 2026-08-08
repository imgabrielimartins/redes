# SMTP — Porta 25 📧

**SMTP** significa *Simple Mail Transfer Protocol* e é usado para enviar e-mails.

Imagine que você manda um e-mail:

```
Você
 ↓
SMTP
 ↓
Servidor de e-mail
 ↓
Servidor do destinatário
 ↓
Pessoa recebe
```

SMTP está relacionado ao **envio**. Ele não serve para você ler ou baixar e-mails — isso é papel de outros protocolos, como POP3 e IMAP.

---

## O caminho completo de um e-mail

Um detalhe importante: o SMTP normalmente é usado em duas etapas diferentes do trajeto de um e-mail.

```
Você (cliente de e-mail)
   │
   │  SMTP (envio autenticado)
   ▼
Servidor de e-mail do remetente
   │
   │  SMTP (comunicação entre servidores)
   ▼
Servidor de e-mail do destinatário
   │
   │  POP3/IMAP (o destinatário busca o e-mail)
   ▼
Pessoa recebe
```

Ou seja: SMTP entrega o e-mail até a "caixa de correio" do destinatário, mas quem efetivamente busca e exibe essa mensagem no dispositivo da pessoa é o POP3 ou o IMAP.

---

## Por que existem portas diferentes?

O SMTP tradicionalmente usa a porta `25`, mas hoje em dia essa porta é usada principalmente para a comunicação **entre servidores** de e-mail — e é comumente bloqueada por provedores de internet residenciais, justamente para dificultar o envio de spam por computadores infectados.

Por isso, quando você configura seu e-mail em um aplicativo (Outlook, celular, etc.), normalmente é usada uma porta diferente para o **envio autenticado**, feito diretamente pelo seu cliente de e-mail:

| Porta | Uso |
|-------|-----|
| 25 | Comunicação tradicional entre servidores de e-mail |
| 587 | Envio autenticado por clientes de e-mail (com STARTTLS) |
| 465 | SMTP sobre TLS direto (SMTPS) |

---

## 🧠 Para lembrar

**SMTP = envia e-mail → 25**

- Cuida apenas do envio, não da leitura
- Passa pelo servidor do remetente e depois pelo servidor do destinatário
- Na prática, o envio do seu app de e-mail costuma usar a porta 587 ou 465, não a 25