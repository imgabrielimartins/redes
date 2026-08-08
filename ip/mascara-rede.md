# Máscara de rede

A máscara de rede serve para dizer qual parte do endereço IP representa a **rede** e qual parte representa o **dispositivo**.

Pensa assim:

- 🏠 **IP** = endereço completo
- 🗺️ **Máscara** = indica qual parte é a "rua/rede" e qual parte é a "casa/dispositivo"

---

## Exemplo simples

Temos:

```
IP:       192.168.1.10
Máscara:  255.255.255.0
```

A máscara indica que:

```
192.168.1  → REDE
10         → DISPOSITIVO
```

Então, nessa rede:

```
192.168.1.1   → dispositivo
192.168.1.2   → dispositivo
192.168.1.3   → dispositivo
...
192.168.1.10  → seu computador
```

Todos pertencem à mesma rede `192.168.1.0`.

---

## Por que precisamos da máscara?

Imagine que seu computador tenha:

```
IP: 192.168.1.10
Máscara: 255.255.255.0
```

Ele consegue entender que um computador com:

```
192.168.1.20
```

está na mesma rede.

Mas um computador com:

```
192.168.2.20
```

está em outra rede.

Isso é importante porque determina se o computador pode se comunicar diretamente ou se precisa passar pelo roteador/gateway.

---

## Máscara mais comum

Você vai encontrar muito:

```
255.255.255.0
```

Ela também pode ser escrita como:

```
/24
```

Então:

```
192.168.1.10/24
```

significa:

```
IP:      192.168.1.10
Máscara: 255.255.255.0
```

---

## 🧠 Para decorar

Máscara de rede = separa REDE de DISPOSITIVO.

```
192.168.1.10
███████████  █
   REDE     HOST
```