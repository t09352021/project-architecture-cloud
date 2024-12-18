# projeto-architecture-cloud
This repo is a project to Arquit@s da Nuvem by Proz and Powered by AWS

# Topologia Estrela no Cisco Packet Tracer

#Case: Para o show da banda de Miguel, será necessário configurar uma rede de computadores. A comunicação entre os membros da equipe de produção, que estarão espalhados pelo teatro, é fundamental para manter todos informados e verificar se nada está fugindo do controle. O agente da banda decidiu modernizar a infraestrutura do show para melhorar essa comunicação. Para ajudá-los, você deve usar o Cisco Packet Tracer para criar uma topologia de rede estrela que permita a toda a equipe se comunicar facilmente.

Este projeto consiste em uma topologia de rede em estrela, implementada no Cisco Packet Tracer. A rede é composta por:
- **1 Switch (Switch-PT)**
- **4 Computadores**

## **Configuração da Topologia**
1. **Criação da Rede:**
   - Adicione 1 switch e 4 PCs.
   - Conecte os PCs ao switch usando cabos Copper Straight-Through (cabo direto).
   - As portas no switch utilizadas foram:
     - Producao1: FastEthernet0/1
     - Producao2: FastEthernet1/1
     - Producao3: FastEthernet2/1
     - Producao4: FastEthernet3/1

2. **Configuração dos Endereços IP:**
   Cada computador recebeu um endereço IP único na sub-rede 192.168.1.0/24:
   - **Producao1:** 192.168.1.1, Máscara: 255.255.255.0
   - **Producao2:** 192.168.1.2, Máscara: 255.255.255.0
   - **Producao3:** 192.168.1.3, Máscara: 255.255.255.0
   - **Producao4:** 192.168.1.4, Máscara: 255.255.255.0

4. **Teste de Conectividade:**
   - Use o comando `ping` em cada PC para verificar a comunicação entre os dispositivos.

## **Arquivo `.pkt`**
O arquivo `.pkt` com a topologia configurada está disponível neste repositório. Basta abri-lo no Cisco Packet Tracer para explorar e testar a rede.

## **Como Executar**
1. Baixe o Cisco Packet Tracer.
2. Faça o download do arquivo `.pkt` deste repositório.
3. Abra o arquivo no Cisco Packet Tracer e siga as instruções descritas acima.

---

### **Estrutura do Repositório**
- `modelo_topologia_estrela_banda.pkt` - Arquivo do Cisco Packet Tracer.
- `README.md` - Instruções detalhadas.

---

## **Contribuição**
Se desejar contribuir com melhorias ou sugestões, sinta-se à vontade para criar um pull request ou abrir uma issue neste repositório.

---

**Autor:** Bruna do Nascimento (t09352021)
