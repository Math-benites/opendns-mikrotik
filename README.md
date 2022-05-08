# opendns-mikrotik-update
update OPEN DNS no mikrotik com (DNS-O-Matic) 


## Requisitos

Dificuldade = basico

1 - Tenha uma conta na OPEN DNS https://www.opendns.com/ (CREATE ACCOUNT FREE)

2 - Saiba utilizar o basico de OPEN DNS

---
## Configuracao de ambiente

1- Crie um network name 

<img src="/README/OPENDNS.png" alt="OPENDNS"/>

2- Crie um uma conta Free no DNSOMATIC

<img src="/README/DNSOMATIC.png" alt="DNSOMATIC"/>

3- Adicione um servico do OPEN DNS e selecione o network name 

<img src="/README/DNSOMATIC-SELECIONAR.png" alt="DNSOMATIC-SELECIONAR"/>

4- Veja como atualiza com seu email :: network name --- > seu endereco publico

<img src="/README/DNSOMATIC-NETWORKINGNAME.png" alt="DNSOMATIC-SELECIONAR"/>

## Configuracao Mikrotik Script

```
SEU EMAIL OPEN-DNS
:local odnsuser "SEU EMAIL"

SUA SENHA OPEN-DNS - NAO PODER TER CIFRAO
:local odnspass "SUA SENHA"

SEU NETWORKING NAME OPEN-DNS
:local odnshost "SEU NETWORKING NAME"
```

# EXTRA

Pode ser usado em script > Scheduler
Script nao gera log desnecessario , apenas quando ip é diferente do antigo ele registra em log para auditar




