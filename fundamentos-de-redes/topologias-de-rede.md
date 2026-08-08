# Topologias de Rede

As topologias de rede representam a forma como os dispositivos (computadores, servidores, impressoras etc.) são conectados entre si.

## 1. Barramento (Bus)

Todos os dispositivos são conectados a um único cabo principal, chamado barramento.

**Vantagens:**

- Baixo custo.
- Fácil de instalar em redes pequenas.
- Usa menos cabos.

**Desvantagens:**

- Se o cabo principal falhar, toda a rede para.
- Pode ficar lenta quando muitos dispositivos transmitem ao mesmo tempo.
- Difícil identificar falhas.

**Exemplo:** redes antigas de escritórios.

## 2. Estrela (Star)

Todos os dispositivos são conectados a um equipamento central, geralmente um switch (ou, em redes domésticas, um roteador).

**Vantagens:**

- Fácil de instalar e expandir.
- Se um cabo falhar, apenas aquele dispositivo perde a conexão.
- Fácil de identificar problemas.
- É a topologia mais utilizada atualmente.

**Desvantagens:**

- Se o equipamento central falhar, toda a rede fica indisponível.
- Requer mais cabeamento.

**Exemplo:** redes de empresas, escolas e residências.

## 3. Anel (Ring)

Cada dispositivo é conectado ao anterior e ao próximo, formando um círculo.

**Vantagens:**

- Organização na transmissão de dados.
- Menor chance de colisões.

**Desvantagens:**

- Se um dispositivo ou cabo falhar, a comunicação pode ser interrompida.
- Difícil de expandir e manter.

**Exemplo:** algumas redes industriais e tecnologias antigas.

## 4. Malha (Mesh)

Cada dispositivo é conectado a vários ou a todos os demais dispositivos.

**Vantagens:**

- Alta confiabilidade.
- Grande tolerância a falhas.
- Existem vários caminhos para os dados chegarem ao destino.

**Desvantagens:**

- Alto custo.
- Instalação e manutenção mais complexas.

**Exemplo:** data centers, redes críticas e algumas redes Wi-Fi do tipo mesh.

## Comparação

| Topologia | Como funciona | Vantagem | Desvantagem |
|-----------|----------------|----------|--------------|
| Barramento | Um único cabo conecta todos os dispositivos | Baixo custo | Falha no cabo principal derruba toda a rede |
| Estrela | Todos ligados a um equipamento central | Fácil manutenção | Dependência do equipamento central |
| Anel | Dispositivos ligados em círculo | Poucas colisões | Falha pode interromper a rede |
| Malha | Várias conexões entre os dispositivos | Alta disponibilidade | Alto custo |

## Dica para memorizar

```
Barramento → Um cabo para todos.
Estrela    → Todos ligados ao centro (switch).
Anel       → Forma um círculo.
Malha      → Todos possuem vários caminhos.
```