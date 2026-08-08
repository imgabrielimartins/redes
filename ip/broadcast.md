# Broadcast 📢

O broadcast é uma forma de enviar uma mensagem para todos os dispositivos de uma mesma rede ao mesmo tempo.

Pensa em um alto-falante em uma sala:

> 📢 "Atenção, todo mundo da sala!"

Todos que estão naquela rede recebem a mensagem.

---

## Exemplo

Imagine esta rede:

```
Rede:      192.168.1.0
Máscara:   255.255.255.0 (/24)
```

Os dispositivos podem ser:

```
192.168.1.1  → Roteador
192.168.1.2  → Notebook
192.168.1.3  → Celular
192.168.1.4  → TV
...
```

O endereço de broadcast dessa rede é:

```
192.168.1.255
```

Quando um dispositivo envia algo para:

```
192.168.1.255
```

a mensagem é destinada a todos os dispositivos daquela rede.

---

## 📌 Os três endereços importantes

Em uma rede `/24`:

```
192.168.1.0    → Endereço da rede
192.168.1.1    → Primeiro IP disponível para dispositivo
...
192.168.1.254  → Último IP disponível
192.168.1.255  → Broadcast
```

⚠️ `192.168.1.0` e `192.168.1.255` normalmente não são usados para dispositivos nessa rede, porque representam a rede e o broadcast.

---

## 🧠 Para decorar

- **IP da rede** → identifica a rede 🏠
- **IP do dispositivo** → identifica um dispositivo 💻
- **Gateway** → saída da rede 🚪
- **Broadcast** → fala com todos 📢

**Broadcast = "enviar para todos os dispositivos da minha rede."**