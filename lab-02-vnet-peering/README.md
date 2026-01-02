# Lab 02 – Virtual Network Peering e Conectividade entre VNets

## 📌 Contexto
Este laboratório foi desenvolvido durante os estudos para a certificação
**AZ-104 – Microsoft Azure Administrator**, com foco em **Administração de Rede Virtual**.

O objetivo principal foi entender o **comportamento padrão de conectividade no Azure**
e as formas corretas de habilitar comunicação entre redes virtuais distintas.

---

## 🎯 Objetivos do Laboratório
- Criar um **Resource Group** organizado
- Criar **duas Virtual Networks (VNets)** distintas
- Criar **uma máquina virtual em cada VNet**
- Testar comunicação **antes e depois** da configuração de conectividade
- Implementar **VNet Peering** como solução
- Validar a conectividade utilizando **Network Watcher**

---

## 🏗️ Arquitetura Implementada

- **Resource Group:** `az104-rg05`
- **VNets criadas:**
  - `CoreServicesVnet`
  - `ManufacturingVnet`
- Cada VNet contém:
  - Subnets próprias
  - Uma VM Windows
- Comunicação entre:
  - Subnets da mesma VNet → **permitida por padrão**
  - VNets diferentes → **não permitida por padrão**

---

## 🔍 Testes Realizados

### ❌ Antes do Peering
- Tentativa de comunicação entre as VMs em VNets diferentes
- Resultado: **falha**
- Confirmação de que o Azure **não permite comunicação entre VNets por padrão**

### ✅ Após o Peering
- Criação de **VNet Peering bidirecional** entre:
  - `CoreServicesVnet` ↔ `ManufacturingVnet`
- Opções habilitadas:
  - Allow VNet access
  - Allow forwarded traffic
- Resultado: **conectividade estabelecida com sucesso**

---

## 🧪 Validação de Conectividade

A validação foi feita de duas formas:

### 1️⃣ Linha de comando (teste direto)
- Testes simples de conectividade entre as VMs

### 2️⃣ Network Watcher – Connection Troubleshoot
- Testes executados:
  - Connectivity
  - NSG diagnostic
  - Next hop
  - Port scanner
- Benefício:
  - Visualização clara do caminho do tráfego
  - Identificação do tipo de rota (VirtualNetworkPeering)
  - Confirmação de regras efetivas de NSG

O **Network Watcher** foi essencial por fornecer **mais detalhes técnicos**
do que um teste básico via linha de comando.

---

## 🧠 Aprendizados Importantes

- VNets **não se comunicam por padrão** no Azure
- Existem várias opções de conectividade entre VNets:
  - VNet Peering
  - VPN Gateway
  - ExpressRoute
- O **VNet Peering** é uma solução simples e eficiente para cenários internos
- Subnets dentro da mesma VNet possuem comunicação padrão
- Ao criar uma VM sem infraestrutura existente, o Azure:
  - Cria automaticamente NIC
  - Cria NSG
  - Cria disco
  - Cria VNet e subnet, se necessário

Esse comportamento reforça a importância de **planejar a infraestrutura antes**
para evitar recursos desnecessários ou fora do padrão.

---

## ✅ Status do Laboratório
✔️ Laboratório finalizado  
✔️ Conectividade validada  
✔️ Testes documentados  

---

## 📚 Relacionado à AZ-104
- Administração de Rede Virtual
- Conectividade entre VNets
- Network Watcher
- Troubleshooting de rede
