# Telnet — Porta 23 ⚠️

**Telnet** também permite acessar um computador remotamente, através de um terminal — foi um dos primeiros protocolos usados para isso, décadas antes do SSH existir.

```
Seu PC
 ↓
Telnet
 ↓
Servidor
```

---

## O problema do Telnet

O Telnet não oferece a mesma proteção criptográfica do SSH: tudo o que você digita — incluindo usuário e senha — trafega em **texto puro** pela rede.

**Exemplo do que acontece na prática:**

```
Você digita:      usuario: admin
                   senha: minhasenha123

O que trafega na rede (sem criptografia):
                   admin
                   minhasenha123
```

Qualquer pessoa capturando o tráfego da rede (por exemplo, com uma ferramenta de análise de pacotes) consegue ler exatamente isso, incluindo a senha.

Por isso, atualmente, quando precisamos de acesso remoto seguro, usamos **SSH**.

---

## Por que o Telnet ainda existe?

Mesmo sendo considerado inseguro para acesso administrativo geral, o Telnet ainda aparece em alguns cenários bem específicos:

- **Testes de conectividade** → é comum usar o comando `telnet` só para verificar se uma porta está aberta em um servidor (ex.: `telnet servidor 80`), sem necessariamente usá-lo para login.
- **Equipamentos antigos** → alguns dispositivos de rede ou industriais mais antigos ainda só oferecem Telnet como opção de gerenciamento.
- **Redes isoladas** → em ambientes fechados, sem acesso à internet, o risco de interceptação é menor (mas ainda existe internamente).

---

## Porta

`23`

---

## 🧠 Para lembrar

**Telnet = acesso remoto antigo/inseguro → 23**

Uma comparação simples:

| | SSH | Telnet |
|---|-----|--------|
| Acesso remoto | ✅ | ✅ |
| Criptografia | ✅ | ❌ |
| Porta | 22 | 23 |
| Uso atual | Muito comum | Mais limitado (testes de porta, equipamentos legados) |