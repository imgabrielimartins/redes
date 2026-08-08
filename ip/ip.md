# Endereçamento IP

O endereço IP (Internet Protocol) é como o endereço da sua casa, mas para dispositivos conectados à rede. Ele permite que computadores, celulares, impressoras e servidores se encontrem e troquem informações.

---

## 1. IPv4

O IPv4 é a versão mais utilizada do protocolo IP. Ele possui 32 bits, divididos em 4 números separados por pontos.

**Exemplo:**

```
192.168.1.10
```

Cada número pode variar de 0 a 255.

**Características:**

- 32 bits
- Aproximadamente 4,3 bilhões de endereços
- Ainda é o mais usado atualmente

**Exemplos de IPs IPv4:**

- `8.8.8.8`
- `192.168.0.15`
- `10.0.0.25`
- `172.16.1.100`

---

## 2. IPv6

O IPv6 foi criado porque os endereços IPv4 estão se esgotando. Possui 128 bits, permitindo uma quantidade enorme de endereços.

**Exemplo:**

```
2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

Pode ser abreviado:

```
2001:db8:85a3::8a2e:370:7334
```

**Características:**

- 128 bits
- Trilhões de trilhões de endereços
- Mais segurança
- Melhor desempenho em algumas situações

---

## 3. IP Público

É o endereço que identifica sua rede na Internet. Seu provedor (Claro, Vivo, Oi...) entrega esse IP.

**Exemplo:**

```
177.45.100.10
```

Todos os sites enxergam esse IP.

**Pense assim:** sua casa possui um único endereço. Toda correspondência chega nesse endereço. O IP público funciona da mesma forma.

---

## 4. IP Privado

É usado apenas dentro da rede local.

**Exemplo:**

```
192.168.1.20
```

Seu notebook, celular e TV possuem IPs privados diferentes.

**Faixas privadas:**

| Faixa | Exemplo |
|-------|---------|
| 10.0.0.0/8 | 10.0.0.5 |
| 172.16.0.0/12 | 172.16.5.20 |
| 192.168.0.0/16 | 192.168.1.30 |

Esses IPs não funcionam diretamente na Internet.

---

## 5. Máscara de Rede

A máscara informa:

- Qual parte do IP representa a **rede**
- Qual parte representa o **dispositivo (host)**

**Exemplo:**

| | |
|---|---|
| IP | 192.168.1.10 |
| Máscara | 255.255.255.0 |

Significa que:

- **Rede:** 192.168.1
- **Host:** 10

Todos os dispositivos que possuem `192.168.1.x` estão na mesma rede.

**Máscaras comuns:**

| Máscara | CIDR |
|---------|------|
| 255.0.0.0 | /8 |
| 255.255.0.0 | /16 |
| 255.255.255.0 | /24 |

---

## 6. Gateway

O gateway é a porta de saída da rede. Quando seu computador quer acessar um site, ele envia os dados para o gateway. Normalmente o gateway é o roteador.

**Exemplo:**

```
Gateway: 192.168.1.1
```

**Fluxo:**

```
Computador
      ↓
Gateway (roteador)
      ↓
Internet
```

Sem gateway configurado, você consegue conversar apenas com dispositivos da mesma rede.

---

## 7. Broadcast

É um endereço usado para enviar uma mensagem para todos os dispositivos da rede ao mesmo tempo.

**Exemplo:**

| | |
|---|---|
| Rede | 192.168.1.0/24 |
| Broadcast | 192.168.1.255 |

Se um computador enviar um pacote para esse endereço, todos os dispositivos da rede recebem.

É muito usado para:

- Descobrir dispositivos na rede.
- Protocolos como DHCP.
- Alguns serviços de compartilhamento.

---

## Exemplo completo

Imagine uma empresa com estas configurações:

| Parâmetro | Valor |
|-----------|-------|
| IP | 192.168.1.10 |
| Máscara | 255.255.255.0 |
| Gateway | 192.168.1.1 |
| Broadcast | 192.168.1.255 |

O computador:

- Tem o IP `192.168.1.10`.
- Está na rede `192.168.1.0/24`.
- Usa o roteador `192.168.1.1` para acessar a Internet.
- Pode enviar mensagens para todos da rede usando `192.168.1.255`.

---

## Resumo para decorar

| Conceito | O que é? | Exemplo |
|----------|----------|---------|
| IPv4 | Endereço IP de 32 bits | 192.168.1.10 |
| IPv6 | Endereço IP de 128 bits | 2001:db8::1 |
| IP Público | Endereço visível na Internet | 177.45.100.10 |
| IP Privado | Endereço usado na rede local | 192.168.1.20 |
| Máscara de Rede | Define rede e host | 255.255.255.0 (/24) |
| Gateway | Roteador que conecta à Internet | 192.168.1.1 |
| Broadcast | Envia mensagem para todos da rede | 192.168.1.255 |