---
title: Criar e atualizar contas de usuário para distribuições do Linux
description: Referência para contas de usuário e gerenciamento de permissões com o Subsistema Windows para Linux.
keywords: BashOnWindows, bash, wsl, windows, windows subsystem for linux, windowssubsystem, ubuntu, user accounts
ms.date: 05/12/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: cdb510b8195f18f89ea475889c34850234b7c0e8
ms.sourcegitcommit: 6ff046993e9f196cdfa04f5f91130e0e4ff1e7fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "89427183"
---
# <a name="create-a-user-account-and-password-for-your-new-linux-distribution"></a>Criar uma conta de usuário e uma senha para sua nova distribuição do Linux

Depois que você [habilitar o WSL e instalar uma distribuição do Linux da Microsoft Store](./install-win10.md), a primeira etapa a ser realizada ao abrir a distribuição do Linux recém-instalada será a criação de uma conta, incluindo um **Nome de Usuário** e **Senha**.

- O **nome de usuário** e a **senha** são específicos da sua distribuição do Linux e não têm nenhuma influência sobre seu nome de usuário do Windows.

- Depois de criar o **nome de usuário** e a **senha**, a conta será o usuário padrão para a distribuição e entrará automaticamente na inicialização.

- Essa conta será considerada o administrador do Linux, com a capacidade de executar comandos administrativos `sudo` (Super User Do).

- Cada distribuição do Linux em execução no Subsistema Windows para Linux tem suas próprias contas de usuário e senhas do Linux.  Você precisará configurar uma conta de usuário do Linux sempre que adicionar uma distribuição, reinstalação ou redefinição.

![Desempacotamento do Ubuntu no console do Windows](media/UbuntuInstall.png)

## <a name="update-and-upgrade-packages"></a>Pacotes de atualização e upgrade

A maioria das distribuições é fornecida com um catálogo de pacotes vazio ou mínimo. É altamente recomendável atualizar regularmente seu catálogo de pacotes e fazer upgrade de seus pacotes instalados usando o gerenciador de pacotes preferencial da distribuição. No Debian/Ubuntu, use apt:

```bash
sudo apt update && sudo apt upgrade
```

O Windows não atualiza ou faz upgrade automaticamente de suas distribuições do Linux. Essa é uma tarefa que a maioria dos usuários do Linux prefere controlar por conta própria.

## <a name="reset-your-linux-password"></a>Redefinir sua senha do Linux

Para alterar sua senha, abra a distribuição do Linux (Ubuntu, por exemplo) e insira o comando: `passwd`

Você será solicitado a inserir a senha atual, inserir a nova senha e, em seguida, confirmar a nova senha.

## <a name="forgot-your-password"></a>Esqueceu sua senha

Se você esqueceu a senha da sua distribuição do Linux:

1. Abra o PowerShell e insira a raiz da distribuição do WSL padrão usando o comando: `wsl -u root`

    > Se você precisa atualizar a senha que foi esquecida em uma distribuição que não seja a padrão, use o comando: `wsl -d Debian -u root`, substituindo `Debian` pelo nome da sua distribuição direcionada.

2. Após a distribuição do WSL ter sido aberta no nível raiz dentro do PowerShell, você poderá usar este comando para atualizar a senha: `passwd <WSLUsername>`, em que `<WSLUsername>` é o nome de usuário da conta da distribuição cuja senha você esqueceu.

3. Você será solicitado a inserir uma nova senha do UNIX e, em seguida, confirmar essa senha. Depois da informação de que a senha foi atualizada com êxito, feche o WSL dentro do PowerShell usando o comando: `exit`

> [!NOTE]
> Se você está executando uma versão anterior do sistema operacional Windows, como a 1703 (Atualização do Windows 10 para Criadores) ou a 1709 (Windows 10 Fall Creators Update), consulte a [versão arquivada deste documento de atualização de conta de usuário](./user-support-archived.md).
