# Azure Networking – NSG e ASG na Prática

## 📌 Objetivo
Demonstrar a implementação prática de **Network Security Groups (NSG)** e
**Application Security Groups (ASG)** no Azure, aplicando boas práticas de
segurança, organização de regras, segmentação por aplicação e prevenção
de configurações órfãs em ambientes de nuvem.

---

## 👤 Autor
**Mikael Vieira**  
Profissional de TI com experiência em infraestrutura e operações,
em processo de transição para Cloud, com foco em Azure,
networking, segurança e governança.

---

## 🧠 Contexto do Laboratório
Este laboratório simula um cenário real de ambiente corporativo,
onde é necessário controlar o tráfego de rede entre aplicações,
evitar regras baseadas em IP fixo ou hosts específicos
e garantir que políticas de segurança continuem válidas
mesmo após a exclusão ou substituição de máquinas virtuais.

---

## 🏗️ Recursos Criados

### 🔐 Network Security Group (NSG)
- Criação do **NSG `nsg-01`**
- Associado a:
  - Subnets **ou**
  - Interfaces de rede (NICs) de VMs  
- **NSGs não são aplicados diretamente em VNets**, apenas em subnets ou NICs

---

### 🧩 Application Security Group (ASG)
- Criação do **ASG `ASG-01`**
- Utilizado para representar a **aplicação**, e não a máquina
- VMs são associadas ao ASG conforme sua função na aplicação

---

## 🔢 Regras de Segurança e Prioridade

### Entendimento de Prioridade
- As regras do NSG são avaliadas da **menor para a maior prioridade**
- Espaçamento intencional entre prioridades (ex: 100, 200, 300)
  para facilitar:
  - Testes
  - Manutenção
  - Inclusão de novas regras sem retrabalho

---

### Regras Criadas (Exemplo)
- Regra de **entrada (Inbound)**:
  - Destino: **Application Security Group (ASG-01)**
  - Porta: **8080**
  - Protocolo: Any
  - Ação: Allow
  - Prioridade: 100

Essa abordagem garante que o tráfego seja liberado
para a **aplicação**, independentemente da VM específica.

---

## 🔗 Uso de ASG como Destino no NSG

### Por que usar ASG?
- Evita regras amarradas a:
  - IPs fixos
  - Máquinas específicas
- Previne a criação de **políticas órfãs**
- Quando uma VM é excluída:
  - A regra continua válida
  - Novas VMs podem herdar o ASG corretamente

### Boa prática aplicada
- O NSG aponta para o **ASG como destino**
- A segurança segue a **aplicação**
- Não depende da existência de um host específico

---

## 🧪 Validações Realizadas
- ✅ Criação e associação correta do NSG
- ✅ Entendimento das regras padrão (Allow e Deny)
- ✅ Criação de regras customizadas com prioridade controlada
- ✅ Associação de regras usando ASG como destino
- ✅ Validação do conceito de regras efetivas
- ✅ Confirmação de que NSGs não são aplicáveis diretamente em VNets

---

## ✅ Principais Aprendizados
- NSGs controlam tráfego de entrada e saída no Azure
- A prioridade das regras é fundamental para evitar bloqueios inesperados
- NSGs devem ser aplicados apenas em subnets ou NICs
- ASGs abstraem a segurança do host para a aplicação
- O uso de ASG evita regras quebradas e heranças indevidas
- Segurança bem feita em Cloud é baseada em **design**, não em IP fixo

---

## 📘 Tecnologias Utilizadas
- Azure Network Security Group (NSG)
- Regras de segurança (Inbound / Outbound)
- Application Security Group (ASG)
- Azure Virtual Network
- Subnets
- Azure Resource Manager

---

## 🎯 Objetivo Profissional
Este laboratório faz parte do meu processo de desenvolvimento técnico em Azure,
com foco em networking e segurança,
aplicando práticas utilizadas em ambientes corporativos reais.

