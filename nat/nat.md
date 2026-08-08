# NAT

**NAT** (*Network Address Translation*) é uma tecnologia que traduz endereços IP.

Ele é muito usado para permitir que vários dispositivos de uma rede privada acessem a Internet usando um ou poucos IPs públicos.

---

## 🏠 Exemplo simples

Imagine sua casa:

- Celular → `192.168.1.10`
- Notebook → `192.168.1.11`
- TV → `192.168.1.12`

Esses são IPs privados.

Quando eles acessam a Internet, o roteador faz a tradução:

```
IP privado → IP público
```

Assim, os dispositivos conseguem acessar a Internet sem cada um precisar ter um IP público.

---

## Tipos de NAT

### 1. NAT (tradução simples)

Faz a tradução de um IP para outro.

**Exemplo:**

```
192.168.1.10 → 200.10.20.30
```

É uma relação mais direta entre IP privado e IP público.

### 2. PAT

**PAT** (*Port Address Translation*) é o tipo mais comum em redes domésticas.

Ele traduz:

```
IP privado + porta → IP público + porta
```

**Por exemplo:**

```
Notebook
192.168.1.10:5000
       ↓
      NAT/PAT
       ↓
200.10.20.30:6000
       ↓
    Internet
```

Isso permite que vários dispositivos usem o mesmo IP público ao mesmo tempo, diferenciados pelas portas.

---

## Como o roteador sabe para onde devolver a resposta?

Um ponto importante: quando a resposta chega da Internet, como o roteador sabe que ela é do notebook e não do celular ou da TV?

Ele mantém uma **tabela de tradução**, guardando qual porta pública corresponde a qual dispositivo/porta interna:

| IP:Porta interno | IP:Porta público |
|-------------------|--------------------|
| 192.168.1.10:5000 | 200.10.20.30:6000 |
| 192.168.1.11:5001 | 200.10.20.30:6001 |
| 192.168.1.12:5002 | 200.10.20.30:6002 |

Quando uma resposta chega em `200.10.20.30:6000`, o roteador consulta essa tabela e sabe que precisa entregá-la para `192.168.1.10:5000` — o notebook.

Isso é o que permite dezenas de dispositivos compartilharem o mesmo IP público ao mesmo tempo, sem confusão.

---

## Por que o NAT existe?

Além de economizar IPs públicos (que são limitados, especialmente em IPv4), o NAT também traz um benefício indireto de segurança: como os dispositivos internos não têm IP público próprio, eles não são diretamente alcançáveis a partir da Internet — alguém de fora não consegue simplesmente "bater na porta" do seu notebook sem que ele tenha iniciado a conexão primeiro.

---

## 🧠 Para memorizar

- **NAT** = troca o endereço IP
- **PAT** = troca IP + porta

👉 PAT é o que normalmente permite que vários dispositivos da sua casa compartilhem um único IP público.