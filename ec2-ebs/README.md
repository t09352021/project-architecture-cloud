# projeto-architecture-cloud
This repo is a project to Arquit@s da Nuvem by Proz and Powered by AWS

### Add EBS on EC2 instance
#Case: A banda de Miguel te contratou para ajudá-los na criação de uma instância EC2 para organizar a documentação e 
os arquivos importantes da banda. Recentemente, a banda se interessou pelo mundo da computação em nuvem e decidiu explorar 
o Amazon EC2, um serviço popular de infraestrutura como serviço (IaaS) oferecido pela Amazon Web Services (AWS). 
Eles também conheceram o Amazon Linux, que é uma distribuição otimizada para a nuvem, sendo uma opção excelente 
para as instâncias EC2. Os membros da banda estão empolgados para testar essa tecnologia e começar a armazenar e 
gerenciar os seus documentos e arquivos na nuvem. Neste exercício, iremos ajudá-los com isso.

---

## 1. Configuração da Instância EC2

    Acesse o Console da AWS:
        Faça login na AWS Management Console.
        No painel de serviços, procure e clique em EC2.

    Crie uma nova instância EC2:
        Clique em Launch Instances.
        Escolha a Amazon Machine Image (AMI): Selecione Amazon Linux 2 (Free Tier Eligible).
        Escolha o tipo de instância:
            Para testes básicos, selecione t2.micro (Free Tier Eligible).
            Caso precise de mais recursos, escolha um tipo adequado (ex.: t3.medium).

    Configuração adicional:
        Configure a chave SSH (ou crie uma nova).
        Defina o Security Group:
            Libere a porta 22 (SSH).
            Adicione regras para acesso HTTP/HTTPS, se necessário no futuro.

    Finalize o lançamento:
        Clique em Launch e baixe o arquivo da chave privada (se criar uma nova).

---

## 2. Conexão via SSH

  Se seu sistema local for windows, pode ser realizado da seguinte maneira:
    Baixe e instale o software PuTTY

  Prepare sua chave privada:

    Salve a chave .pem em um local seguro.
    Execute o comando abaixo no terminal para ajustar as permissões:

  Use o executável PuTTY Key Generator:
    Em file, selecione a opção load private key;
    Selecione a chave .pem, clique em save private key e yes;

  Use o executável PuTTY;
    -No campo "Host name", adicione a chave IPv4 Public IP que está localizada no console da instância EC2;
    -No campo "Saved Session", dê um nome e clique em save;
    -Na lateral do menu, clique em SSH, escolha auth e credentials, em private key file for authentication adicione o arquivo .ppk
     e save;
    -Clique em open para abrir o terminal da instância.     
  
  
---

## 3. Gerenciando o Armazenamento

    Crie um volume EBS:
        No Console da AWS, vá até Volumes (dentro de EC2).
        Clique em Create Volume:
            Escolha um tamanho (ex.: 10 GB) e tipo (ex.: General Purpose SSD - gp3).
            Escolha a mesma Zona de Disponibilidade (AZ) da sua instância EC2.

    Anexe o volume à instância:
        No painel do volume, clique em Attach Volume.
        Selecione a instância EC2 e finalize.

---

## 4. Formatando e Montando o Volume

    Identifique o volume:
        No terminal da instância EC2, use o comando:
        "lsblk", para identificar o dispositivo (ex.: /dev/xvdf).

    Formate o volume:
      Formate o dispositivo com um sistema de arquivos (ex.: ext4), use o comando:
      sudo mkfs.ext4 /dev/xvdf

    Monte o volume:

      Crie um diretório para montar o volume, use o comando:
      sudo mkdir /mnt/banda

    Monte o volume no diretório:
      sudo mount /dev/xvdf /mnt/banda

---

## 5. Criação de Arquivos

    Crie um arquivo de texto:
        Use um editor como nano ou vim, use o comando:
        sudo nano /mnt/banda/info.txt

        Escreva algo como:
    

    Salve e saia.
---

## 6. Explorando Recursos

      Verifique o status do volume:
          
      Use os comandos abaixo:
        ls /mnt/banda  --Certifique-se de que o diretório contém arquivos.
        df -h          --Verifique o espaço em disco do volume.
        mount          --Valide que o volume está montado no local correto.
        cat /mnt/banda/info.txt  --Leia o conteúdo do arquivo criado.
---
**Autora:** Bruna do Nascimento (t09352021)
