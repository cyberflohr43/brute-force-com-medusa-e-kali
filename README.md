# brute-force-com-medusa-e-kali
Projeto do Bootcamp de Ciberseguranca do Banco Santander em parceria com a DIO, nesse projeto estarei invadindo uma máquina virtual na mesma rede Wi-Fi e um site exploitable, para fins educativos e exploratórios das ferramentas de ethical hacking e cybersecurity.

)--Metasploitable 2--(
A máquina virtual que será invadida está com o Metasploitable 2 instalado

Nas últimas aulas aprendi usos básicos de ferramentas do kali linux, como Medusa, TCP, Nmap, SMB, entre outros.

**Deixando claro que já tenho o IP da VM Metasploitable, até por ser uma máquina virtual**

Na pasta /images tem prints do processo, mas vou descrevê-lo aqui:

1. Comando
   "ping -c 3 <IP>":
   Envia pacotes de rede ICMP para testar conectividade com outro dispositivo
   
3. Comando
   "nmap -sV -p 21,22,80,445,139 <IP>":
   Escaneia as portas especificadas após "-p" (ports) no IP inputado e mostra quais que estão abertas.
   
4. Criação das listas de palavras
   Criamos dois arquivos .txt, um com nomes prováveis de usuário e outro com senhas possíveis, chamei-os de "usuarios.txt" e "senhas.txt".

5. Comando
   "medusa -h <IP> -U usuarios.txt -P senhas.txt -M tcp -6":
   Tenta todas as combinações possíveis dos dois documentos no input de login e senha do pc.

6. Análise
   A Medusa retorna uma mensagem de sucesso caso ela consiga acessar o sistema com as palavras passadas, e te retorna o usuário e senha corretos.

7. Comando
   "ftp <IP>"
   Estabelece uma conexão através do ftp, sendo possível logar com as credenciais adiquiridas com a Medusa.

8. Comando
   "smbclient -L <IP> -U <USER>"
   Uma vez tendo acesso ao sistema, é possível também verificar se existem outros users com mais permissões, como admins do sistema por exemplo.

* Vale lembrar que segurança de sistemas não é só sobre contratar os melhores hackers do mundo, incentivar práticas de segurança básicas aos usuários já ajuda e muito, como disse a professora do curso:
  "- Não tem pra que investir milhões em segurança digital se a senha do administrador de TI ainda é 123456."
