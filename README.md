<h1 align="center">opendns-mikrotik-update-dynamic</h1> 

✔️ RouterOS 6

✔️ RouterOS 7

---

### Pré-requisitos

🛎️ Crie contas no site abaixo para seguir o passo a passo

🛑 Por limitacoes que ate o momento quero resolver , crie uma senha usando simbolo especial # (exemplo: Willpull22#)

🛑 Script pode nao funcionar se a senha tiver @ * $

DNSOMATIC https://www.dnsomatic.com/ (CREATE ACCOUNT FREE)

OPEN DNS https://www.opendns.com/ (CREATE ACCOUNT FREE)

---

### 👀 como fazer usar opendns filtros

https://www.youtube.com/watch?v=vXncOSdeQLQ

---

### 🪓 Configuracao de ambiente

1- Acesse o OPENDNS , crie uma NETWORKING
<p float="left">
 <img src="/README/1.png" width="600" />
<p>

2- Defina uma Nome de NETWORKING
<p float="left">
 <img src="/README/2.png" width="600" />
<p>

3- Crie um uma conta Free no DNSOMATIC ( https://www.dnsomatic.com/ )

<p float="left">
 <img src="/README/3.png" width="600" />
<p>

4- Adicione um servico do OPEN DNS e selecione o network name 

<p float="left">
 <img src="/README/4.png" width="600" />
<p>

<p float="left">
 <img src="/README/4.1.png" width="600" />
<p>

😎 Concluido a configuracao no portal

---

## Configuracao Mikrotik

<p float="left">
 <img src="/README/5.png" width="600" />
<p>

Cole script.txt e altere o campo abaixo com credenciais do DNSOMATIC

```
SEU EMAIL OPEN-DNS
:local odnsuser "SEU EMAIL"

SUA SENHA OPEN-DNS - NAO PODER TER CIFRAO
:local odnspass "SUA SENHA"

SEU NETWORKING NAME OPEN-DNS
:local odnshost "SEU NETWORKING NAME"
```

Quando o ip mudar voce vai ver isso aqui abaixo no seu log mikrotik

<p float="left">
 <img src="/README/6.png" width="600" />
<p>

---

# EXTRA

Regra para definir rede que deve ser aplicado o OPENDNS (altere conforme necessario)

src-address= rede local

in-interface="ether4 - LAN"
```
/ip firewall nat

add action=dst-nat chain=dstnat comment=OPENDNS dst-port=53 in-interface=\
    "ether4 - LAN" protocol=udp src-address=192.168.0.0/24 to-addresses=\
    208.67.222.222 to-ports=53

add action=dst-nat chain=dstnat comment=OPENDNS2 dst-port=53 in-interface=\
    "ether4 - LAN" protocol=udp src-address=192.168.0.0/24 to-addresses=\
    208.67.220.220 to-ports=53
```
Pode ser usado em script > Scheduler recomendado atualizacao acada 3 min

🧠 Script nao gera log desnecessario , apenas quando ip é diferente do antigo ele registra em log para auditar

#Creditos
Matheus Benites

https://www.linkedin.com/in/matheus-benites/




