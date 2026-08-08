# TCP x UDP

Os dois são protocolos da camada de transporte e servem para levar dados de um computador para outro.

| Característica | TCP | UDP |
|-----------------|-----|-----|
| Confiabilidade | ✅ Alta | ❌ Baixa |
| Velocidade | Mais lento | Mais rápido |
| Confirmação | ✅ Sim | ❌ Não |
| Retransmissão | ✅ Sim | ❌ Não |
| Ordem dos dados | ✅ Garante | ❌ Não garante |
| Conexão | Orientado à conexão | Sem conexão |

---

## 🟢 TCP — confiável

Imagine que você está enviando uma encomenda. O TCP verifica se ela chegou corretamente.

- Envia os dados.
- O destino confirma o recebimento.
- Se alguma parte se perder, o TCP envia novamente.
- Garante que os dados cheguem na ordem correta.

Por fazer todas essas verificações, é mais lento que UDP.

**Exemplos:** 🌐 HTTPS, HTTP, SSH, FTP.

### O "aperto de mãos" antes de enviar dados

Antes de qualquer dado trafegar, o TCP faz um processo chamado *three-way handshake* (três etapas), para garantir que os dois lados estão prontos para conversar:

```
Cliente                          Servidor
   │                                 │
   │──── SYN ("quero conectar") ───▶│
   │                                 │
   │◀─── SYN-ACK ("pode, tô aqui") ──│
   │                                 │
   │──── ACK ("combinado") ────────▶│
   │                                 │
   │═══ Conexão estabelecida ═══════│
```

Só depois desse processo é que os dados de fato começam a trafegar. Isso adiciona um pequeno atraso, mas garante que a conexão é confiável desde o início.

---

## 🔵 UDP — rápido

Imagine que você está conversando em uma chamada de vídeo. O mais importante é que os dados cheguem rapidamente. Se um pequeno pedaço se perder, não vale a pena parar tudo para reenviar.

- Envia os dados.
- Não espera confirmação.
- Não retransmite automaticamente.
- Não garante que os dados cheguem na ordem.
- É mais rápido e possui menos controle.

**Exemplos:** 🎮 Jogos online, chamadas de vídeo, streaming e DNS.

### Sem handshake

Diferente do TCP, o UDP simplesmente envia os dados direto, sem negociar nada antes:

```
Cliente                          Servidor
   │                                 │
   │──── Dados ─────────────────────▶│
   │                                 │
```

Não há confirmação de que o pacote chegou, nem verificação de que o servidor está pronto para recebê-lo. Por isso é tão mais rápido — mas também menos confiável.

---

## Como escolher entre os dois?

A pergunta chave é: **"o que é mais importante aqui: confiabilidade ou velocidade?"**

- Se um dado faltando pode quebrar a aplicação (uma senha incompleta, um arquivo corrompido) → **TCP**.
- Se um dado faltando é aceitável e reenviar demoraria mais do que vale a pena (um quadro perdido numa chamada de vídeo) → **UDP**.

---

## 🧠 Para decorar

**TCP = "Tem Controle e Precisão"**
➡️ Confirma, verifica e retransmite.

**UDP = "Urgente, Direto e Prático"**
➡️ Envia rápido, sem ficar esperando.