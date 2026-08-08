# SSH — Porta 22 🖥️

**SSH** significa *Secure Shell*.

Ele permite que você acesse outro computador remotamente pelo terminal, de forma segura — toda a comunicação (comandos, senhas, dados) é criptografada.

Imagine que existe um servidor Linux em outra cidade. Você está no seu computador:

```
Seu PC
  ↓
 SSH
  ↓
Servidor Linux
```

Você consegue abrir um terminal e executar comandos no servidor.

**Por exemplo:**

```
ls
cd /var/www
mkdir teste
```

Tudo isso pode ser feito remotamente, como se você estivesse sentado na frente daquele servidor.

---

## Como funciona a conexão

Quando você digita algo como:

```
ssh usuario@servidor.com
```

acontece basicamente isso:

```
Seu PC                              Servidor
   │                                    │
   │─── "Quero me conectar" ──────────▶│
   │                                    │
   │◀── Envia a chave pública ─────────│  (identifica o servidor)
   │                                    │
   │── Negocia criptografia ──────────▶│
   │                                    │
   │── Autenticação (senha ou chave) ─▶│
   │                                    │
   │═══ Sessão de terminal segura ═════│
```

A partir daí, tudo que você digita e tudo que o servidor responde trafega criptografado.

---

## Duas formas de autenticação

### 1. Usuário e senha

A forma mais simples, mas menos recomendada para servidores expostos na internet — senhas podem ser alvo de ataques de força bruta.

### 2. Chave pública/privada

Mais segura e muito usada em ambientes profissionais:

- Você gera um **par de chaves**: uma privada (fica só com você) e uma pública (vai para o servidor).
- O servidor guarda sua chave pública na lista de "quem pode entrar".
- Na hora de conectar, o servidor desafia seu computador a provar que possui a chave privada correspondente — sem que a senha nunca precise trafegar pela rede.

```
Sua chave privada 🔑  ─── fica com você, nunca sai do seu PC
Sua chave pública 🔓  ─── fica registrada no servidor
```

---

## Além do terminal

O SSH não serve só para digitar comandos. Ele também é a base de outros usos comuns:

- **SFTP** → transferência segura de arquivos usando a mesma conexão SSH.
- **Túnel SSH** → redirecionar tráfego de outras aplicações por dentro de uma conexão SSH criptografada.
- **Git sobre SSH** → muitos desenvolvedores usam SSH para autenticar no GitHub/GitLab sem digitar senha a cada `push`.

---

## Porta

`22`

---

## 🧠 Para lembrar

**SSH = entrar remotamente no terminal, de forma segura → 22**

- Toda a comunicação é criptografada
- Pode autenticar por senha ou por par de chaves (mais seguro)
- Também é a base do SFTP, de túneis seguros e do acesso ao Git