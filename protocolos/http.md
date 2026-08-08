# HTTP — Porta 80 🌐

**HTTP** (*HyperText Transfer Protocol*) é o protocolo usado para o navegador conversar com um servidor web.

Ele define as regras de como um cliente (seu navegador) pede uma informação e como o servidor responde a esse pedido.

---

## Como funciona

Quando você entra em um site, acontece mais ou menos isso:

```
Você
 ↓
Navegador
 ↓
HTTP
 ↓
Servidor do site
```

Por exemplo, quando você acessa um site, o navegador faz uma **solicitação** (request) ao servidor:

> "Me envie a página inicial."

E o servidor devolve uma **resposta** (response):

> "Aqui está a página."

---

## O que tem dentro de uma requisição HTTP?

Toda requisição HTTP é composta basicamente por:

- **Método** → o que o cliente quer fazer (ex.: `GET`, `POST`)
- **URL** → o endereço do recurso desejado
- **Cabeçalhos (headers)** → informações extras (tipo de navegador, cookies, etc.)
- **Corpo (body)** → dados enviados, quando necessário (ex.: um formulário)

### Principais métodos HTTP

| Método | Para que serve |
|--------|-----------------|
| GET | Buscar/ler uma informação (ex.: abrir uma página) |
| POST | Enviar dados ao servidor (ex.: enviar um formulário) |
| PUT | Atualizar um recurso existente |
| DELETE | Remover um recurso |

---

## O que tem dentro de uma resposta HTTP?

O servidor responde com:

- **Código de status** → indica se deu certo ou não
- **Cabeçalhos** → informações sobre a resposta
- **Corpo** → o conteúdo em si (o HTML da página, uma imagem, um JSON, etc.)

### Códigos de status mais comuns

| Código | Significado |
|--------|--------------|
| 200 | OK — deu tudo certo |
| 301/302 | Redirecionamento |
| 404 | Página não encontrada |
| 500 | Erro interno no servidor |

---

## Exemplo prático

Você acessa:

```
http://exemplo.com
```

O navegador se comunica com o servidor usando HTTP, enviando algo como:

```
GET / HTTP/1.1
Host: exemplo.com
```

E o servidor responde com o código de status e o conteúdo da página:

```
HTTP/1.1 200 OK
Content-Type: text/html

<html>...</html>
```

**Porta padrão:** `80`

---

## O problema do HTTP

O HTTP não protege adequadamente os dados com criptografia — tudo trafega em texto puro, o que significa que qualquer pessoa no meio do caminho (por exemplo, em uma rede Wi-Fi pública) poderia ler o conteúdo.

Por isso, atualmente usamos muito mais o **HTTPS**, que é o HTTP combinado com criptografia (TLS), protegendo os dados durante a transmissão.

---

## 🧠 Para lembrar

**HTTP = comunicação com sites → porta 80**

- Sem criptografia
- Usa métodos como GET e POST
- Respostas trazem códigos de status (200, 404, 500...)
- Foi substituído, na prática, pelo HTTPS na maioria dos sites