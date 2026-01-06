---
---

## 🔐 Administração de Armazenamento – Azure Blob Storage

Este laboratório tem como objetivo consolidar o entendimento prático sobre **Azure Blob Storage**, com foco em **segurança, custos, camadas de acesso e gerenciamento de ciclo de vida**, pontos críticos cobrados na certificação **AZ-104** e amplamente utilizados em ambientes corporativos.

---

## 📦 Recursos Criados

- Storage Account
- Container Blob
- Upload de arquivo (Blob)
- Regra de Lifecycle Management
- Geração de SAS (Shared Access Signature)

---

## 🗂️ Azure Blob Storage – Conceitos Aplicados

### Tipos de Blob
- **Block Blob** (utilizado no laboratório)
- Page Blob
- Append Blob

---

## 🔐 Segurança e Acesso (SAS)

- Geração de **SAS Token** para acesso controlado ao Blob
- Definição de:
  - Permissões (Read)
  - Janela de tempo (Start / Expiry)
  - Protocolo permitido (HTTPS only)
- Entendimento de que o **SAS permite acesso sem expor a chave da Storage Account**, aumentando a segurança

Essa abordagem é amplamente utilizada para:
- Compartilhamento temporário de arquivos
- Integrações com aplicações externas
- Controle granular de acesso

---

## 🧊 Camadas de Acesso (Access Tiers)

Foram estudadas e aplicadas as seguintes camadas:

- **Hot**  
  Dados acessados com frequência (maior custo de armazenamento, menor custo de acesso)

- **Cool**  
  Dados acessados com menos frequência (equilíbrio entre custo e acesso)

- **Cold**  
  Dados raramente acessados (menor custo de armazenamento, maior custo de acesso)

- **Archive**  
  Dados de longo prazo, com necessidade de reidratação para acesso

Entendimento claro de que a **escolha correta do tier impacta diretamente o custo operacional**.

---

## ♻️ Gerenciamento de Ciclo de Vida (Lifecycle Management)

Foi criada uma **regra de Lifecycle** com as seguintes características:

### Condição (IF)
- Blobs baseados na data de **Last Modified**
- Mais antigos que **60 dias**

### Ação (THEN)
- Movimentação automática para o tier **Cool**

Esse controle permite:
- Redução significativa de custos
- Automação da governança de dados
- Otimização de armazenamento conforme o uso real

---

## 🧪 Validações Realizadas

- Verificação do tier atual do Blob
- Validação da regra de Lifecycle
- Teste de acesso via **SAS URL**
- Confirmação de criptografia do Blob (Server-side encryption)

---

## 📌 Observações Importantes

- Ao criar um recurso no Azure, o portal pode provisionar automaticamente dependências como:
  - Network Interface (NIC)
  - Discos
  - NSG
  - Virtual Network  
- O uso de **Lifecycle Management** é fundamental em ambientes corporativos para controle de custos
- O **Network Watcher** e logs auxiliam na validação de conectividade e segurança, mas para Storage o foco principal é **controle de acesso e governança**

---

## 🧠 Competências Desenvolvidas

- Administração de Azure Storage
- Segurança baseada em SAS
- Otimização de custos com Access Tiers
- Governança de dados com Lifecycle Management
- Visão prática de cenários reais de produção

---

## 📚 Relacionamento com AZ-104

Este laboratório cobre diretamente tópicos do domínio:
- **Administração de Armazenamento do Azure**
- **Proteção de dados**
- **Gerenciamento de custos e governança**

---

## 👤 Autor

Mikael Vieira de Souza  
Gestor de TI | Estudos focados em Azure Infrastructure & Cloud Administration
