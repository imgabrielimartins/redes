# IMAP — Porta 143 📬

**IMAP** significa *Internet Message Access Protocol* e também é usado para acessar e-mails.

Mas ele funciona de uma maneira diferente do POP3.

Com IMAP, os e-mails ficam **sincronizados com o servidor**, em vez de serem baixados e removidos de lá.

---

## Como a sincronização funciona

Imagine que você tenha:

```
📱 Celular
💻 Notebook
🖥️ Computador
```

Todos acessam a mesma conta.

Se você ler um e-mail no celular:

```
📱 → e-mail lido
```

essa informação pode aparecer também no notebook, porque a caixa de correio é sincronizada com o servidor:

```
Servidor de e-mail
   │
   ├──▶ 📱 Celular    → "e-mail 3 está lido"
   ├──▶ 💻 Notebook   → "e-mail 3 está lido"
   └──▶ 🖥️ Computador → "e-mail 3 está lido"
```

O servidor é sempre a "fonte da verdade": as pastas, os e-mails lidos/não lidos, apagados, movidos — tudo continua existindo no servidor e cada dispositivo apenas reflete esse estado.

---

## O que fica sincronizado

Além de ler ou não ler, o IMAP também sincroniza ações como:

- Mover e-mail para outra pasta
- Marcar como importante/favorito
- Apagar (geralmente move para a lixeira, também sincronizada)
- Criar novas pastas

Tudo isso reflete em qualquer dispositivo conectado à mesma conta.

---

## IMAP x POP3

| | IMAP | POP3 |
|---|------|------|
| Onde ficam os e-mails | No servidor | Baixados para o dispositivo |
| Múltiplos dispositivos | Sincroniza automaticamente | Não sincroniza bem |
| Uso de espaço no servidor | Maior (fica tudo lá) | Baixo (some do servidor) |
| Cenário ideal | Acesso por vários dispositivos | Um único dispositivo fixo |

Por causa dessa sincronização, o IMAP é o padrão usado hoje pela maioria dos serviços de e-mail (Gmail, Outlook, etc.).

---

## Porta

`143`

**IMAPS**, com TLS, normalmente usa a porta `993`.

---

## 🧠 Para lembrar

**IMAP = e-mail sincronizado → 143**

- E-mails permanecem no servidor
- Ações (ler, mover, apagar) refletem em todos os dispositivos
- É o padrão atual na maioria dos serviços de e-mail