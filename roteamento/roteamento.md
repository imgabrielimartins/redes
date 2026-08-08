# Roteamento

Roteamento é o processo de escolher por qual caminho os dados devem passar para chegar de uma rede até outra.

```
PC → Switch → Roteador → Internet
```

O roteador analisa o IP de destino e decide para onde enviar o pacote.

---

## 🟢 Roteamento Estático

No roteamento estático, o administrador configura manualmente as rotas.

**Exemplo:**

```
Rede 192.168.2.0
       ↓
  Roteador 2
```

O administrador informa ao roteador:

> "Para chegar à rede 192.168.2.0, envie os pacotes pelo Roteador 2."

**Vantagens:**

- Simples em redes pequenas
- Mais previsível
- Não depende de protocolos de roteamento

**Desvantagens:**

- Dá mais trabalho em redes grandes
- Se uma rota mudar, alguém precisa alterá-la manualmente

🧠 **Estático = alguém configura o caminho.**

---

## 🔵 Roteamento Dinâmico

No roteamento dinâmico, os roteadores utilizam protocolos de roteamento para aprender as rotas automaticamente.

**Exemplo:**

```
Roteador A ←→ Roteador B ←→ Roteador C
```

Os roteadores trocam informações e conseguem descobrir:

> "Para chegar nessa rede, o melhor caminho é por aqui."

Se um caminho ficar indisponível, o protocolo pode encontrar outro caminho.

🧠 **Dinâmico = os roteadores aprendem os caminhos.**

---

## ⚖️ Estático x Dinâmico

| | Estático | Dinâmico |
|---|----------|----------|
| Configuração | Manual | Automática |
| Alteração de rotas | Manual | Automática |
| Redes pequenas | ✅ Bom | Pode ser desnecessário |
| Redes grandes | ❌ Trabalhoso | ✅ Ideal |
| Adaptação a falhas | ❌ Não automática | ✅ Automática |

---

## 📡 Protocolos de roteamento

### 1. RIP

**RIP** (*Routing Information Protocol*) é um protocolo de roteamento relativamente simples.

Ele utiliza principalmente o número de saltos (hops) para escolher uma rota.

**Exemplo:**

```
Roteador A → B → C → D
             3 saltos
```

O RIP prefere o caminho com menos saltos.

📌 Limite importante: **15 saltos**. 16 é considerado inalcançável.

🧠 **Para lembrar:** RIP = conta os saltos.

É mais simples e hoje é menos utilizado em redes modernas.

### 2. OSPF

**OSPF** (*Open Shortest Path First*) é muito utilizado em redes corporativas.

Ele constrói uma visão da topologia da rede e calcula os melhores caminhos.

**Exemplo:**

```
        B
       / \
      /   \
     A     D
      \   /
       \ /
        C
```

O OSPF pode analisar os caminhos disponíveis e escolher a melhor rota com base em seu custo.

🧠 **Para lembrar:** OSPF = encontra o melhor caminho dentro da rede.

É um protocolo **IGP**, utilizado principalmente dentro de uma organização/AS.

### 3. BGP

**BGP** (*Border Gateway Protocol*) é o principal protocolo utilizado para roteamento entre grandes redes na Internet.

**Imagine:**

```
Empresa A
    │
    ↓
   BGP
    │
    ↓
Provedor de Internet
    │
    ↓
Outra grande rede
```

O BGP permite que diferentes Sistemas Autônomos (AS) troquem informações de roteamento.

É fundamental para o funcionamento da Internet.

🧠 **Para lembrar:** BGP = conecta grandes redes/Internet.

---

## Como o roteador decide qual rota usar?

Quando existem várias rotas possíveis para o mesmo destino (aprendidas de formas diferentes, ou vindas de protocolos diferentes), o roteador precisa escolher uma. Dois conceitos ajudam a entender essa escolha:

- **Métrica** → um valor que cada protocolo usa internamente para comparar rotas (no RIP, é o número de saltos; no OSPF, é um "custo" baseado na largura de banda dos links).
- **Distância administrativa** → quando existe mais de um protocolo rodando ao mesmo tempo, esse valor decide qual fonte é mais "confiável". Rotas estáticas, por exemplo, normalmente têm prioridade sobre rotas aprendidas dinamicamente.

Isso explica por que, mesmo com vários caminhos disponíveis, o roteador sempre converge para uma única rota escolhida por vez para cada destino.

---

## 📌 Resumo para estudar

| Protocolo | Uso principal | Ideia principal |
|-----------|-----------------|-------------------|
| RIP | Redes menores/legadas | Conta saltos |
| OSPF | Redes corporativas | Melhor caminho dentro do AS |
| BGP | Internet | Roteamento entre AS |

---

## ⭐ O mais importante para uma prova/entrevista

- **RIP** → número de saltos
- **OSPF** → melhor caminho dentro da rede
- **BGP** → comunicação entre grandes redes/AS
- **Estático** → administrador configura
- **Dinâmico** → roteadores aprendem automaticamente