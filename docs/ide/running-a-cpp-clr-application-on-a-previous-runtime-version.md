---
title: Запуск приложения - clr C++ в предыдущей версии среды выполнения | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- applications [C++], runtime version specified
- versions [C++]
- app.config files, runtime version specified
- compatibility [C++], runtime version specified
- backward compatibility [C++], runtime version specified
- application deployment [C++], runtime version specified
- common language runtime [C++], version specified
- deploying applications [C++], runtime version specified
ms.assetid: 940171b7-6937-4b14-8e87-c199e23f4f2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f8e76930eb9191d27085d92a9d3a678812715fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="running-a-c-clr-application-on-a-previous-runtime-version"></a>Выполнение приложения C++ с параметром /clr в более ранней версии среды выполнения
Если не указано иначе, приложение C++ .NET Framework создается для запуска в версии среды выполнения (CLR), используемый компилятором для построения приложения. Тем не менее это приложение .exe, предназначенную для одной версии среды выполнения для выполнения в любой версии, который предоставляет требуемые функции.  
  
 Чтобы сделать это, укажите файл app.config, который содержит сведения о версии среды выполнения в `supportedRuntime` тег.  
  
 Во время выполнения в файл app.config должен иметь имя в формате *имяфайла.расширение*.config, где *имяфайла.расширение* является имя исполняемого файла, запустившего приложение, и он должен быть в том же каталоге, что исполняемый файл. Например если приложение называется TestApp.exe, файл app.config будет называться TestApp.exe.config.  
  
 Если указать более одной версии среды выполнения и приложение будет выполняться на компьютере с более чем одной версии установленной среды выполнения, приложение использует первой версии, указано в файле конфигурации и работает.  
  
 Дополнительные сведения см. в разделе [как: настройте приложение для целевой версии .NET Framework](http://msdn.microsoft.com/en-us/5247b307-89ca-417b-8dd0-e8f9bd2f4717).  
  
 Для запуска в версии 1.0 или 1.1 среда CLR, приложения, разработанного на Visual C++ компилятора должны быть скомпилированы с помощью [/clr:initialAppDomain](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="see-also"></a>См. также  
 [Развертывание приложений для настольных систем](../ide/deploying-native-desktop-applications-visual-cpp.md)