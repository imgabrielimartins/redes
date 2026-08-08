# VLAN

**VLAN** (*Virtual Local Area Network*) é uma forma de dividir uma rede física em várias redes virtuais.

Imagine uma empresa com um único switch:

```
             SWITCH
        ┌──────┼──────┐
        ↓      ↓      ↓
      RH     TI    Financeiro
```

Com VLANs, podemos separar os setores:

```
VLAN 10 → RH
VLAN 20 → TI
VLAN 30 → Financeiro
```

Mesmo estando conectados ao mesmo switch, eles ficam em redes lógicas diferentes.

---

## 🏷️ VLAN Tag

A VLAN Tag é uma identificação colocada no quadro Ethernet para indicar a qual VLAN aquele dado pertence.

O padrão mais utilizado é o **IEEE 802.1Q**.

**Exemplo:**

```
Quadro Ethernet
┌───────────────┬─────────┬──────────────┐
│ MAC origem    │ VLAN 20 │ Dados        │
└───────────────┴─────────┴──────────────┘
```

A tag informa: *"Esse quadro pertence à VLAN 20."*

📌 Importante: normalmente a tag é utilizada em links Trunk.

---

## 🔵 Access

Uma porta Access pertence a uma única VLAN.

É normalmente utilizada para conectar dispositivos finais:

- 💻 Computador
- 🖨️ Impressora
- 📞 Telefone IP
- 📷 Câmera

**Exemplo:**

```
Computador
    │
    ↓
Porta Access
VLAN 10
    │
    ↓
  Switch
```

O computador geralmente não precisa saber que está em uma VLAN. O switch associa aquela porta à VLAN.

🧠 **Pense assim:** Access = uma porta → uma VLAN

---

## 🟠 Trunk

Uma porta Trunk consegue transportar várias VLANs ao mesmo tempo.

É muito utilizada para conectar:

- Switch ↔ Switch
- Switch ↔ Roteador
- Switch ↔ Firewall
- Switch ↔ Access Point

**Exemplo:**

```
        SWITCH 1
       ┌─────────┐
       │ VLAN 10 │
       │ VLAN 20 │
       │ VLAN 30 │
       └────┬────┘
            │
          TRUNK
            │
       ┌────┴────┐
       │ SWITCH 2│
       │ VLAN 10 │
       │ VLAN 20 │
       │ VLAN 30 │
       └─────────┘
```

Nesse link, os quadros precisam ser identificados para que o outro switch saiba a qual VLAN cada quadro pertence. É aí que entra a VLAN Tag (802.1Q).

🧠 **Pense assim:** Trunk = uma porta → várias VLANs

---

## Por que separar em VLANs?

Além de organizar por setor, dividir a rede em VLANs traz benefícios concretos:

- 🔒 **Segurança** → um dispositivo do RH não consegue simplesmente "enxergar" o tráfego do Financeiro, mesmo estando no mesmo switch físico.
- 📉 **Menos tráfego desnecessário** → mensagens de broadcast de uma VLAN não se espalham para as outras, reduzindo ruído na rede.
- 🗂️ **Organização** → facilita aplicar regras diferentes (ex.: firewall, prioridade de tráfego) para cada setor.
- 💰 **Economia** → em vez de comprar um switch físico para cada setor, um único switch pode atender vários setores separados logicamente.

---

## Como o roteador entra nessa história (Router-on-a-Stick)

Como cada VLAN é uma rede separada, dispositivos de VLANs diferentes normalmente não conseguem se comunicar diretamente — é preciso um roteador (ou switch de camada 3) para rotear entre elas.

Um cenário comum é o **router-on-a-stick**: um único link Trunk conecta o switch a um roteador, que enxerga todas as VLANs e decide o que pode (ou não) trafegar entre elas.

```
        SWITCH
       ┌─────────┐
       │ VLAN 10 │
       │ VLAN 20 │
       │ VLAN 30 │
       └────┬────┘
            │
          TRUNK
            │
       ┌────┴────┐
       │ ROTEADOR │  → decide o que passa entre VLAN 10, 20 e 30
       └──────────┘
```

---

## 📌 Resumo

| Conceito | O que significa |
|----------|-------------------|
| VLAN | Divide uma rede física em redes virtuais |
| VLAN Tag | Identifica a qual VLAN o quadro pertence |
| Access | Transporta uma VLAN |
| Trunk | Transporta várias VLANs |
| 802.1Q | Padrão usado para VLAN tagging |

---

## 🧠 Para decorar

- **Access** = uma VLAN
- **Trunk** = várias VLANs
- **Tag** = identificação da VLAN
- **VLAN** = separação lógica da rede