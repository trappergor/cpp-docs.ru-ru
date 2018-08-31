---
title: Подготовка тестового компьютера для выполнения исполняемого файла отладки | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debug executable, preparing a test machine to run
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3600e5541c095b3879fe60404c9a5994c2a91088
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2018
ms.locfileid: "42578217"
---
# <a name="preparing-a-test-machine-to-run-a-debug-executable"></a>Подготовка тестового компьютера для выполнения исполняемого файла отладки
Чтобы подготовить компьютер к тестированию отладочной версии приложения, созданного с помощью Visual C++, нужно развернуть отладочные версии библиотек DLL Visual C++, от которых зависит приложение. Чтобы определить, какие библиотеки DLL нужно развернуть, выполните действия, описанные в разделе [Основные сведения о зависимостях приложения Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Как правило, отладочные версии библиотек DLL Visual C++ имеют имена, заканчивающиеся на "d". Например, отладочная версия msvcr100.dll называется msvcr100d.dll.  
  
> [!NOTE]
>  Отладочные версии приложения, как и отладочные версии библиотек DLL Visual C++, не являются распространяемыми. Вы можете развернуть отладочные версии приложений и библиотек DLL Visual C++ только на других своих компьютерах и исключительно для отладки и тестирования приложений на компьютере без установленной Visual Studio. Дополнительные сведения см. в разделе [Redistributing Visual C++ Files](../ide/redistributing-visual-cpp-files.md).  
  
 Существует три способа развернуть отладочные версии библиотек DLL Visual C++ вместе с отладочной версией приложения.  
  
-   Используйте центральное развертывание для установки отладочной версии конкретной библиотеки DLL Visual C++ в каталоге %windir%\system32\, используя проект установки, который включает в себя модули слияния для подходящей версии библиотеки и архитектуры приложения. Модули слияния можно найти в каталоге Program Files или Program Files (x86) внутри \Common Files\Merge Modules\\. Отладочная версия модуля слияния имеет слово Debug в имени, например Microsoft_VC110_DebugCRT_x86.msm. Пример этого развертывания можно найти в разделе [Пошаговое руководство. Развертывание приложения Visual C++ с помощью проекта установки](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).  
  
-   Используйте локальное развертывание для установки отладочной версии конкретной библиотеки DLL Visual C++ в каталоге установки приложения, используя файлы, находящиеся в каталоге Program Files или Program Files (x86) внутри \Microsoft Visual Studio \<версия>\VC\redist\Debug_NonRedist\\.  
  
    > [!NOTE]
    >  Для удаленной отладки приложения, созданного с помощью Visual C++ 2005 или Visual C++ 2008 на другом компьютере, нужно развернуть отладочные версии библиотек DLL Visual C++ в качестве общих параллельных сборок. Вы можете использовать проект установки или установщик Windows для установки подходящих модулей слияния.  
  
-   Используйте параметр **Развернуть** в диалоговом окне **Диспетчер конфигураций** Visual Studio, чтобы скопировать выходные и другие файлы проекта на удаленный компьютер. 
  
 Установив библиотеки DLL Visual C++, вы можете запустить удаленный отладчик в сетевой папке. Дополнительные сведения об удаленной отладке см. в разделе [Удаленная отладка](/visualstudio/debugger/remote-debugging.md).  
  
## <a name="see-also"></a>См. также  
 
 [Развертывание в Visual C++](../ide/deployment-in-visual-cpp.md)   
 [Параметры командной строки установщика Windows](/windows/desktop/Msi/command-line-options)   
 [Примеры развертывания](../ide/deployment-examples.md) [Удаленная отладка](/visualstudio/debugger/remote-debugging.md)