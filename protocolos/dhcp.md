# DHCP — Portas 67 e 68 📡

**DHCP** significa *Dynamic Host Configuration Protocol* e serve para configurar automaticamente um dispositivo na rede.

Quando você conecta seu notebook ao Wi-Fi, ele precisa receber informações como:

```
IP:       192.168.1.20
Máscara:  255.255.255.0
Gateway:  192.168.1.1
DNS:      192.168.1.1
```

Você normalmente não precisa colocar tudo isso manualmente. O DHCP faz isso para você.

Funciona mais ou menos assim:

```
Notebook
   ↓
"Preciso de um IP!"
   ↓
DHCP
   ↓
"Pode usar 192.168.1.20"
```

---

## O processo completo (DORA)

Por trás desse "pedido e resposta" simples, existe uma sequência de 4 etapas, conhecida pela sigla **DORA**:

```
Notebook                              Servidor DHCP
   │                                        │
   │── 1. Discover ──────────────────────▶ │  "Alguém tem um IP pra mim?"
   │                                        │
   │◀── 2. Offer ─────────────────────────│  "Pode usar 192.168.1.20"
   │                                        │
   │── 3. Request ────────────────────────▶│  "Ok, quero esse IP mesmo"
   │                                        │
   │◀── 4. Acknowledge (ACK) ──────────────│  "Confirmado, é seu"
```

1. **Discover** → o dispositivo entra na rede e "grita" perguntando se existe um servidor DHCP por perto.
2. **Offer** → o servidor responde oferecendo um IP disponível.
3. **Request** → o dispositivo confirma que aceita aquele IP.
4. **Acknowledge (ACK)** → o servidor confirma a entrega e envia as demais configurações (máscara, gateway, DNS).

---

## Tempo de concessão (lease time)

O IP entregue pelo DHCP não é seu para sempre — ele é **emprestado** por um período determinado, chamado **lease time**.

- Quando esse tempo está acabando, o dispositivo tenta renovar o mesmo IP.
- Se o dispositivo ficar muito tempo fora da rede, esse IP pode ser liberado e entregue para outro dispositivo depois.

Isso é útil em redes com muitos dispositivos entrando e saindo, como redes de escritório ou Wi-Fi público.

---

## Portas

- `67` → servidor DHCP
- `68` → cliente DHCP

---

## 🧠 Para lembrar

**DHCP = entrega configuração de rede → 67/68**

- Segue o processo DORA: Discover, Offer, Request, Acknowledge
- O IP entregue é temporário (lease time), não fixo
- Evita que você precise configurar IP, máscara, gateway e DNS manualmente