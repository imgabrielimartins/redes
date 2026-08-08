# IP Público e IP Privado

## 1. IP Público 🌍

O IP público é o endereço que identifica sua rede na internet. É como o endereço da sua casa: qualquer site ou serviço na internet vê esse endereço quando você se conecta.

### Exemplo

Imagine que sua casa tenha vários dispositivos:

- Notebook
- Celular
- Smart TV

Todos acessam a internet usando o mesmo IP público, fornecido pelo seu provedor (Claro, Vivo, Oi, etc.).

**Exemplo de IP público:**

```
179.184.52.10
```

### Características

- É único na internet.
- É fornecido pelo provedor de internet.
- Pode ser visto por sites que você acessa.
- Pode ser fixo ou mudar de tempos em tempos (IP dinâmico).

### Analogia

🏠 **IP Público = Endereço da casa**

Quem quer enviar uma carta precisa saber o endereço da sua casa.

---

## 2. IP Privado 🏡

O IP privado é usado apenas dentro da sua rede local (Wi-Fi ou empresa). Ele identifica cada dispositivo conectado ao roteador.

**Exemplo:**

```
Notebook → 192.168.0.10
Celular  → 192.168.0.15
TV       → 192.168.0.20
```

Esses IPs não aparecem na internet. Eles só existem dentro da sua rede.

### Faixas de IP privado

As três faixas reservadas são:

- `10.0.0.0` até `10.255.255.255`
- `172.16.0.0` até `172.31.255.255`
- `192.168.0.0` até `192.168.255.255`

O mais comum em casas é:

```
192.168.0.x
```
ou
```
192.168.1.x
```

### Analogia

🏠 **IP Privado = Número de cada quarto da casa**

A casa tem um único endereço (IP público), mas cada cômodo ou morador pode ser identificado internamente.

---

## Como eles trabalham juntos

Imagine esta rede:

```
Internet
     │
IP Público
200.180.50.12
     │
 Roteador
     │
 ┌───────────────────────┐
 │                        │
Notebook   192.168.0.2
Celular    192.168.0.3
TV         192.168.0.4
```

- A internet conhece apenas o IP público (`200.180.50.12`).
- Dentro da rede, cada dispositivo possui um IP privado diferente.
- O roteador faz a "tradução" entre os IPs privados e o IP público usando uma técnica chamada **NAT** (Network Address Translation).

---

## Resumo

| IP Público | IP Privado |
|------------|------------|
| Identifica sua rede na internet | Identifica dispositivos dentro da rede local |
| É único na internet | Pode ser repetido em outras redes |
| Fornecido pelo provedor | Atribuído pelo roteador (geralmente via DHCP) |
| Exemplo: 179.184.52.10 | Exemplo: 192.168.1.10 |
| Visível na internet | Não é visível diretamente na internet |

---

## Para memorizar

- 🌍 **IP Público** = Internet = Endereço da casa
- 🏡 **IP Privado** = Rede local = Número do quarto