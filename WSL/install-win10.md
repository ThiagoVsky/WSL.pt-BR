---
title: Instalar o WSL (Subsistema Windows para Linux) no Windows 10
description: Saiba como instalar o Subsistema do Windows para Linux no Windows 10. O Windows 10 precisa ser atualizado para a versão 2004, build 19041 ou superior.
keywords: BashOnWindows, bash, wsl, windows, windows subsystem for linux, windowssubsystem, ubuntu, debian, suse, windows 10, install, enable, WSL2, version 2
ms.date: 05/12/2020
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: 14e1697d1f2ac7a1efa17368be830a5c22973bc6
ms.sourcegitcommit: 910845e9b3f980b2c5b9b4968331a706720603c6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2020
ms.locfileid: "89058491"
---
# <a name="windows-subsystem-for-linux-installation-guide-for-windows-10"></a>Guia de instalação do Subsistema Windows para Linux para Windows 10

## <a name="install-the-windows-subsystem-for-linux"></a>Instalar o Subsistema Windows para Linux

Antes de instalar as distribuições do Linux no Windows, você deverá habilitar o recurso opcional "Subsistema do Windows para Linux".

Abra o PowerShell como administrador e execute:

```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

Para instalar apenas o WSL 1, você deve reiniciar o computador e passar para [Instalar a distribuição do Linux de sua escolha](./install-win10.md#install-your-linux-distribution-of-choice), caso contrário, espere para reiniciar e passar para a atualização para o WSL 2. Leia mais sobre a [Comparação entre o WSL 2 e o WSL 1](./compare-versions.md).

## <a name="update-to-wsl-2"></a>Atualizar para o WSL 2

Para atualizar para o WSL 2, você deve atender aos seguintes critérios:

- Executar o Windows 10, [atualizado para a versão 1903 ou superior](ms-settings:windowsupdate), **Build 18362** ou superior para sistemas x64.
- Executar o Windows 10, atualizado para a versão 2004 ou superior, **build 19041**, para sistemas ARM64.
- Observe que, se você estiver no Windows 10 versão 1903 ou 1909, será necessário verificar se você tem o backport apropriado. As instruções podem ser [encontradas aqui](https://devblogs.microsoft.com/commandline/wsl-2-support-is-coming-to-windows-10-versions-1903-and-1909/#how-do-i-get-it). 

- Verifique sua versão do Windows selecionando a **tecla do logotipo do Windows + R**, digite **winver**, selecione **OK**. (Ou digite o comando `ver` no prompt de comando do Windows). [Faça a atualização para a versão mais recente do Windows](ms-settings:windowsupdate) se o build for anterior ao 18361. [Obtenha o Assistente do Windows Update](https://www.microsoft.com/software-download/windows10).

### <a name="enable-the-virtual-machine-platform-optional-component"></a>Habilite o componente opcional "Plataforma de máquina virtual"

Antes de instalar o WSL 2, você deve habilitar o recurso opcional "Plataforma de Máquina Virtual".

Abra o PowerShell como administrador e execute:

```powershell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```

**Reinicie** o computador para concluir a instalação do WSL e a atualização para o WSL 2.

### <a name="set-wsl-2-as-your-default-version"></a>Definir o WSL 2 como sua versão padrão

Abra o PowerShell como administrador e execute este comando para definir o WSL 2 como a versão padrão ao instalar uma nova distribuição do Linux:

```powershell
wsl --set-default-version 2
```

Você poderá ver esta mensagem depois de executar esse comando: `WSL 2 requires an update to its kernel component. For information please visit https://aka.ms/wsl2kernel`. Siga o link ([https://aka.ms/wsl2kernel](https://aka.ms/wsl2kernel)) e instale o MSI dessa página em nossa documentação para instalar um kernel do Linux em seu computador para o WSL 2 usar. Depois de instalar o kernel, execute o comando novamente e ele deverá ser concluído com êxito sem mostrar a mensagem. 

