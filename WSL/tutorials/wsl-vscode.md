---
title: Introdução ao uso de VS Code com o subsistema do Windows para Linux
description: Saiba como configurar VS Code para criar e depurar código usando o subsistema do Windows para Linux.
keywords: WSL, Windows, windowssubsystem, GNU, Linux, Bash, vs Code, extensão remota, depuração, caminho, Visual Studio
ms.date: 05/28/2020
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 416862201094ba28474918dca8e7d9ce316844cc
ms.sourcegitcommit: d95bdbc2fea991ba14a4c9ec53ee0ec19d6bbdb4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84457778"
---
# <a name="get-started-using-visual-studio-code-with-windows-subsystem-for-linux"></a><span data-ttu-id="b48ca-104">Introdução ao uso de Visual Studio Code com o subsistema do Windows para Linux</span><span class="sxs-lookup"><span data-stu-id="b48ca-104">Get started using Visual Studio Code with Windows Subsystem for Linux</span></span>

<span data-ttu-id="b48ca-105">Visual Studio Code, juntamente com a extensão Remote-WSL, permite que você use o WSL como seu ambiente de desenvolvimento em tempo integral diretamente do VS Code.</span><span class="sxs-lookup"><span data-stu-id="b48ca-105">Visual Studio Code, along with the Remote - WSL extension, enables you to use WSL as your full-time development environment directly from VS Code.</span></span> <span data-ttu-id="b48ca-106">Você pode:</span><span class="sxs-lookup"><span data-stu-id="b48ca-106">You can:</span></span>

