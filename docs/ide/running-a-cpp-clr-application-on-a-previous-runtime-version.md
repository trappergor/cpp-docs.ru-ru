---
title: Выполнение приложения C++ с параметром -clr в более ранней версии среды выполнения | Документы Майкрософт
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
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33323619"
---
# <a name="running-a-c-clr-application-on-a-previous-runtime-version"></a>Выполнение приложения C++ с параметром /clr в более ранней версии среды выполнения
Если не указано иное, приложение .NET Framework на C++ предназначено для запуска в версии среды CLR, используемой компилятором для сборки приложения. Однако приложение EXE, созданное для одной версии среды выполнения, может запускаться в другой версии, если она предоставляет необходимые функции.  
  
 Для этого предоставьте файл app.config с информацией о версии среды выполнения в теге `supportedRuntime`.  
  
 Во время выполнения имя файла app.config должно иметь формат *имя_файла.расширение*.config, где *имя_файла.расширение* — это имя исполняемого файла, запустившего приложение, а сам этот файл должен находиться в одном каталоге с исполняемым файлом. Например, если приложение называется TestApp.exe, файл app.config будет называться TestApp.exe.config.  
  
 Если указано несколько версий среды выполнения и приложение выполняется на компьютере с несколькими установленными версиями среды выполнения, приложение использует первую версию, которая указана в файле конфигурации и установлена.  
  
 Дополнительные сведения см. в разделе [Практическое руководство. Настройка приложения для назначения версии .NET Framework](http://msdn.microsoft.com/en-us/5247b307-89ca-417b-8dd0-e8f9bd2f4717).  
  
 Для запуска в версии 1.0 или 1.1 среды CLR приложение, созданное компилятором Visual C++, должно быть скомпилировано с параметром [/clr:initialAppDomain](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="see-also"></a>См. также  
 [Развертывание классических приложений](../ide/deploying-native-desktop-applications-visual-cpp.md)