> [!NOTE]
> A atualização da WSL 1 para a WSL 2 pode levar vários minutos para ser concluída, dependendo do tamanho da sua distribuição alvo. Se você estiver executando uma instalação mais antiga (herdada) do WSL 1 da Atualização para Criadores ou da Atualização de Aniversário do Windows 10, poderá encontrar um erro de atualização. Siga estas instruções para [desinstalar e remover as distribuições herdadas](https://docs.microsoft.com/windows/wsl/install-legacy#uninstallingremoving-the-legacy-distro). 
>
> Se `wsl --set-default-version` resultar como um comando inválido, insira `wsl --help`. Se `--set-default-version` não estiver listado, isso significa que o sistema operacional não é compatível com ele, e você precisará atualizá-lo para a versão 1903, Build 18362 ou superior.

## <a name="install-your-linux-distribution-of-choice"></a>Instalar a distribuição do Linux de sua escolha

1. Abra a [Microsoft Store](https://aka.ms/wslstore) e escolha sua distribuição do Linux favorita.

    ![Exibição das distribuições do Linux na Microsoft Store](media/store.png)

    Os links a seguir abrirão a página da Microsoft Store para cada distribuição:

    - [Ubuntu 16.04 LTS](https://www.microsoft.com/store/apps/9pjn388hp8c9)
    - [Ubuntu 18.04 LTS](https://www.microsoft.com/store/apps/9N9TNGVNDL3Q)
    - [Ubuntu 20.04 LTS](https://www.microsoft.com/store/apps/9n6svws3rx71)
    - [OpenSUSE Leap 15.1](https://www.microsoft.com/store/apps/9NJFZK00FGKV)
    - [SUSE Linux Enterprise Server 12 SP5](https://www.microsoft.com/store/apps/9MZ3D1TRP8T1)
    - [SUSE Linux Enterprise Server 15 SP1](https://www.microsoft.com/store/apps/9PN498VPMF3Z)
    - [Kali Linux](https://www.microsoft.com/store/apps/9PKR34TNCV07)
    - [Debian GNU/Linux](https://www.microsoft.com/store/apps/9MSVKQC78PK6)
    - [Fedora Remix para WSL](https://www.microsoft.com/store/apps/9n6gdm4k2hnc)
    - [Pengwin](https://www.microsoft.com/store/apps/9NV1GV1PXZ6P)
    - [Pengwin Enterprise](https://www.microsoft.com/store/apps/9N8LP0X93VCP)
    - [Alpine WSL](https://www.microsoft.com/store/apps/9p804crf0395)

2. Na página da distribuição, selecione "Obter".

    ![Distribuições do Linux na Microsoft Store](media/UbuntuStore.png)

## <a name="set-up-a-new-distribution"></a>Configurar uma nova distribuição

Na primeira vez que você iniciar uma distribuição do Linux recém-instalada, uma janela de console será aberta e será solicitado que você aguarde um ou dois minutos para que os arquivos sejam descompactados e armazenados em seu PC. Todas as futuras inicializações deverão levar menos de um segundo.

Em seguida, você precisará [criar uma conta de usuário e uma senha para sua nova distribuição do Linux](./user-support.md).

![Desempacotamento do Ubuntu no console do Windows](media/UbuntuInstall.png)

## <a name="set-your-distribution-version-to-wsl-1-or-wsl-2"></a>Definir a versão de distribuição para WSL 1 ou WSL 2

Verifique a versão do WSL atribuída a cada uma das distribuições do Linux instaladas abrindo a linha de comando do PowerShell e inserindo o comando (disponível somente no [Windows Build 18362 ou superior](ms-settings:windowsupdate)): `wsl -l -v`

```powershell
wsl --list --verbose
```

Para definir uma distribuição para ter suporte de qualquer versão do WSL, execute:

```powershell
wsl --set-version <distribution name> <versionNumber>
```

Assegure-se de substituir `<distribution name>` pelo nome real da sua distribuição e `<versionNumber>` pelo número '1' ou '2'. Você pode retornar ao WSL 1 a qualquer momento executando o mesmo comando acima, mas substituindo “2” por “1”.

Além disso, se quiser tornar o WSL 2 sua arquitetura padrão, você poderá fazê-lo com este comando:

```powershell
wsl --set-default-version 2
```

Isso definirá a versão de qualquer nova distribuição instalada no WSL 2.

## <a name="troubleshooting-installation"></a>Como solucionar problemas de instalação

Veja abaixo erros relacionados e correções sugeridas. Consulte a [página de solução de problemas do WSL](troubleshooting.md) para ver outros erros comuns e suas soluções.

- **Falha na instalação com o erro 0x80070003**
  - O Subsistema Windows para Linux é executado somente na unidade do sistema (normalmente, a unidade `C:`). Verifique se as distribuições estão armazenadas na unidade do sistema:  
  - Abra **Configurações** -> **Armazenamento** -> **Mais Configurações de Armazenamento: Altere onde o novo conteúdo é salvo**
    ![Imagem das configurações do sistema para instalar aplicativos na unidade C:](media/AppStorage.png)

- **WslRegisterDistribution falhou com o erro 0x8007019e**
  - O componente opcional do Subsistema Windows para Linux não está habilitado:
  - Abra **Painel de Controle** -> **Programas e Recursos** -> **Ativar ou Desativar Recursos do Windows** -> Selecione **Subsistema do Windows para Linux** ou use o cmdlet PowerShell mencionado no início deste artigo.

- **Ocorreu falha na instalação com o erro 0x80070003 ou 0x80370102**
  - Verifique se a virtualização está habilitada dentro do BIOS do seu computador. As instruções para fazer isso variam de um computador para o outro e muito provavelmente estarão sob opções relacionadas à CPU.

- **Erro ao tentar fazer upgrade: `Invalid command line option: wsl --set-version Ubuntu 2`**
  - Verifique se você tem o Subsistema do Windows para Linux habilitado e se está usando o Windows versão do Build 18362 ou superior. Para habilitar o WSL, execute este comando em um prompt do PowerShell com privilégios de administrador: `Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`.

- **A operação solicitada não pôde ser concluída devido a uma limitação do sistema de disco virtual. Os arquivos do disco rígido virtual devem ser descompactados e descriptografados e não devem ser esparsos.**
  - Desmarque "Compactar conteúdo" (bem como "Criptografar conteúdo", se estiver marcado) abrindo a pasta de perfil da sua distribuição do Linux. Ela deve estar localizada em uma pasta no sistema de arquivos do Windows, algo como: `USERPROFILE%\AppData\Local\Packages\CanonicalGroupLimited...`
  - Nesse perfil de distribuição do Linux, deve haver uma pasta LocalState. Clique com o botão direito do mouse nessa pasta para exibir um menu de opções. Selecione Propriedades > Avançado e, em seguida, verifique se as caixas de seleção "Compactar conteúdo para economizar espaço em disco" e "Criptografar conteúdo para proteger dados" estão desmarcadas (não selecionadas). Se for solicitado que você aplique isso apenas à pasta atual ou a todas as subpastas e arquivos, selecione "somente esta pasta" porque você só vai limpar o sinalizador de compactação. Depois disso, o comando `wsl –set-version` deve funcionar.

![Captura de tela das configurações da propriedade de distribuição do WSL](media/troubleshooting-virtualdisk-compress.png)

> [!NOTE]
> No meu caso, a pasta LocalState da minha distribuição do Ubuntu 18.04 estava localizada em C:\Users\<my-user-name>\AppData\Local\Packages\CanonicalGroupLimited.Ubuntu18.04onWindows_79rhkp1fndgsc
>
> Para obter informações atualizadas, verifique o [thread 4103 do GitHub dos documentos do WSL](https://github.com/microsoft/WSL/issues/4103) em que esse problema está sendo acompanhado.

- **O termo 'wsl' não é reconhecido como nome de um cmdlet, uma função, um arquivo de script ou um programa operável.**
  - Verifique se o [componente opcional do Subsistema do Windows para Linux está instalado](./install-win10.md#enable-the-virtual-machine-platform-optional-component). Além disso, se você estiver usando um dispositivo ARM64 e executar esse comando no PowerShell, receberá esse erro. Em vez disso, execute `wsl.exe` no [PowerShell Core](https://docs.microsoft.com/powershell/scripting/install/installing-powershell-core-on-windows?view=powershell-6) ou no prompt de comando.
