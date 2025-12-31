
---

## 🔐 Segurança de Rede

### Network Security Group (NSG)
- Criação de um **NSG customizado**
- Aplicação do NSG em subnets / interfaces de rede
- Entendimento de que:
  - NSGs **não são aplicados diretamente em VNets**
  - Apenas em **subnets ou NICs**

---

### Application Security Group (ASG)
- Criação de um **ASG** para representar a aplicação
- Uso do ASG como destino nas regras do NSG
- Abordagem baseada em aplicação, e não em IP ou VM específica

Essa prática evita:
- Regras órfãs
- Dependência de IP fixo
- Problemas quando VMs são removidas ou substituídas

---

## 🔢 Regras de Segurança Criadas

### 🔸 Regras de Entrada (Inbound)
- Permissão de tráfego **apenas para o ASG**
- Portas liberadas: **80 e 443**
- Protocolo: TCP
- Prioridade definida manualmente para organização
- Tráfego não explicitamente permitido é negado pela regra padrão

---

### 🔸 Regras de Saída (Outbound)
- Criação de regra **customizada de negação**
- Bloqueio de tráfego de saída para a **Internet**
- Porta bloqueada: **8080**
- Objetivo:
  - Restringir comunicação externa
  - Controlar o fluxo de dados de saída
  - Reforçar o princípio de menor privilégio

---

## 🧪 Validações Realizadas
- ✅ Criação correta das VNets e subnets
- ✅ Associação adequada do NSG
- ✅ Funcionamento das regras de prioridade
- ✅ Liberação de tráfego inbound apenas via ASG
- ✅ Bloqueio de tráfego outbound para a Internet
- ✅ Confirmação das regras padrão do NSG (Allow/Deny)
- ✅ Validação de regras efetivas

---

## ✅ Principais Aprendizados
- VNets devem ser bem planejadas para facilitar segmentação
- NSGs controlam tráfego de entrada e saída, mas não são aplicados em VNets
- A prioridade das regras é fundamental para o comportamento do tráfego
- ASGs permitem segurança orientada à aplicação
- Regras outbound são tão importantes quanto inbound
- Segurança em Cloud deve ser previsível, escalável e fácil de manter

---

## 📘 Tecnologias Utilizadas
- Azure Virtual Network (VNet)
- Subnets
- Network Security Group (NSG)
- Application Security Group (ASG)
- Regras de segurança Inbound e Outbound
- Azure Resource Manager

---

## 🎯 Objetivo Profissional
Este laboratório faz parte do meu processo de desenvolvimento técnico em Azure,
com foco em redes e segurança,
aplicando práticas comuns em ambientes corporativos e exigidas pela certificação AZ-104.
