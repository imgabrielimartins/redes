# O que é um Proxy?

Um **proxy** é um servidor intermediário entre o seu computador e a internet.

Em vez de o seu computador acessar um site diretamente, ele envia a solicitação ao proxy. O proxy então acessa o site e devolve a resposta para você.

---

## Funcionamento

```
Seu computador
      │
      ▼
    Proxy
      │
      ▼
Internet (Google, YouTube, etc.)
```

Ou seja:

1. Você solicita um site.
2. A solicitação vai para o proxy.
3. O proxy acessa o site.
4. O site responde ao proxy.
5. O proxy envia a resposta para você.

---

## Para que serve um proxy?

### 1. Controlar o acesso à internet

Empresas e escolas usam proxies para bloquear determinados sites.

**Exemplo:**
- Permite acesso ao site da empresa.
- Bloqueia redes sociais durante o expediente.

### 2. Aumentar a segurança

O proxy pode esconder o endereço IP interno dos computadores da empresa. Assim, os sites externos enxergam apenas o IP do proxy.

### 3. Melhorar o desempenho (Cache)

O proxy pode guardar cópias de páginas já acessadas.

**Exemplo:**
- João acessa o site da empresa.
- O proxy salva uma cópia.
- Maria acessa o mesmo site.
- O proxy entrega a cópia sem precisar baixar novamente.

Isso reduz o uso da internet e acelera o acesso.

### 4. Monitorar a navegação

Os administradores de rede podem registrar informações como:

- Quais sites foram acessados.
- Horário dos acessos.
- Qual usuário acessou cada site.

---

## Tipos de Proxy

### Forward Proxy

É o tipo mais comum. Fica entre os usuários e a internet.

```
Computador
     │
     ▼
Forward Proxy
     │
     ▼
Internet
```

É usado para:
- Bloquear sites.
- Fazer cache.
- Controlar acessos.

### Reverse Proxy

Fica na frente dos servidores, e não dos usuários.

```
Usuário
    │
    ▼
Reverse Proxy
    │
    ▼
Servidor
```

Ele pode:
- Distribuir requisições entre vários servidores (balanceamento de carga).
- Proteger os servidores contra ataques.
- Encerrar conexões HTTPS antes de encaminhar a requisição ao servidor.

É muito utilizado em sites de grande porte.

---

## Proxy × VPN

| Proxy | VPN |
|-------|-----|
| Intermedia apenas determinadas conexões ou aplicações. | Criptografa praticamente todo o tráfego do dispositivo. |
| Pode não criptografar os dados. | Criptografa os dados. |
| Geralmente é mais simples e rápido de configurar. | Oferece mais privacidade e segurança. |

---

## Proxy × Firewall

Muita gente confunde os dois.

| Proxy | Firewall |
|-------|----------|
| Intermedia as conexões entre cliente e servidor. | Filtra o tráfego com base em regras de segurança. |
| Pode fazer cache e controlar navegação. | Bloqueia ou permite conexões conforme políticas definidas. |

Eles frequentemente trabalham juntos em redes corporativas.

---

## Exemplo em uma empresa

Imagine uma empresa com 100 funcionários.

**Sem proxy:**

```
100 computadores
        │
        ▼
     Internet
```

**Com proxy:**

```
100 computadores
        │
        ▼
      Proxy
        │
        ▼
     Internet
```

Nesse cenário, o proxy pode:

- Bloquear redes sociais durante o expediente.
- Armazenar páginas em cache para acelerar o acesso.
- Registrar os sites acessados.
- Ocultar os IPs internos da empresa.