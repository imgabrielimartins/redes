# 🌐 Equipamentos de Rede

## 🔌 Hub

### Como funciona

O Hub é um equipamento que conecta vários dispositivos em uma rede.

Quando recebe uma informação, ele envia para todos os dispositivos conectados, sem saber qual é o verdadeiro destinatário.

**Exemplo:**

```
Computador A → Hub → Computadores A, B, C e D
```

Todos recebem a informação, mas somente o destinatário correto utiliza.

📌 **Importante:** Hub é antigo e pouco eficiente. Hoje, normalmente usamos Switch no lugar dele.

**Para lembrar:** Hub = manda para todo mundo.

---

## 🔀 Switch

O Switch também conecta vários dispositivos, mas é muito mais inteligente que o Hub.

### Camada 2

O Switch trabalha principalmente na Camada 2 (Enlace) do modelo OSI.

Ele utiliza o endereço MAC dos dispositivos para saber para onde enviar os dados.

### Tabela MAC

O Switch cria uma tabela associando MAC → Porta.

**Exemplo:**

| MAC | Porta |
|-----|-------|
| AA:AA:AA | 1 |
| BB:BB:BB | 2 |
| CC:CC:CC | 3 |

Assim, quando recebe um pacote destinado ao MAC `BB:BB:BB`, ele sabe que deve enviar pela porta 2.

### VLAN

VLAN significa *Virtual LAN*.

Ela permite dividir uma rede física em redes lógicas separadas.

**Exemplo:**

```
Switch
├── VLAN 10 → Financeiro
├── VLAN 20 → RH
└── VLAN 30 → TI
```

Mesmo estando conectados ao mesmo Switch, os grupos podem ficar separados logicamente.

**Para lembrar:** Switch = usa MAC e envia para o dispositivo certo.

---

## 🌐 Roteador

O Roteador conecta redes diferentes.

**Por exemplo:**

```
Rede da sua casa
       ↓
   Roteador
       ↓
    Internet
```

### Roteamento

O roteador decide qual caminho os dados devem seguir para chegar ao destino. Ele utiliza endereços IP para fazer isso.

```
Switch    → MAC
Roteador  → IP
```

### Gateway

O Gateway é a "porta de saída" da sua rede.

**Por exemplo:**

```
PC → Switch → Roteador/Gateway → Internet
```

Se seu computador precisa acessar algo fora da sua rede, normalmente envia os dados para o gateway padrão.

### NAT

NAT (Network Address Translation) permite que vários dispositivos da sua rede privada compartilhem um IP público para acessar a Internet.

**Exemplo:**

```
PC       192.168.1.10 ┐
Celular  192.168.1.11 ├── Roteador → IP público → Internet
TV       192.168.1.12 ┘
```

**Para lembrar:** Roteador = conecta redes e trabalha com IP.

---

## 📡 Access Point (AP)

O Access Point permite que dispositivos se conectem à rede sem usar cabo, através do Wi-Fi.

**Exemplo:**

```
Internet
   ↓
Roteador
   ↓
Switch
   ↓
Access Point
   ↓
📱 Celular
💻 Notebook
📺 TV
```

O AP transforma uma conexão de rede cabeada em uma rede Wi-Fi.

📌 Em muitas redes domésticas, o roteador já possui um Access Point integrado.

**Para lembrar:** Access Point = fornece Wi-Fi.

---

## 📶 Modem

O Modem faz a comunicação entre a sua rede e a tecnologia utilizada pela operadora.

Ele recebe o sinal da operadora e o converte para que os equipamentos da sua rede possam utilizá-lo.

**Exemplo:**

```
Operadora
    ↓
  Modem
    ↓
 Roteador
    ↓
  Sua rede
```

Dependendo da tecnologia e do equipamento fornecido pela operadora, modem e roteador podem estar no mesmo aparelho.

**Para lembrar:** Modem = faz a ligação com a operadora.

---

## 🛡️ Firewall

O Firewall funciona como uma espécie de segurança da rede.

Ele analisa o tráfego e pode permitir ou bloquear conexões de acordo com regras.

**Exemplo:**

```
Internet
   ↓
🔥 Firewall
   ↓
Rede interna
```

Uma regra poderia ser:

```
Permitir → HTTPS (443)
Bloquear → determinada conexão
Permitir → acesso de um servidor específico
```

Firewall pode existir em:

- Roteadores
- Servidores
- Computadores
- Equipamentos de rede
- Firewalls dedicados

**Para lembrar:** Firewall = controla e protege o tráfego da rede.

---

## 🧠 Resumo para decorar

| Equipamento | Função principal | Lembrete |
|-------------|-------------------|----------|
| Hub | Envia dados para todos | 📢 Todos |
| Switch | Conecta dispositivos usando MAC | 🔀 MAC |
| Roteador | Conecta redes usando IP | 🌐 IP |
| Access Point | Fornece Wi-Fi | 📡 Wi-Fi |
| Modem | Faz a comunicação com a operadora | 📶 Operadora |
| Firewall | Controla e bloqueia tráfego | 🛡️ Segurança |

**Uma forma fácil de visualizar:**

```
              INTERNET
                  │
               Modem
                  │
              Firewall
                  │
              Roteador
                  │
               Switch
            ┌─────┼─────┐
            │     │     │
           PC  Servidor  AP
                          │
                     📱 💻 📺
```

Se você está estudando Redes para trabalhar com Infra, decore principalmente esta sequência:

> Hub → Switch → Roteador → Access Point → Modem → Firewall

E as associações:

- Switch = MAC
- Roteador = IP
- Gateway = saída da rede
- NAT = IP privado ↔ IP público
- AP = Wi-Fi
- Firewall = segurança