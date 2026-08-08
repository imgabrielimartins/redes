# DNS — Porta 53 🌎

DNS é um dos protocolos mais importantes de toda a Internet.

**DNS** significa *Domain Name System*.

Sua função é transformar:

```
nome → endereço IP
```

**Por exemplo:**

```
google.com
     ↓
    DNS
     ↓
IP do servidor
```

---

## Por que precisamos disso?

Porque seria muito difícil decorar:

```
142.250.xxx.xxx
```

para cada site.

É muito mais fácil lembrar:

```
google.com
```

---

## Como a busca acontece na prática

Quando você digita um endereço no navegador, o dispositivo geralmente não pergunta direto ao "dono" do site — ele passa por uma pequena cadeia de consultas até achar a resposta:

```
Seu PC
   │
   ▼
Servidor DNS (do provedor ou 8.8.8.8, por exemplo)
   │
   ├── já sabe a resposta? → devolve na hora (cache)
   │
   └── não sabe?
          │
          ▼
     Consulta servidores DNS raiz/autoritativos
          │
          ▼
     Descobre o IP e devolve para você
```

Esse processo costuma ser muito rápido (poucos milissegundos), em parte porque os resultados ficam guardados em **cache** por um tempo, evitando repetir a consulta inteira toda vez.

---

## Tipos de registro DNS mais comuns

O DNS não guarda só o IP de um site — ele armazena vários tipos de informação, chamados **registros**:

| Registro | Para que serve |
|----------|-----------------|
| A | Aponta um nome de domínio para um IP (IPv4) |
| AAAA | Igual ao A, mas para IPv6 |
| CNAME | Aponta um nome de domínio para outro nome (um "apelido") |
| MX | Indica qual servidor recebe e-mails daquele domínio |
| TXT | Armazena informações em texto (usado para verificações e segurança) |

---

## Porta

`53`

DNS normalmente utiliza UDP 53, mas também pode utilizar TCP 53 em situações específicas (como consultas maiores ou transferências de zona entre servidores DNS).

---

## 🧠 Para lembrar

**DNS = transforma nome em IP → 53**

- Funciona em cadeia: seu PC pergunta ao servidor DNS, que pode perguntar a outros
- Usa cache para responder mais rápido
- Guarda diferentes tipos de registro (A, AAAA, CNAME, MX, TXT...)