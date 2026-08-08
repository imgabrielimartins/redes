# IPv4 e IPv6

O IPv4 e o IPv6 são versões do Protocolo IP (Internet Protocol), responsável por identificar dispositivos em uma rede e permitir a comunicação entre eles.

---

## IPv4 (Internet Protocol Version 4)

É a versão mais antiga e ainda a mais utilizada.

Um endereço IPv4 possui 32 bits, divididos em 4 grupos de números separados por pontos.

**Exemplo:**

```
192.168.1.10
```

Cada grupo (octeto) pode variar de 0 a 255.

**Características:**

- 32 bits
- Aproximadamente 4,3 bilhões de endereços
- Mais simples e amplamente compatível
- Está ficando sem endereços disponíveis devido ao crescimento da Internet

---

## IPv6 (Internet Protocol Version 6)

Foi criado para substituir o IPv4 e resolver a falta de endereços.

Um endereço IPv6 possui 128 bits, escritos em 8 grupos de números hexadecimais separados por dois-pontos (`:`).

**Exemplo:**

```
2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

Também pode ser abreviado:

```
2001:db8:85a3::8a2e:370:7334
```

**Características:**

- 128 bits
- Quantidade enorme de endereços (cerca de 340 undecilhões)
- Melhor suporte para segurança e desempenho em alguns cenários
- Elimina praticamente o problema de falta de endereços

---

## Comparação

| Característica | IPv4 | IPv6 |
|-----------------|------|------|
| Tamanho | 32 bits | 128 bits |
| Formato | 4 números separados por ponto | 8 grupos hexadecimais separados por `:` |
| Exemplo | 192.168.1.10 | 2001:db8::1 |
| Quantidade de endereços | ~4,3 bilhões | ~340 undecilhões |
| Uso atual | Mais comum | Crescendo rapidamente |

---

## Exemplo prático

Imagine uma cidade:

- **IPv4** é como uma cidade com 4 bilhões de casas. Quando todas as casas forem ocupadas, não há espaço para novas.
- **IPv6** é como um planeta inteiro com espaço para construir casas praticamente sem limite.

---

## Como saber qual IP você está usando?

**No Windows:**

1. Pressione `Windows + R`.
2. Digite `cmd` e pressione Enter.
3. Execute:

```
ipconfig
```

Você verá algo parecido com:

```
Endereço IPv4. . . . . . . . . : 192.168.1.15
Endereço IPv6. . . . . . . . . : fe80::d85f:2a7b:4b2e:9c6a
```