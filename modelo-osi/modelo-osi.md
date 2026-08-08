# Modelo OSI (Open Systems Interconnection)

O Modelo OSI é um modelo criado para explicar como os dados trafegam de um dispositivo para outro em uma rede. Ele divide a comunicação em **7 camadas**, facilitando o entendimento, a configuração e a solução de problemas.

## Exemplo prático: enviando uma mensagem pelo WhatsApp

- No seu celular, a mensagem passa da **camada 7 até a 1**.
- Ela viaja pela rede.
- No celular da outra pessoa, ela sobe da **camada 1 até a 7**, onde a mensagem é exibida.

---

## As 7 camadas do Modelo OSI

### 7. Aplicação (Application)

É a camada com a qual o usuário interage. Ela fornece serviços para programas como:

- Navegador
- WhatsApp
- Outlook
- Chrome

**Protocolos:** HTTP, HTTPS, FTP, SMTP, DNS

**Exemplo:** Você abre o Google no navegador.

### 6. Apresentação (Presentation)

Responsável por preparar os dados para a aplicação. Ela faz:

- Criptografia
- Compressão
- Conversão de formatos

**Exemplo:** Quando você acessa um site HTTPS, os dados são criptografados aqui.

### 5. Sessão (Session)

Controla a comunicação entre dois dispositivos. Ela:

- inicia conexões;
- mantém a conexão ativa;
- encerra a conexão.

**Exemplo:** Enquanto você participa de uma chamada no Teams ou Zoom, essa camada mantém a sessão funcionando.

### 4. Transporte (Transport)

Garante que os dados cheguem corretamente. Os dois principais protocolos são:

**TCP**
- Confiável
- Confirma recebimento
- Reenvia pacotes perdidos
- Usado em: sites, bancos, e-mails

**UDP**
- Mais rápido
- Não confirma recebimento
- Usado em: jogos, streaming, chamadas de vídeo

### 3. Rede (Network)

Responsável pelo endereçamento IP e pelo roteamento dos pacotes.

**Trabalham aqui:** IP, ICMP, Roteadores

**Exemplo:** Seu computador envia um pacote para outro computador pela internet usando o endereço IP de destino.

### 2. Enlace (Data Link)

Entrega os dados entre dispositivos da mesma rede local.

**Trabalha com:** Endereço MAC, Switches, Quadros (Frames)

**Exemplo:** O switch identifica para qual computador deve enviar um quadro usando o endereço MAC.

### 1. Física (Physical)

É a camada dos sinais. Tudo o que transmite os bits:

- Cabo de rede
- Fibra óptica
- Wi-Fi (ondas de rádio)
- Conectores
- Hub

Aqui existem apenas bits (0 e 1).

---

## Fluxo completo

Imagine que você acessa um site.

```
Você abre o navegador
        ↓
Aplicação
        ↓
Apresentação
        ↓
Sessão
        ↓
Transporte (TCP)
        ↓
Rede (IP)
        ↓
Enlace (MAC)
        ↓
Física (cabos/sinais)
```

No computador de destino ocorre o caminho inverso:

```
Física
   ↑
Enlace
   ↑
Rede
   ↑
Transporte
   ↑
Sessão
   ↑
Apresentação
   ↑
Aplicação
```

---

## Equipamentos em cada camada

| Camada          | Equipamentos                |
|------------------|------------------------------|
| 7 - Aplicação    | Navegador, Outlook          |
| 6 - Apresentação | SSL/TLS, criptografia       |
| 5 - Sessão       | Controle de sessões         |
| 4 - Transporte   | TCP, UDP                    |
| 3 - Rede         | Roteador                    |
| 2 - Enlace       | Switch                      |
| 1 - Física       | Cabo, fibra, Wi-Fi, Hub     |

---
