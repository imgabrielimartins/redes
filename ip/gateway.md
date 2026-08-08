# Gateway 🌐

O gateway é o dispositivo que funciona como uma "porta de saída" da sua rede.

Na maioria das redes domésticas, o gateway é o **roteador**.

---

## 🏠 Exemplo simples

Imagine sua rede:

```
Notebook
192.168.1.10
       │
       ↓
Roteador
192.168.1.1  ← Gateway
       │
       ↓
    Internet
```

Seu notebook está na rede `192.168.1.0`. Quando ele quer acessar algo fora dessa rede, ele manda os dados para o gateway:

```
Notebook
192.168.1.10
     ↓
Gateway
192.168.1.1
     ↓
Internet
```

---

## Por que ele é necessário?

Imagine que você queira acessar:

```
Google
142.250.x.x
```

Seu computador percebe: *"Esse endereço não pertence à minha rede."*

Então ele envia os dados para o gateway, que sabe como encaminhá-los para outras redes.

---

## 📌 Exemplo completo

```
IP:       192.168.1.10
Máscara:  255.255.255.0
Gateway:  192.168.1.1
```

- **IP** → identifica seu computador
- **Máscara** → identifica qual é a sua rede
- **Gateway** → caminho para sair da sua rede
- **DNS** → transforma nomes como `google.com` em IPs

---

## 🧠 Para memorizar

🚪 **Gateway = porta de saída da rede**

Uma analogia boa:

- Seu computador = sua casa 🏠
- Sua rede = seu bairro 🏘️
- Gateway = saída do bairro 🚪
- Internet = resto da cidade/mundo 🌎