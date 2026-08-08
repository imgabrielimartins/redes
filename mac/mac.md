# MAC Address

O MAC Address é o endereço físico/lógico usado para identificar uma interface de rede dentro de uma rede local.

Se o IP identifica o dispositivo na rede, o MAC identifica a interface de rede.

---

## 1. O que é MAC Address?

**MAC** significa *Media Access Control*.

É um endereço formado normalmente por 48 bits, representado por 12 caracteres hexadecimais.

**Exemplo:**

```
00:1A:2B:3C:4D:5E
```

Ou:

```
00-1A-2B-3C-4D-5E
```

Cada placa de rede possui um MAC Address. Por exemplo:

```
Notebook
   │
   └── Placa Wi-Fi
          ↓
    MAC: AA:BB:CC:11:22:33
```

Um computador pode ter mais de um MAC, porque pode possuir diferentes interfaces de rede:

- Wi-Fi → MAC 1
- Ethernet → MAC 2
- Bluetooth → MAC 3

---

## 2. Como funciona?

O MAC é utilizado principalmente na rede local (LAN) para que os dispositivos consigam entregar os quadros ao destino correto.

Imagine:

```
Notebook A
MAC: AA:AA:AA
     │
     ↓
   Switch
     │
     ↓
Notebook B
MAC: BB:BB:BB
```

O switch aprende quais MACs estão conectados em quais portas. Por exemplo:

| MAC | Porta |
|-----|-------|
| AA:AA:AA | 1 |
| BB:BB:BB | 2 |
| CC:CC:CC | 3 |

Se o Notebook A quiser enviar dados para o Notebook B, o switch pode encaminhar o quadro diretamente para a porta 2.

📌 Switch trabalha principalmente com MAC Addresses.

---

## 3. Diferença entre MAC e IP

Essa é uma diferença muito importante em redes.

| MAC Address | IP Address |
|-------------|------------|
| Identifica uma interface de rede | Identifica um dispositivo/interface em uma rede |
| Usado principalmente na rede local | Usado para comunicação entre redes |
| Camada 2 | Camada 3 |
| Trabalha com switches | Roteadores trabalham com IP |
| Exemplo: AA:BB:CC:11:22:33 | Exemplo: 192.168.1.10 |

### Uma analogia simples

Imagine uma cidade:

- 🏠 **IP** = endereço da casa
- 📦 **MAC** = identificação da pessoa/placa que vai receber a entrega

O IP ajuda a descobrir para qual rede/dispositivo os dados devem ir. O MAC é utilizado para fazer a entrega dentro da rede local.

---

## 4. E o ARP?

Aqui entra uma parte muito importante.

**ARP** = *Address Resolution Protocol*.

Ele serve para descobrir: *"Qual MAC Address corresponde a este endereço IP?"*

### Exemplo

Seu computador sabe que quer enviar algo para:

```
IP: 192.168.1.20
```

Mas ele precisa descobrir o MAC desse dispositivo. Então ele faz uma pergunta na rede:

> 📢 "Quem possui o IP 192.168.1.20?"

O dispositivo que possui esse IP responde:

> "Sou eu! Meu MAC é AA:BB:CC:11:22:33"

Então o computador guarda essa informação temporariamente:

```
192.168.1.20
      ↓
AA:BB:CC:11:22:33
```

Essa informação fica na tabela/cache ARP.

---

## 🔄 Exemplo completo

Imagine:

```
Notebook
IP: 192.168.1.10
MAC: AA:AA:AA
       │
       ↓
    Switch
       │
       ↓
PC
IP: 192.168.1.20
MAC: BB:BB:BB
```

O notebook quer conversar com o PC.

1. Ele sabe o IP: `192.168.1.20`
2. Mas não sabe o MAC. Então utiliza ARP: *"📢 Quem tem 192.168.1.20?"*
3. O PC responde: *"Meu IP é 192.168.1.20, meu MAC é BB:BB:BB"*
4. O notebook aprende: `192.168.1.20 → BB:BB:BB`
5. O switch usa o MAC para encaminhar o quadro.

---

## 🧠 Para memorizar

```
IP
↓
"Para onde quero ir?"

ARP
↓
"Qual MAC corresponde a esse IP?"

MAC
↓
"Qual interface deve receber?"

Switch
↓
"Por qual porta devo enviar?"
```

---

## Resumo

- **MAC Address:** identifica a interface de rede na comunicação local.
- **IP:** identifica o endereço lógico usado para comunicação em redes.
- **ARP:** descobre o MAC associado a um IP dentro da rede local.
- **Switch:** usa principalmente MAC Address para encaminhar quadros.

⭐ Uma frase ótima para entrevista:

> "O ARP resolve um endereço IPv4 em um endereço MAC dentro da rede local."