# cyber

## Pacotes necessários
apt update
apt install net-tools
sudo apt-get install openssh-server

## Ip
ip -br -c a
netstat -nltp
service ssh status
service apache status

Config

vim /etc/network/interfaces
iface enp0s3 inet static
address 192.168.10.10

Mudar porta do ssh
vim /etc/ssh/sshd_config
Mudar Senha:
passwd aluno


## Kali
WorldList:
cd /usr/share/worldlists
sudo gunzip rockyou.txt.gz
grep -E "" rockyou.txt

## Hydra
hydra -l aluno -P rockyou.txt ssh://192.168.15.73
hydra -L users.txt -p fiap ssh://192.168.15.73

## Config apache
vi /etc/apache2/apache2.conf

<Directory /var/www/>
  Options Indexes FollowSymLinks

vi /etc/apache2/conf-enabled/security.conf

(25)ServerTokens OS
(36)ServerSignature On

cd /var/www/html
esse é o arquivo padrao do apache
a porta padrao é 80

cd /home/aluno
python3 -m http.server 1234

vi /etc/apache2/apache2.conf
(193)  Options Indexes FollowSymLinks 
PARA
(193)  Options FollowSymLinks
service apache2 restart

vi /etc/apache2/conf-enabled/security.conf
(25)ServerTokens Prod
(36)ServerSignature Off

## CURL 
curl -u username:password https://example.com
curl http://<ip-da-vm>
curl -I http://<ip-da-vm>
3. curl -A (User-Agent)
curl -A "Aluno" http://<ip-da-vm>/agent/
curl -X POST -d "user=teste" http://<ip-da-vm>/posttest/
curl -o nome.txt https:google.com.br
curl -I http://<ip-da-vm> >> salvaaqui.txt

## SSH
acessando
ssh aluno@192.168.53.12

Transferindo arquivos
scp arquivotranferir aluno@192.168.10.30:/home/aluno/pastassh
