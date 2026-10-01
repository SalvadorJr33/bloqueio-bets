# bloqueio-bets

Lista de domínios de sites de apostas (bets) e cassinos online, no formato de arquivo *hosts*, para bloqueio via DNS.

Cada domínio aponta para `0.0.0.0`, o que impede o acesso ao site quando a lista é usada pelo seu servidor DNS:

```
0.0.0.0 blaze.com
0.0.0.0 br.betano.com
```

## Compatibilidade

- **MikroTik** (RouterOS 7 – recurso *Adlist*)
- **Pi-hole**

## URL da lista

```
https://raw.githubusercontent.com/SalvadorJr33/bloqueio-bets/main/dominios.txt
```

## Como usar

### MikroTik (Adlist)

No terminal do RouterOS:

```
/ip dns adlist add url=https://raw.githubusercontent.com/SalvadorJr33/bloqueio-bets/main/dominios.txt ssl-verify=no
```

Garanta que os clientes da rede usem o MikroTik como servidor DNS (`/ip dns set allow-remote-requests=yes`).

### Pi-hole

1. Acesse o painel do Pi-hole e vá em **Adlists** (ou **Lists**, nas versões mais recentes).
2. Adicione a URL da lista acima e salve.
3. Atualize o Gravity: **Tools > Update Gravity** (ou rode `pihole -g`).

## Créditos

Esta lista foi convertida a partir da lista do repositório [faakit/bet-blocker-dns](https://github.com/faakit/bet-blocker-dns/blob/main/blocks.txt). Todo o crédito pela coleta original dos domínios é dos autores desse projeto.