* <span data-ttu-id="b48ca-107">desenvolva em um ambiente baseado em Linux</span><span class="sxs-lookup"><span data-stu-id="b48ca-107">develop in a Linux-based environment</span></span>
* <span data-ttu-id="b48ca-108">usar cadeias e utilitários específicos do Linux</span><span class="sxs-lookup"><span data-stu-id="b48ca-108">use Linux-specific toolchains and utilities</span></span>
* <span data-ttu-id="b48ca-109">Execute e depure seus aplicativos baseados em Linux do conforto do Windows mantendo o acesso a ferramentas de produtividade como o Outlook e o Office</span><span class="sxs-lookup"><span data-stu-id="b48ca-109">run and debug your Linux-based applications from the comfort of Windows while maintaining access to productivity tools like Outlook and Office</span></span>
* <span data-ttu-id="b48ca-110">Use o VS Code terminal interno para executar sua distribuição do Linux de sua escolha</span><span class="sxs-lookup"><span data-stu-id="b48ca-110">use the VS Code built-in terminal to run your Linux distribution of choice</span></span>
* <span data-ttu-id="b48ca-111">Aproveite os recursos de VS Code como a [conclusão de código do IntelliSense](https://code.visualstudio.com/docs/editor/intellisense), a reutilização, o [suporte à depuração](https://code.visualstudio.com/docs/nodejs/nodejs-debugging), os [trechos de código](https://code.visualstudio.com/docs/editor/userdefinedsnippets)e os testes de [unidade](https://code.visualstudio.com/docs/python/testing) [linting](https://code.visualstudio.com/docs/python/linting)</span><span class="sxs-lookup"><span data-stu-id="b48ca-111">take advantage of VS Code features like [Intellisense code completion](https://code.visualstudio.com/docs/editor/intellisense), [linting](https://code.visualstudio.com/docs/python/linting), [debug support](https://code.visualstudio.com/docs/nodejs/nodejs-debugging), [code snippets](https://code.visualstudio.com/docs/editor/userdefinedsnippets), and [unit testing](https://code.visualstudio.com/docs/python/testing)</span></span>
* <span data-ttu-id="b48ca-112">Gerencie facilmente seu controle de versão com o suporte interno a [git](https://code.visualstudio.com/docs/editor/versioncontrol#_git-support) do vs Code</span><span class="sxs-lookup"><span data-stu-id="b48ca-112">easily manage your version control with VS Code's built-in [Git support](https://code.visualstudio.com/docs/editor/versioncontrol#_git-support)</span></span>
* <span data-ttu-id="b48ca-113">executar comandos e extensões de VS Code diretamente em seus projetos do WSL</span><span class="sxs-lookup"><span data-stu-id="b48ca-113">run commands and VS Code extensions directly on your WSL projects</span></span>
* <span data-ttu-id="b48ca-114">Edite arquivos em seu sistema operacional Windows Linux ou montado (por exemplo/mnt/c) sem se preocupar com problemas de caminhos, compatibilidade binária ou outros desafios entre sistemas operacionais</span><span class="sxs-lookup"><span data-stu-id="b48ca-114">edit files in your Linux or mounted Windows filesystem (for example /mnt/c) without worrying about pathing issues, binary compatibility, or other cross-OS challenges</span></span>

## <a name="install-vs-code-and-the-remote-wsl-extension"></a><span data-ttu-id="b48ca-115">Instalar VS Code e a extensão WSL remota</span><span class="sxs-lookup"><span data-stu-id="b48ca-115">Install VS Code and the Remote WSL extension</span></span>

* <span data-ttu-id="b48ca-116">Visite a [página de instalação do vs Code](https://code.visualstudio.com/download) e selecione o instalador de 32 ou 64 bits.</span><span class="sxs-lookup"><span data-stu-id="b48ca-116">Visit the [VS Code install page](https://code.visualstudio.com/download) and select the 32 or 64 bit installer.</span></span> <span data-ttu-id="b48ca-117">Instale o Visual Studio Code no Windows (não em seu sistema de arquivos WSL).</span><span class="sxs-lookup"><span data-stu-id="b48ca-117">Install Visual Studio Code on Windows (not in your WSL file system).</span></span>

* <span data-ttu-id="b48ca-118">Quando solicitado a **selecionar tarefas adicionais** durante a instalação, certifique-se de marcar a opção **Adicionar ao caminho** para que você possa abrir facilmente uma pasta no WSL usando o comando de código.</span><span class="sxs-lookup"><span data-stu-id="b48ca-118">When prompted to **Select Additional Tasks** during installation, be sure to check the **Add to PATH** option so you can easily open a folder in WSL using the code command.</span></span>

* <span data-ttu-id="b48ca-119">Instale o [pacote de extensão de desenvolvimento remoto](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack).</span><span class="sxs-lookup"><span data-stu-id="b48ca-119">Install the [Remote Development extension pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack).</span></span> <span data-ttu-id="b48ca-120">Esse pacote de extensão inclui a extensão WSL remota, além das extensões SSH remota e contêineres remotos, permitindo que você abra qualquer pasta em um contêiner, em um computador remoto ou em WSL.</span><span class="sxs-lookup"><span data-stu-id="b48ca-120">This extension pack includes the Remote - WSL extension, in addition to the Remote - SSH, and Remote - Containers extensions, enabling you to open any folder in a container, on a remote machine, or in WSL.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b48ca-121">Para instalar a extensão Remote-WSL, você precisará da versão [1,35 pode ser lançada](https://code.visualstudio.com/updates/v1_35) ou posterior do vs Code.</span><span class="sxs-lookup"><span data-stu-id="b48ca-121">In order to install the Remote-WSL extension, you will need the [1.35 May release](https://code.visualstudio.com/updates/v1_35) version or later of VS Code.</span></span> <span data-ttu-id="b48ca-122">Não recomendamos o uso de WSL em VS Code sem a extensão WSL remota, pois você perderá o suporte para preenchimento automático, depuração, refiapo, etc. Fatos divertidos: essa extensão WSL é instalada em $HOME/.vscode-Server/Extensions.</span><span class="sxs-lookup"><span data-stu-id="b48ca-122">We do not recommend using WSL in VS Code without the Remote-WSL extension as you will lose support for auto-complete, debugging, linting, etc. Fun fact: this WSL extension is installed in $HOME/.vscode-server/extensions.</span></span>

## <a name="update-your-linux-distribution"></a><span data-ttu-id="b48ca-123">Atualizar sua distribuição do Linux</span><span class="sxs-lookup"><span data-stu-id="b48ca-123">Update your Linux distribution</span></span>

<span data-ttu-id="b48ca-124">Algumas distribuições do Linux WSL são bibliotecas que são necessárias para que o servidor de VS Code seja inicializado.</span><span class="sxs-lookup"><span data-stu-id="b48ca-124">Some WSL Linux distributions are lacking libraries that are required by the VS Code server to start up.</span></span> <span data-ttu-id="b48ca-125">Você pode adicionar bibliotecas adicionais à sua distribuição do Linux usando seu Gerenciador de pacotes.</span><span class="sxs-lookup"><span data-stu-id="b48ca-125">You can add additional libraries into your Linux distribution by using its package manager.</span></span>

<span data-ttu-id="b48ca-126">Por exemplo, para atualizar o Debian ou Ubuntu, use:</span><span class="sxs-lookup"><span data-stu-id="b48ca-126">For example, to update Debian or Ubuntu, use:</span></span>

```bash
sudo apt-get update
```

<span data-ttu-id="b48ca-127">Para adicionar wget (para recuperar o conteúdo de servidores Web) e certificados de CA (para permitir que aplicativos baseados em SSL verifiquem a autenticidade das conexões SSL), digite:</span><span class="sxs-lookup"><span data-stu-id="b48ca-127">To add wget (to retrieve content from web servers) and ca-certificates (to allow SSL-based applications to check for the authenticity of SSL connections), enter:</span></span>

```bash
sudo apt-get install wget ca-certificates
```

## <a name="open-a-wsl-project-in-visual-studio-code"></a><span data-ttu-id="b48ca-128">Abra um projeto do WSL no Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b48ca-128">Open a WSL project in Visual Studio Code</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="b48ca-129">Na linha de comando</span><span class="sxs-lookup"><span data-stu-id="b48ca-129">From the command-line</span></span>

<span data-ttu-id="b48ca-130">Para abrir um projeto da sua distribuição do WSL, abra a linha de comando da distribuição e digite:`code .`</span><span class="sxs-lookup"><span data-stu-id="b48ca-130">To open a project from your WSL distribution, open the distribution's command line and enter: `code .`</span></span>

![Abrir o projeto WSL com o servidor remoto VS Code](../media/wsl-open-vs-code.gif)

### <a name="from-vs-code"></a><span data-ttu-id="b48ca-132">De VS Code</span><span class="sxs-lookup"><span data-stu-id="b48ca-132">From VS Code</span></span>

<span data-ttu-id="b48ca-133">Você também pode acessar mais VS Code opções remotas usando o atalho: `CTRL+SHIFT+P` em vs Code para abrir a paleta de comandos.</span><span class="sxs-lookup"><span data-stu-id="b48ca-133">You can also access more VS Code Remote options by using the shortcut: `CTRL+SHIFT+P` in VS Code to bring up the command palette.</span></span> <span data-ttu-id="b48ca-134">Se você digitar, `VSCODE-REMOTE` verá todas as vs Code opções remotas disponíveis, permitindo que você reabra a pasta em uma sessão remota, especifique a distribuição que deseja abrir e muito mais.</span><span class="sxs-lookup"><span data-stu-id="b48ca-134">If you then type `VSCODE-REMOTE` you will see all of the VS Code Remote options available, allowing you to reopen the folder in a remote session, specify which distribution you want to open in, and more.</span></span>

![Paleta de comandos do VS Code](../media/vscode-remote-command-palette.png)

## <a name="extensions-inside-of-vs-code-remote"></a><span data-ttu-id="b48ca-136">Extensões dentro de VS Code remotas</span><span class="sxs-lookup"><span data-stu-id="b48ca-136">Extensions inside of VS Code Remote</span></span>

<span data-ttu-id="b48ca-137">A extensão Remote-WSL divide VS Code em uma arquitetura de "cliente-servidor", com o cliente (a interface do usuário) em execução no computador com Windows e no servidor (seu código, git, plug-ins, etc) em execução remota.</span><span class="sxs-lookup"><span data-stu-id="b48ca-137">The Remote-WSL extension splits VS Code into a “client-server” architecture, with the client (the user interface) running on your Windows machine and the server (your code, Git, plugins, etc) running remotely.</span></span>

<span data-ttu-id="b48ca-138">Ao executar VS Code remoto, a seleção da guia ' extensões ' exibirá uma lista de extensões divididas entre o computador local e sua distribuição WSL.</span><span class="sxs-lookup"><span data-stu-id="b48ca-138">When running VS Code Remote, selecting the 'Extensions' tab will display a list of extensions split between your local machine and your WSL distribution.</span></span>

<span data-ttu-id="b48ca-139">A instalação de uma extensão local, como um [tema](https://marketplace.visualstudio.com/search?target=VSCode&category=Themes&sortBy=Installs), só precisa ser instalada uma vez.</span><span class="sxs-lookup"><span data-stu-id="b48ca-139">Installing a local extension, like a [theme](https://marketplace.visualstudio.com/search?target=VSCode&category=Themes&sortBy=Installs),  only needs to be installed once.</span></span>

<span data-ttu-id="b48ca-140">Algumas extensões, como a [extensão do Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python) ou qualquer coisa que manipule coisas como refazer o pano ou a depuração, devem ser instaladas separadamente em cada distribuição de WSL remota.</span><span class="sxs-lookup"><span data-stu-id="b48ca-140">Some extensions, like the [Python extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python) or anything that handles things like linting or debugging, must be installed separately on each remote WSL distributions.</span></span> <span data-ttu-id="b48ca-141">VS Code exibirá um ícone de aviso ⚠ , junto com um botão "instalar no WSL" verde, se você tiver uma extensão instalada localmente que não esteja instalada em seu WSL remoto.</span><span class="sxs-lookup"><span data-stu-id="b48ca-141">VS Code will display a warning icon ⚠, along with a green "Install in WSL" button, if you have an extension locally installed that is not installed on your WSL Remote.</span></span>

![VS Code com extensões remotas do WSL vs. extensões locais](../media/vscode-remote-wsl-extensions.png)

<span data-ttu-id="b48ca-143">Para obter mais informações, consulte o VS Code docs:</span><span class="sxs-lookup"><span data-stu-id="b48ca-143">For further information, see the VS Code docs:</span></span>

* <span data-ttu-id="b48ca-144">Quando VS Code Remote é iniciado no WSL, nenhum script de inicialização do Shell é executado.</span><span class="sxs-lookup"><span data-stu-id="b48ca-144">When VS Code Remote is started in WSL, no shell startup scripts are run.</span></span> <span data-ttu-id="b48ca-145">Consulte o [artigo script de configuração de ambiente avançado](https://code.visualstudio.com/docs/remote/wsl#_advanced-environment-setup-script) para obter mais informações sobre como executar comandos adicionais ou modificar o ambiente.</span><span class="sxs-lookup"><span data-stu-id="b48ca-145">See this [advanced environment setup script article](https://code.visualstudio.com/docs/remote/wsl#_advanced-environment-setup-script) for more info on how to run additional commands or modify the environment.</span></span>

* <span data-ttu-id="b48ca-146">Problemas ao iniciar o VS Code na linha de comando do WSL?</span><span class="sxs-lookup"><span data-stu-id="b48ca-146">Having problems launching VS Code from your WSL command line?</span></span> <span data-ttu-id="b48ca-147">Este [Guia de solução de problemas](https://code.visualstudio.com/docs/remote/troubleshooting#_fixing-problems-with-the-code-command-not-working) inclui dicas sobre como alterar variáveis de caminho, resolver erros de extensão sobre dependências ausentes, resolver problemas de finalização de linha do git, instalar um VSIX local em um computador remoto, iniciar uma janela do navegador, porta de localhost do bloqueador, soquetes da Web não funcionando, erros de armazenamento de dados de extensão e muito mais.</span><span class="sxs-lookup"><span data-stu-id="b48ca-147">This [troubleshooting guide](https://code.visualstudio.com/docs/remote/troubleshooting#_fixing-problems-with-the-code-command-not-working) includes tips on changing path variables, resolving extension errors about missing dependencies, resolving Git line ending issues, installing a local VSIX on a remote machine, launching a browser window, blocker localhost port, web sockets not working, errors storing extension data, and more.</span></span>

## <a name="install-git-optional"></a><span data-ttu-id="b48ca-148">Instalar o Git (opcional)</span><span class="sxs-lookup"><span data-stu-id="b48ca-148">Install Git (optional)</span></span>

<span data-ttu-id="b48ca-149">Se você pretende colaborar com outras pessoas ou hospedar seu projeto em um site de software livre (como o GitHub), o VS Code é compatível com o [controle de versão com o Git](https://code.visualstudio.com/docs/editor/versioncontrol#_git-support).</span><span class="sxs-lookup"><span data-stu-id="b48ca-149">If you plan to collaborate with others, or host your project on an open-source site (like GitHub), VS Code supports [version control with Git](https://code.visualstudio.com/docs/editor/versioncontrol#_git-support).</span></span> <span data-ttu-id="b48ca-150">A guia Controle do Código-fonte no VS Code acompanha todas as alterações e tem comandos Git comuns (add, commit, push e pull) incorporados diretamente na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="b48ca-150">The Source Control tab in VS Code tracks all of your changes and has common Git commands (add, commit, push, pull) built right into the UI.</span></span>

<span data-ttu-id="b48ca-151">Para instalar o Git, consulte [Configurar o Git para funcionar com o subsistema do Windows para Linux](./wsl-git.md).</span><span class="sxs-lookup"><span data-stu-id="b48ca-151">To install Git, see [set up Git to work with Windows Subsystem for Linux](./wsl-git.md).</span></span>

## <a name="install-windows-terminal-optional"></a><span data-ttu-id="b48ca-152">Instalar o Terminal do Windows (opcional)</span><span class="sxs-lookup"><span data-stu-id="b48ca-152">Install Windows Terminal (optional)</span></span>

<span data-ttu-id="b48ca-153">O novo terminal do Windows permite várias guias (alternar rapidamente entre o prompt de comando, o PowerShell ou várias distribuições do Linux), associações de chave personalizadas (crie suas próprias teclas de atalho para abrir ou fechar guias, copiar + colar, etc.), emojis ☺ e temas personalizados (esquemas de cores, estilos e tamanhos de fonte, imagem de plano de fundo/desfoque</span><span class="sxs-lookup"><span data-stu-id="b48ca-153">The new Windows Terminal enables multiple tabs (quickly switch between Command Prompt, PowerShell, or multiple Linux distributions), custom key bindings (create your own shortcut keys for opening or closing tabs, copy+paste, etc.), emojis ☺, and custom themes (color schemes, font styles and sizes, background image/blur/transparency).</span></span> <span data-ttu-id="b48ca-154">Saiba mais nos [documentos de terminal do Windows](https://docs.microsoft.com/windows/terminal).</span><span class="sxs-lookup"><span data-stu-id="b48ca-154">Learn more in the [Windows Terminal docs](https://docs.microsoft.com/windows/terminal).</span></span>

1. <span data-ttu-id="b48ca-155">Obter o [terminal do Windows na Microsoft Store](https://www.microsoft.com/store/apps/9n0dx20hk701): ao instalar por meio da loja, as atualizações são manipuladas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b48ca-155">Get [Windows Terminal in the Microsoft Store](https://www.microsoft.com/store/apps/9n0dx20hk701): By installing via the store, updates are handled automatically.</span></span>

2. <span data-ttu-id="b48ca-156">Depois de instalado, abra o Terminal do Windows e selecione **Configurações** para personalizar o terminal usando o arquivo `profile.json`.</span><span class="sxs-lookup"><span data-stu-id="b48ca-156">Once installed, open Windows Terminal and select **Settings** to customize your terminal using the `profile.json` file.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b48ca-157">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b48ca-157">Additional Resources</span></span>

* [<span data-ttu-id="b48ca-158">Desenvolvimento VS Code remoto</span><span class="sxs-lookup"><span data-stu-id="b48ca-158">VS Code Remote Development</span></span>](https://code.visualstudio.com/docs/remote/remote-overview)
* [<span data-ttu-id="b48ca-159">Dicas e truques de desenvolvimento remoto</span><span class="sxs-lookup"><span data-stu-id="b48ca-159">Remote development tips and tricks</span></span>](https://code.visualstudio.com/docs/remote/troubleshooting)
* [<span data-ttu-id="b48ca-160">Tutorial de desenvolvimento remoto com WSL</span><span class="sxs-lookup"><span data-stu-id="b48ca-160">Remote development with WSL tutorial</span></span>](https://code.visualstudio.com/remote-tutorials/wsl/getting-started)
* [<span data-ttu-id="b48ca-161">Usando o Docker com WSL 2 e VS Code</span><span class="sxs-lookup"><span data-stu-id="b48ca-161">Using Docker with WSL 2 and VS Code</span></span>](https://code.visualstudio.com/blogs/2020/03/02/docker-in-wsl2)
* [<span data-ttu-id="b48ca-162">Usando C++ e WSL no VS Code</span><span class="sxs-lookup"><span data-stu-id="b48ca-162">Using C++ and WSL in VS Code</span></span>](https://code.visualstudio.com/docs/cpp/config-wsl)
* [<span data-ttu-id="b48ca-163">Serviço R Remoto para Linux</span><span class="sxs-lookup"><span data-stu-id="b48ca-163">Remote R Service for Linux</span></span>](https://docs.microsoft.com/visualstudio/rtvs/setting-up-remote-r-service-on-linux?view=vs-2017)

<span data-ttu-id="b48ca-164">Algumas extensões adicionais que talvez você queira considerar incluem:</span><span class="sxs-lookup"><span data-stu-id="b48ca-164">A few additional extensions you may want to consider include:</span></span>

* <span data-ttu-id="b48ca-165">[Mapas de teclas de outros editores](https://marketplace.visualstudio.com/search?target=VSCode&category=Keymaps&sortBy=Downloads): essas extensões poderão ajudar na familiaridade com seu ambiente se você estiver fazendo a transição de outro editor de texto (como Atom, Sublime, Vim, eMacs, Notepad++ etc.).</span><span class="sxs-lookup"><span data-stu-id="b48ca-165">[Keymaps from other editors](https://marketplace.visualstudio.com/search?target=VSCode&category=Keymaps&sortBy=Downloads): These extensions can help your environment feel right at home if you're transitioning from another text editor (like Atom, Sublime, Vim, eMacs, Notepad++, etc).</span></span>
* <span data-ttu-id="b48ca-166">[Sincronização de configurações](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync): permite que você sincronize suas configurações do VS Code em diferentes instalações usando o GitHub.</span><span class="sxs-lookup"><span data-stu-id="b48ca-166">[Settings Sync](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync): Enables you to synchronize your VS Code settings across different installations using GitHub.</span></span> <span data-ttu-id="b48ca-167">Se você trabalha em diferentes computadores, isso ajuda a manter seu ambiente consistente entre eles.</span><span class="sxs-lookup"><span data-stu-id="b48ca-167">If you work on different machines, this helps keep your environment consistent across them.</span></span>
* <span data-ttu-id="b48ca-168">[Depurador para Chrome](https://code.visualstudio.com/blogs/2016/02/23/introducing-chrome-debugger-for-vs-code): depois de concluir o desenvolvimento no lado do servidor com o Linux, você precisará desenvolver e testar o lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="b48ca-168">[Debugger for Chrome](https://code.visualstudio.com/blogs/2016/02/23/introducing-chrome-debugger-for-vs-code): Once you finish developing on the server side with Linux, you'll need to develop and test the client side.</span></span> <span data-ttu-id="b48ca-169">Essa extensão integra seu editor do VS Code ao serviço de depuração do navegador Chrome, tornando as coisas um pouco mais eficientes.</span><span class="sxs-lookup"><span data-stu-id="b48ca-169">This extension integrates your VS Code editor with your Chrome browser debugging service, making things a bit more efficient.</span></span>