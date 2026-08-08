# RDP — Porta 3389 🖥️

**RDP** significa *Remote Desktop Protocol*.

Ele permite acessar remotamente a **interface gráfica** de um computador Windows.

Por exemplo, você está no seu computador:

```
💻 Seu PC
    ↓
   RDP
    ↓
🖥️ Servidor Windows
```

Uma janela é aberta mostrando a área de trabalho do computador remoto.

Você consegue:

- abrir programas;
- acessar arquivos;
- configurar o Windows;
- administrar o servidor.

---

## RDP x SSH

Essa comparação ajuda a fixar bem quando usar cada um:

| | RDP | SSH |
|---|-----|-----|
| O que você vê | Interface gráfica completa | Apenas terminal (linha de comando) |
| Sistema típico | Windows | Linux (mas também funciona em Windows) |
| Uso de rede | Mais pesado (transmite imagem da tela) | Mais leve (transmite apenas texto) |
| Porta | 3389 | 22 |

Ou seja: se você precisa clicar em ícones, abrir janelas e usar o mouse, é RDP. Se você só precisa digitar comandos, SSH costuma ser mais rápido e leve.

---

## Como funciona por trás dos panos

O RDP basicamente transmite:

```
Servidor Windows                    Seu PC
      │                                │
      │── Captura tela ──────────────▶ │  Você vê a imagem da área de trabalho
      │                                │
      │◀── Envia cliques e teclas ─────│  Você controla o mouse/teclado
```

O servidor faz o processamento pesado (roda os programas), e o seu computador só precisa exibir a imagem e enviar seus comandos de mouse/teclado — por isso o RDP é muito usado para acessar máquinas mais potentes a partir de dispositivos mais simples.

---

## Cuidados de segurança

Como o RDP dá acesso total à área de trabalho, ele é um alvo comum de ataques quando exposto diretamente à internet sem proteção. Algumas boas práticas comuns em ambientes corporativos:

- Não expor a porta `3389` diretamente na internet
- Usar VPN para acessar o RDP apenas dentro de uma rede protegida
- Ativar autenticação em duas etapas quando disponível
- Limitar quais usuários/IPs podem se conectar

---

## Porta

`3389`

---

## 🧠 Para lembrar

**RDP = acessar Windows remotamente → 3389**

- Mostra a interface gráfica completa, não só o terminal
- Mais pesado que SSH, pois transmite imagem da tela
- Exige cuidado extra de segurança quando exposto à internet