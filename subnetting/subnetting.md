# Subnetting

Subnetting é o processo de dividir uma rede grande em redes menores, chamadas de **sub-redes**.

Imagine uma empresa com 100 computadores. Em vez de colocar todos na mesma rede, podemos separar:

```
Rede principal
      ↓
 ┌────┴────┐
RH       TI       Financeiro
30 PCs    40 PCs    30 PCs
```

Isso ajuda na organização, segurança e gerenciamento da rede.

---

## 1. Prefixo

O prefixo indica quantos bits do endereço IP pertencem à rede.

**Exemplo:**

```
192.168.1.0/24
```

O `/24` é o prefixo.

IPv4 possui 32 bits:

```
11111111.11111111.11111111.00000000
←──── 24 ────→ ←── 8 ──→
    REDE          HOST
```

Portanto:

```
/24 = 24 bits para rede
       8 bits para hosts
```

---

## 2. Máscara

O prefixo `/24` corresponde à máscara `255.255.255.0`.

Alguns exemplos importantes:

| Prefixo | Máscara |
|---------|---------|
| /8 | 255.0.0.0 |
| /16 | 255.255.0.0 |
| /24 | 255.255.255.0 |
| /25 | 255.255.255.128 |
| /26 | 255.255.255.192 |
| /27 | 255.255.255.224 |
| /28 | 255.255.255.240 |
| /29 | 255.255.255.248 |
| /30 | 255.255.255.252 |

Você não precisa decorar tudo de uma vez. Com prática, você começa a reconhecer os valores.

---

## 3. Quantidade de hosts

Essa é uma das contas mais importantes do subnetting.

A fórmula é:

```
Hosts = 2ⁿ - 2
```

Onde **n** = quantidade de bits disponíveis para hosts.

### Exemplo: /24

IPv4 tem 32 bits.

```
32 - 24 = 8
```

Temos 8 bits para hosts:

```
2⁸ - 2
= 256 - 2
= 254 hosts
```

Então: `/24 → 254 hosts`

### Exemplos

| Prefixo | Bits de host | Hosts disponíveis |
|---------|---------------|--------------------|
| /24 | 8 | 254 |
| /25 | 7 | 126 |
| /26 | 6 | 62 |
| /27 | 5 | 30 |
| /28 | 4 | 14 |
| /29 | 3 | 6 |
| /30 | 2 | 2 |

📌 O `-2` acontece porque normalmente temos:
- 1 endereço para identificar a rede
- 1 endereço para broadcast

---

## 4. Calcular sub-redes

Agora vem a parte mais interessante.

Imagine:

```
192.168.1.0/24
```

Queremos dividir essa rede em 4 sub-redes.

Precisamos pegar bits que eram destinados aos hosts e transformá-los em bits de rede.

Para descobrir quantos bits precisamos:

```
2ⁿ ≥ quantidade de sub-redes
```

Queremos 4:

```
2² = 4
```

Então precisamos pegar 2 bits.

O prefixo passa de `/24` para `/26`.

A máscara passa a ser:

```
255.255.255.192
```

E teremos: **4 sub-redes, cada uma com 62 hosts disponíveis.**

---

## 5. Exemplo completo

Vamos dividir `192.168.1.0/24` em 4 sub-redes.

**Resultado:**

### Sub-rede 1 — `192.168.1.0/26`
- Rede: `192.168.1.0`
- Hosts: `192.168.1.1` – `192.168.1.62`
- Broadcast: `192.168.1.63`

### Sub-rede 2 — `192.168.1.64/26`
- Rede: `192.168.1.64`
- Hosts: `192.168.1.65` – `192.168.1.126`
- Broadcast: `192.168.1.127`

### Sub-rede 3 — `192.168.1.128/26`
- Rede: `192.168.1.128`
- Hosts: `192.168.1.129` – `192.168.1.190`
- Broadcast: `192.168.1.191`

### Sub-rede 4 — `192.168.1.192/26`
- Rede: `192.168.1.192`
- Hosts: `192.168.1.193` – `192.168.1.254`
- Broadcast: `192.168.1.255`

---

## 🧠 O segredo: tamanho do bloco

Para descobrir onde começa cada sub-rede, podemos calcular:

```
256 - valor da máscara
```

No `/26`:

```
Máscara: 255.255.255.192
256 - 192 = 64
```

Então as redes começam de 64 em 64:

```
0
64
128
192
```

Pronto! Temos as 4 sub-redes.

---

## 📚 O que você precisa saber de Subnetting

Para estudar redes para infraestrutura, recomenda-se dominar nesta ordem:

```
1️⃣ Prefixo
/24, /25, /26, /27...
     ↓
2️⃣ Máscara
/24 → 255.255.255.0
/25 → 255.255.255.128
/26 → 255.255.255.192
     ↓
3️⃣ Quantidade de hosts
2ⁿ - 2
     ↓
4️⃣ Quantidade de sub-redes
2ⁿ
     ↓
5️⃣ Endereço da rede
Exemplo: 192.168.1.64
     ↓
6️⃣ Faixa de hosts
192.168.1.65 até 192.168.1.126
     ↓
7️⃣ Broadcast
192.168.1.127
```

---

## 🎯 Resumo para decorar

```
SUBNETTING
     │
     ├── Prefixo → /24
     │
     ├── Máscara → 255.255.255.0
     │
     ├── Hosts → 2ⁿ - 2
     │
     ├── Sub-redes → 2ⁿ
     │
     ├── Rede → primeiro endereço
     │
     └── Broadcast → último endereço
```

**Exemplo que vale muito a pena saber:**

```
192.168.1.0/26

Máscara:         255.255.255.192
Sub-redes:       4
Hosts/sub-rede:  62

Rede 1:          192.168.1.0
Hosts:           .1 até .62
Broadcast:       .63
```