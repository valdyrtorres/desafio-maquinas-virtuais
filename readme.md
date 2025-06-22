# ☁️ Criando e Gerenciando Máquinas Virtuais na Azure via System Center VMM

Este guia detalha o processo para criar uma máquina virtual (VM) na Microsoft Azure usando o **System Center Virtual Machine Manager (VMM)**, além de executar operações com discos como **redimensionamento**, **adição** e **desanexação** de discos de dados.

## Pré-requisitos

- Conta Azure com permissões para criar recursos.
- Ambiente com **System Center VMM 2022** configurado e integrado ao Azure.
- Subscription conectada no VMM.
- Biblioteca com imagem de base ou modelo de VM.

---

## 🔧 Etapa 1: Adicionar Conta do Azure ao VMM

1. No console do VMM, vá em **Fabric**.
2. Clique com o botão direito em **Azure Subscriptions** > **Add Subscription**.
3. Insira as credenciais da sua conta Azure e selecione a Subscription.

---

## 🖥️ Etapa 2: Criar uma Máquina Virtual na Azure

1. Vá para a guia **VMs and Services**.
2. Clique em **Create Virtual Machine** > **Azure VM**.
3. Siga o assistente:

   - **Nome e Local**: defina um nome e região da Azure.
   - **Imagem de Base**: escolha uma imagem do Azure (ex: Windows Server 2022).
   - **Tamanho**: selecione o tamanho da VM (ex: Standard_D2s_v3).
   - **Rede**: configure a rede virtual e o grupo de segurança de rede (NSG).
   - **Credenciais**: defina o usuário administrador e senha.
   - **Grupo de Recursos**: selecione um existente ou crie um novo.

4. Revise as configurações e clique em **Finish**.

---

## 📏 Etapa 3: Redimensionar o Disco do Sistema Operacional

1. No console do VMM, selecione a VM criada.
2. Clique em **Properties** > vá até a aba **Hardware Configuration**.
3. Localize o **disco do sistema operacional**.
4. Altere o **tamanho desejado (em GB)**.
5. Clique em **OK** para aplicar a alteração.

> ⚠️ Lembre-se que o redimensionamento não reduz o tamanho do disco, apenas aumenta.

---

## ➕ Etapa 4: Adicionar um Novo Disco de Dados

1. Selecione a VM no console.
2. Clique em **Properties** > aba **Hardware Configuration**.
3. Clique em **Add** > **Disk**.
4. Defina:
   - Nome do disco
   - Tipo (Managed/Unmanaged)
   - Tamanho (ex: 128 GB)
   - Unidade lógica (ex: L:)
5. Clique em **OK**.

---

## ❌ Etapa 5: Desanexar o Disco Adicional

1. Com a VM **desligada**, vá até **Properties** > **Hardware Configuration**.
2. Localize o disco de dados adicionado.
3. Selecione e clique em **Remove**.
4. Confirme a exclusão (opcional: mantenha o disco no armazenamento se desejar reutilizá-lo).

---

## ✅ Conclusão

Você criou e gerenciou uma VM no Azure utilizando o System Center VMM, incluindo:

- Criação da VM via assistente
- Redimensionamento de disco OS
- Adição e desanexação de disco de dados

Para mais detalhes e comandos avançados, consulte a [documentação oficial da Microsoft](https://learn.microsoft.com/pt-br/system-center/vmm/manage-azure-vms?view=sc-vmm-2022).

---

## 📚 Referência

- [Gerenciar VMs do Azure usando VMM](https://learn.microsoft.com/pt-br/system-center/vmm/manage-azure-vms?view=sc-vmm-2022)
- diretório images: ver as imagens na sequência de *-p1 até *-p22

