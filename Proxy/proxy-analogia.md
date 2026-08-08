# O que é um Proxy?

Imagine que você quer comprar alguma coisa pela internet, mas não quer que a loja saiba onde você mora. Então você pede para um amigo fazer a compra para você.

O processo fica assim:

```
Você → Seu amigo → Loja
```

A loja conversa apenas com seu amigo. Ela não sabe quem realmente fez o pedido.

Um proxy funciona exatamente assim:

```
Seu computador → Proxy → Internet
```

O proxy fica no meio da comunicação entre você e o site.

---

## Exemplo do dia a dia

Imagine que você quer acessar o Google.

**Sem proxy:**

```
Seu computador ---------------> Google
```

O Google vê diretamente o seu endereço IP.

**Com proxy:**

```
Seu computador ---> Proxy ---> Google
                       |
                  recebe a resposta
                       |
Seu computador <-------
```

Agora o Google vê apenas o IP do proxy, não o seu.

---

## Para que serve um proxy?

### 1. Esconder seu IP

Os sites enxergam o IP do proxy em vez do seu.

**Exemplo:**

| | |
|---|---|
| Seu IP | 189.25.10.30 |
| IP do Proxy | 200.150.50.12 |

O site pensa que quem acessou foi o proxy.

### 2. Bloquear sites

Empresas usam proxy para impedir acesso a determinados sites.

**Exemplo:**

Você tenta acessar `youtube.com`. O pedido passa pelo proxy, que verifica: *"Esse site é permitido?"*

- ✅ Sim → libera.
- ❌ Não → bloqueia.

### 3. Aumentar a velocidade (Cache)

Imagine que 100 funcionários acessam o mesmo site.

**Sem proxy:**

```
Funcionário 1 → Internet
Funcionário 2 → Internet
Funcionário 3 → Internet
...
```

**Com proxy:**

1. O primeiro acessa o site.
2. O proxy guarda uma cópia (cache).
3. Os próximos recebem essa cópia sem precisar buscar novamente na internet.

**Resultado:**
- Internet mais rápida.
- Menos consumo de banda.

### 4. Monitorar acessos

O proxy pode registrar tudo o que os usuários acessam.

**Exemplo:**

| Horário | Usuário | Site |
|---------|---------|------|
| 08:00 | João | google.com |
| 08:05 | Maria | youtube.com |
| 08:10 | Pedro | gmail.com |

Assim, a empresa consegue acompanhar o uso da internet.

---

## Exemplo em uma empresa

Imagine um escritório com 50 computadores. Todos acessam a internet assim:

```
PC1
PC2      \
PC3       \
           Proxy
             │
          Firewall
             │
          Internet
```

Todos os acessos passam primeiro pelo proxy.

---

## Proxy × VPN

Essa é uma dúvida muito comum.

| Proxy | VPN |
|-------|-----|
| Esconde o IP em algumas conexões ou aplicativos | Criptografa praticamente todo o tráfego do dispositivo |
| Geralmente mais rápido | Pode ser um pouco mais lenta devido à criptografia |
| Muito usado em empresas para controle de acesso | Muito usada para privacidade e segurança |

---

## Como lembrar na prova

Pense nesta frase:

> **Proxy = intermediário.**

Sempre que ouvir "proxy", lembre-se de alguém que fica entre o usuário e a internet, podendo:

- esconder o IP;
- bloquear sites;
- armazenar páginas em cache;
- controlar e registrar acessos.

---

## Resumo em uma frase

> Um proxy é um servidor intermediário que recebe as requisições do usuário, decide o que fazer com elas (permitir, bloquear ou armazenar em cache) e depois as envia para a internet.