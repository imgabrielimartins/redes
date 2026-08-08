# HTTPS — Porta 443 🔒

**HTTPS** (*HyperText Transfer Protocol Secure*) é basicamente o HTTP com uma camada de segurança através do **TLS** (*Transport Layer Security*).

Ele criptografa a comunicação entre você e o servidor, garantindo que os dados não possam ser lidos por quem estiver "no meio do caminho".

```
Você
 ↓
🔒 HTTPS
 ↓
Servidor
```

---

## Comparando com o HTTP

Imagine que você está enviando uma mensagem com sua senha:

**Com HTTP:**

```
"Minha senha é 123456"
```

A mensagem trafega em texto puro. Qualquer pessoa capturando o tráfego da rede consegue ler exatamente isso.

**Com HTTPS:**

```
"x9F2#kL8@qP1zR..."
```

Os dados são embaralhados por criptografia. Mesmo que alguém intercepte a comunicação, não consegue entender o conteúdo sem a chave correta.

---

## O que o HTTPS garante?

O HTTPS entrega três coisas principais:

- 🔐 **Confidencialidade** → os dados são criptografados, ninguém no meio consegue ler.
- ✅ **Integridade** → garante que os dados não foram alterados durante o trajeto.
- 🪪 **Autenticidade** → confirma que você está realmente falando com o servidor certo (e não com um impostor).

---

## Como funciona por trás dos panos (resumo do TLS)

Antes de trocar qualquer dado, o navegador e o servidor fazem um "aperto de mãos" chamado **TLS Handshake**:

```
Navegador                          Servidor
    │                                  │
    │──── "Olá, quero conversar" ────▶│
    │                                  │
    │◀── Envia o certificado digital ──│
    │                                  │
    │── Verifica se o certificado ────▶│
    │   é válido e confiável            │
    │                                  │
    │◀── Combinam uma chave de ───────▶│
    │    criptografia da sessão         │
    │                                  │
    │═══ Dados trafegam criptografados ═══│
```

### Certificado digital

O servidor apresenta um **certificado digital**, emitido por uma **Autoridade Certificadora (CA)**, que comprova que aquele domínio realmente pertence a quem diz ser.

É esse certificado que faz o navegador exibir o cadeado 🔒 na barra de endereços.

### Criptografia assimétrica e simétrica

O TLS combina dois tipos de criptografia:

- **Assimétrica** (chave pública/privada) → usada no início, para negociar a conexão com segurança.
- **Simétrica** (chave compartilhada) → usada depois, para criptografar os dados com mais velocidade durante toda a sessão.

---

## Exemplo

Quando você acessa:

```
https://google.com
```

está usando HTTPS. O navegador verifica o certificado do Google, negocia uma chave de criptografia e, a partir daí, todos os dados trocados (senhas, mensagens, cookies) ficam protegidos.

**Porta padrão:** `443`

---

## 🧠 Para lembrar

**HTTPS = site seguro → 443**

- HTTP + TLS = HTTPS
- Garante confidencialidade, integridade e autenticidade
- Usa certificado digital para provar identidade do servidor
- Cadeado 🔒 no navegador = conexão criptografada