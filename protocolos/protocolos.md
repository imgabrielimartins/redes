# 🌐 Protocolos de Rede

Um protocolo é um conjunto de regras que define como os dispositivos se comunicam em uma rede.

A porta identifica qual serviço está sendo acessado.

**Exemplo:**

```
192.168.1.10:22

192.168.1.10 → endereço IP do dispositivo
22           → porta do serviço SSH
```

---

## 🌍 HTTP — Porta 80

HTTP (HyperText Transfer Protocol) é usado para acessar páginas e serviços web.

**Exemplo:**

```
Navegador → Servidor Web
```

A porta padrão é `80`.

📌 HTTP não criptografa a comunicação.

**Para lembrar:** HTTP = site sem HTTPS → 80

---

## 🔒 HTTPS — Porta 443

É o HTTP com criptografia usando TLS. É utilizado pela maioria dos sites atualmente.

**Exemplo:**

```
https://google.com
```

Porta: `443`

📌 Protege os dados durante a comunicação.

**Para lembrar:** HTTPS = HTTP seguro → 443

---

## 📁 FTP — Porta 21

FTP (File Transfer Protocol) é usado para transferência de arquivos. Pode ser utilizado para enviar e baixar arquivos de um servidor.

Porta de controle padrão: `21`

⚠️ FTP tradicional não fornece criptografia adequada para credenciais e dados.

**Para lembrar:** FTP = transferência de arquivos → 21

---

## 🔐 SFTP — Porta 22

SFTP (SSH File Transfer Protocol) permite transferir arquivos de forma segura através do SSH.

Porta: `22`

**Exemplo:**

```
Computador → SFTP → Servidor
```

**Para lembrar:** SFTP = arquivos seguros → 22

---

## 🖥️ SSH — Porta 22

SSH (Secure Shell) permite acessar um computador ou servidor remotamente através de um terminal seguro.

**Exemplo:**

```
Seu PC
  ↓
 SSH
  ↓
Servidor Linux
```

Você pode executar comandos no servidor mesmo estando em outro computador.

Porta: `22`

**Para lembrar:** SSH = acesso remoto seguro → 22

---

## ⚠️ Telnet — Porta 23

O Telnet também permite acesso remoto ao terminal. Porém, ele não criptografa adequadamente a comunicação.

Porta: `23`

Hoje, normalmente preferimos SSH.

**Para lembrar:** Telnet = acesso remoto antigo/inseguro → 23

---

## 🌐 DNS — Porta 53

DNS (Domain Name System) transforma nomes de domínio em endereços IP.

**Por exemplo:**

```
google.com
     ↓
142.250.x.x
```

Sem precisar decorar o IP dos sites.

Porta padrão: `53`

DNS normalmente utiliza UDP 53, mas também pode utilizar TCP 53 em determinadas situações.

**Para lembrar:** DNS = nome → IP → 53

---

## 📡 DHCP — Portas 67 e 68

DHCP (Dynamic Host Configuration Protocol) configura automaticamente os dispositivos da rede.

Ele pode fornecer:

- IP
- Máscara de rede
- Gateway
- DNS

**Exemplo:**

```
Notebook entra na rede
        ↓
       DHCP
        ↓
IP:      192.168.1.20
Gateway: 192.168.1.1
DNS:     8.8.8.8
```

Portas:
- `67` → servidor DHCP
- `68` → cliente DHCP

**Para lembrar:** DHCP = entrega configuração de rede → 67/68

---

## 📧 SMTP — Porta 25

SMTP (Simple Mail Transfer Protocol) é utilizado para envio de e-mails, principalmente na comunicação entre servidores de e-mail.

Porta tradicional: `25`

Existem também portas como `587` para submissão autenticada de e-mail e `465` para SMTP sobre TLS em configurações modernas.

**Para lembrar:** SMTP = envia e-mail → 25

---

## 📥 POP3 — Porta 110

POP3 é usado para receber/baixar e-mails do servidor.

Porta: `110`

Uma característica tradicional do POP3 é baixar as mensagens para o dispositivo, embora clientes modernos possam manter cópias no servidor.

