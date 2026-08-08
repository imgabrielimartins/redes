# FTP — Porta 21 📁

**FTP** significa *File Transfer Protocol*.

Ele serve para transferir arquivos entre computadores.

```
Seu computador
      ↓
     FTP
      ↓
Servidor
```

Você pode:

- enviar arquivos;
- baixar arquivos;
- organizar arquivos no servidor (criar pastas, renomear, excluir).

---

## Exemplo

Imagine que você desenvolveu um site e precisa colocar os arquivos no servidor:

```
index.html
style.css
script.js
```

O FTP pode ser usado para enviar esses arquivos.

---

## Duas conexões: controle e dados

Uma particularidade do FTP é que ele usa **duas conexões separadas** para funcionar:

```
Cliente                          Servidor
   │                                 │
   │── Conexão de controle (21) ────▶│  → comandos: login, listar, apagar...
   │                                 │
   │── Conexão de dados ────────────▶│  → transferência real do arquivo
```

- **Conexão de controle** (porta 21) → usada para autenticação e comandos, como "entre nesta pasta" ou "liste os arquivos".
- **Conexão de dados** → usada para o envio/recebimento efetivo dos arquivos. Pode ser aberta em modo ativo ou passivo, o que às vezes causa dor de cabeça com firewalls.

---

## Porta

`21` é a porta tradicional de controle do FTP.

⚠️ O FTP tradicional não é considerado seguro para transmitir credenciais e dados: usuário, senha e o conteúdo dos arquivos trafegam sem criptografia, ou seja, podem ser lidos por qualquer pessoa que intercepte a conexão.

---

## Alternativas mais seguras

Por causa dessa fragilidade, hoje é comum usar variações mais seguras no lugar do FTP puro:

| Protocolo | O que muda |
|-----------|-------------|
| **FTPS** | FTP com criptografia TLS/SSL adicionada por cima |
| **SFTP** | Transferência de arquivos feita sobre o protocolo SSH (porta 22), totalmente diferente do FTP por baixo dos panos |

---

## 🧠 Para lembrar

**FTP = transferência de arquivos → 21**

- Usa duas conexões: controle (21) e dados
- Não criptografa usuário, senha nem arquivos
- Hoje é mais comum usar FTPS ou SFTP em ambientes que exigem segurança