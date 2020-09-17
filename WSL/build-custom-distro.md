---
title: Criar um distribuição Linux personalizado para o WSL
description: Saiba como criar uma distribuição personalizada do Linux para o subsistema do Windows para Linux.
keywords: BashOnWindows, Bash, WSL, Windows, subsistema do Windows, distribuição, personalizado
ms.date: 09/15/2020
ms.topic: article
ms.openlocfilehash: 8b898cbee12aaff6e575afbeaa57d52c3a2c9e75
ms.sourcegitcommit: ba3399a5ffeffd23551315acd04ea6848d30693b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90719145"
---
# <a name="creating-a-custom-linux-distribution-for-wsl"></a>Criando uma distribuição personalizada do Linux para WSL

Use nosso exemplo de WSL de software livre para criar pacotes WSL distribuição para o Microsoft Store e/ou para criar pacotes personalizados do Linux distribuição para Sideload. Você pode encontrar o [repositório do iniciador distribuição](https://github.com/Microsoft/WSL-DistroLauncher) no github.

Este projeto permite:

- Os mantenedores de distribuição do Linux para empacotar e enviar uma distribuição do Linux como um Appx executado no WSL
- Desenvolvedores para criar distribuições personalizadas do Linux que podem ser sideloaddas em sua máquina de desenvolvimento

## <a name="background"></a>Tela de fundo

Distribuímos o Linux distribuições para WSL como aplicativos UWP por meio do Microsoft Store. Você pode instalar os aplicativos que serão executados em WSL-o subsistema que reside no kernel do Windows. Esse mecanismo de entrega tem muitos benefícios como discutidos em uma [postagem no blog anterior](https://blogs.msdn.microsoft.com/commandline/2017/07/10/ubuntu-now-available-from-the-windows-store/).

## <a name="sideloading-a-custom-linux-distro-package"></a>Sideload de um pacote personalizado de distribuição do Linux

Você pode criar um pacote personalizado do Linux distribuição como um aplicativo para Sideload em seu computador pessoal. Observe que seu pacote personalizado não seria distribuído por meio do Microsoft Store, a menos que você envie como um mantenedor de distribuição.
Para configurar seu computador para aplicativos Sideload, você precisará habilitá-lo nas configurações do sistema em "para desenvolvedores".  Certifique-se de ter o modo de desenvolvedor ou aplicativos Sideload selecionados

## <a name="for-linux-distro-maintainers"></a>Para os mantenedores do Linux distribuição

Para enviar para a loja, você precisará trabalhar conosco para receber aprovação de publicação. Se você for um proprietário de distribuição do Linux interessado em adicionar sua distribuição ao Microsoft Store, entre em contato com wslpartners@microsoft.com .

## <a name="getting-started"></a>Introdução

Siga as instruções no [repositório GitHub do iniciador do distribuição](https://github.com/Microsoft/WSL-DistroLauncher) para criar um pacote personalizado do distribuição do Linux.

## <a name="team-blogs"></a>Blogs da equipe

-  [Abrir o fornecimento de um exemplo de WSL para os mantenedores de distribuição do Linux e distribuição personalizada do Linux de Sideload](https://blogs.msdn.microsoft.com/commandline/2018/03/26/wsl-distro-launcher/)
- [Blog de linha de comando](https://blogs.msdn.microsoft.com/commandline/)

## <a name="provide-feedback"></a>Forneça comentários

- [Repositório GitHub do iniciador distribuição](https://github.com/Microsoft/WSL-DistroLauncher)
- [Rastreador de problemas do GitHub para WSL](https://github.com/Microsoft/BashOnWindows/issues)
- [Portal UserVoice de linha de comando](https://wpdev.uservoice.com/forums/266908-command-prompt-console-bash-on-ubuntu-on-windo/category/161892-bash)