**Para lembrar:** POP3 = baixar e-mail → 110

---

## 📬 IMAP — Porta 143

IMAP também é utilizado para receber/acessar e-mails.

Porta: `143`

A principal diferença é que o IMAP mantém os e-mails sincronizados com o servidor.

**Exemplo:**

```
Servidor
   │
   ├── 📱 Celular
   ├── 💻 Notebook
   └── 🖥️ PC
```

Você pode acessar a mesma caixa de entrada em vários dispositivos.

**Para lembrar:** IMAP = e-mail sincronizado → 143

---

## 📊 SNMP — Porta 161

SNMP (Simple Network Management Protocol) é utilizado para monitorar e gerenciar dispositivos de rede.

Pode monitorar:

- Switch
- Roteador
- Servidor
- Impressora
- Access Point

**Exemplo:**

```
Servidor de monitoramento
          ↓
         SNMP
          ↓
       Switch
```

Porta: `161`

📌 A porta `162` é tradicionalmente usada para SNMP Trap, mensagens de alerta enviadas pelo dispositivo ao sistema de gerenciamento.

**Para lembrar:** SNMP = monitoramento → 161

---

## 👥 LDAP — Porta 389

LDAP (Lightweight Directory Access Protocol) é usado para acessar e consultar diretórios de usuários e recursos.

É muito utilizado em ambientes corporativos para informações de:

- Usuários
- Grupos
- Computadores
- Permissões

Porta: `389`

📌 LDAP pode ser usado com mecanismos de segurança/TLS; LDAPS tradicionalmente usa a porta `636`.

**Para lembrar:** LDAP = diretório de usuários → 389

---

## 🖥️ RDP — Porta 3389

RDP (Remote Desktop Protocol) permite acessar remotamente a interface gráfica de um computador Windows.

**Exemplo:**

```
Seu computador
      ↓
     RDP
      ↓
Servidor Windows
```

Você vê a área de trabalho do computador remoto e pode interagir com ela.

Porta padrão: `3389`

**Para lembrar:** RDP = acesso remoto Windows → 3389

---

## 📂 SMB — Porta 445

SMB (Server Message Block) é muito utilizado para compartilhamento de arquivos, pastas e impressoras, especialmente em ambientes Windows.

**Exemplo:**

```
PC
 ↓
SMB
 ↓
Servidor
 ↓
📁 Pasta compartilhada
```

Porta: `445`

É muito importante em redes corporativas.

**Para lembrar:** SMB = compartilhamento de arquivos → 445

---

## 🧠 Tabela para estudar

| Protocolo | Para que serve | Porta |
|-----------|-----------------|-------|
| HTTP | Sites | 80 |
| HTTPS | Sites seguros | 443 |
| FTP | Transferência de arquivos | 21 |
| SFTP | Transferência segura de arquivos | 22 |
| SSH | Terminal remoto seguro | 22 |
| Telnet | Terminal remoto sem segurança adequada | 23 |
| DNS | Nome → IP | 53 |
| DHCP | Configuração automática de rede | 67/68 |
| SMTP | Envio de e-mails | 25 |
| POP3 | Recebimento de e-mails | 110 |
| IMAP | E-mail sincronizado | 143 |
| SNMP | Monitoramento de dispositivos | 161 |
| LDAP | Diretório de usuários | 389 |
| RDP | Acesso remoto Windows | 3389 |
| SMB | Compartilhamento de arquivos | 445 |

---

## 🎯 As mais importantes para você decorar primeiro

Se você está começando em Infra, priorize:

- `22` → SSH/SFTP
- `53` → DNS
- `67/68` → DHCP
- `80` → HTTP
- `443` → HTTPS
- `445` → SMB
- `3389` → RDP
- `161` → SNMP

E uma associação que ajuda MUITO:

- 🌐 DNS → descobre o IP
- 📡 DHCP → entrega o IP
- 🔀 Switch → usa MAC
- 🌎 Roteador → usa IP
- 🔐 SSH → acesso remoto Linux
- 🖥️ RDP → acesso remoto Windows
- 📂 SMB → compartilhamento de arquivos
- 🛡️ Firewall → controla quais conexões podem passar