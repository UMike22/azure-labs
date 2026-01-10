Azure Storage – Blobs e File Shares (AZ-104)
📌 Objetivo do Laboratório

Este laboratório tem como objetivo consolidar o entendimento prático sobre Azure Storage, abordando Blob Storage e Azure File Shares, com foco em segurança, custo, governança e boas práticas operacionais, alinhado ao conteúdo da certificação AZ-104.

🗂️ Recursos Criados

Storage Account

Blob Container

Azure File Share (SMB)

Recovery Services Vault

Backup Policy

Lifecycle Management Policy

Snapshots

SAS Token (Shared Access Signature)

🧱 Blob Storage
🔹 Criação de Container e Upload de Blob

Criação de um container Blob

Upload de arquivo local (.png)

Validação de propriedades do blob:

Tipo: Block Blob

Tier inicial: Hot

Metadados e criptografia em repouso habilitada

🔐 Segurança com SAS (Shared Access Signature)

Geração de SAS Token com:

Permissão Read

Período de validade definido

Restrição de protocolo (HTTPS only)

Entendimento de que o SAS permite acesso temporário e controlado, sem expor a chave da conta

💰 Access Tiers (Custo x Uso)
Tier	Uso recomendado
Hot	Acesso frequente
Cool	Acesso esporádico
Cold	Acesso raro
Archive	Longa retenção, acesso eventual e lento
♻️ Lifecycle Management

Criação de regra de ciclo de vida baseada em:

Last modified

Mais de 60 dias

Ação automática:

Mover blobs do Hot para Cool

Objetivo:

Redução de custos

Manutenção da usabilidade dos dados

⚠️ Observação: Blobs apenas consultados, mas não modificados, continuam elegíveis para mudança de tier.

📁 Azure File Shares (SMB)
🔹 Criação do File Share

Tipo: Azure Files

Nome do compartilhamento: tecnologia

Tier: Hot

Protocolo: SMB 3.0

🔗 Acesso On-Premises

Mapeamento do File Share na máquina local (Windows)

Autenticação via Storage Account Key

Entendimento da porta 445 (TCP) como requisito obrigatório

Uso de script PowerShell fornecido pelo Azure para conexão persistente

🔐 Segurança e Proteção de Dados
🧾 Snapshot

Criação manual de snapshot

Entendimento de que:

Snapshot não é backup

É um ponto de restauração rápido dentro do próprio File Share

💾 Backup com Recovery Services Vault

Criação de Recovery Services Vault

Política de backup:

Frequência: Diária

Retenção: 30 dias

Ativação de Storage Account Lock

Registro do Recovery Services Provider na subscription

🗑️ Soft Delete

Soft delete habilitado para File Share

Possibilidade de recuperar exclusões em até 7 dias

Proteção contra exclusão acidental

🧠 Principais Aprendizados

Diferença prática entre Blob Storage e Azure Files

Importância do Lifecycle Management para controle de custos

Uso correto de SAS para acesso temporário e seguro

Diferença entre Snapshot x Backup

Impacto da porta 445 para integração on-premises

Como o Azure cria automaticamente recursos dependentes (NIC, NSG, Discos, VNet) ao criar VMs
