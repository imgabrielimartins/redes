# POP3 — Porta 110 📥

**POP3** significa *Post Office Protocol version 3* e é utilizado para receber/baixar e-mails de um servidor.

```
Servidor de e-mail
       ↓
      POP3
       ↓
Seu computador
```

Tradicionalmente, o POP3 baixa as mensagens para o dispositivo.

---

## Como o download funciona na prática

O comportamento clássico do POP3 é: buscar as mensagens, transferi-las para o seu dispositivo e **remover** do servidor.

```
Servidor                          Seu computador
   │                                    │
   │── Você tem 5 e-mails novos ───────▶│
   │                                    │
   │═══ Baixa as 5 mensagens ══════════▶│
   │                                    │
   │── Apaga do servidor ──────────────│
```

Isso significa que, depois de baixados, os e-mails passam a existir só no dispositivo que fez o download — se você abrir outro computador ou celular depois, aquelas mensagens não estarão mais lá.

📌 Muitos clientes de e-mail modernos permitem configurar o POP3 para *"deixar uma cópia no servidor"*, mas esse não é o comportamento padrão original do protocolo.

---

## POP3 x IMAP

Essa é a comparação mais importante para entender quando usar cada um:

| | POP3 | IMAP |
|---|------|------|
| Onde ficam os e-mails | Baixados para o dispositivo | Permanecem no servidor |
| Múltiplos dispositivos | Não sincroniza bem | Sincroniza automaticamente |
| Uso de espaço no servidor | Baixo (some do servidor) | Maior (fica tudo lá) |
| Cenário ideal | Um único dispositivo fixo | Acesso por vários dispositivos (celular, PC, etc.) |

Por causa dessa limitação, o POP3 é bem menos usado hoje em dia do que o IMAP, que é o padrão da maioria dos serviços de e-mail atuais (Gmail, Outlook, etc.).

---

## Porta

`110`

Existe também **POP3S** (POP3 com criptografia TLS), normalmente na porta `995`.

---

## 🧠 Para lembrar

**POP3 = baixa e-mail → 110**

- Comportamento clássico: baixa e apaga do servidor
- Não sincroniza bem entre vários dispositivos
- Foi amplamente substituído pelo IMAP no uso cotidiano