---
title: "Подготовка тестового компьютера для запуска исполняемого файла отладки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- debug executable, preparing a test machine to run
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 344f413eb2325156996700b6975826600ab997f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="preparing-a-test-machine-to-run-a-debug-executable"></a>Подготовка тестового компьютера для выполнения исполняемого файла отладки
Чтобы подготовить компьютер для тестирования отладочной версии приложения, созданного с помощью Visual C++, необходимо развернуть отладочные версии библиотеки Visual C++ библиотеки DLL, которая зависит от приложения. Чтобы определить, имеющих библиотеки DLL для развертывания, выполните действия, описанные в [основные сведения о зависимостях приложения Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Как правило отладочные версии библиотек DLL Visual C++ имеют имена, заканчивающиеся на «d»; Например отладочная версия msvcr100.dll называется msvcr100d.dll.  
  
> [!NOTE]
>  Отладочные версии приложения не являются распространяемыми и непригодны отладочные версии библиотек DLL Visual C++. Отладочные версии приложений и библиотек DLL Visual C++ можно развернуть только на других компьютерах, исключительно с целью отладки и тестирования приложения на компьютере, который не установлено приложение Visual Studio. Дополнительные сведения см. в разделе [Redistributing Visual C++ Files](../ide/redistributing-visual-cpp-files.md).  
  
 Существует три способа развернуть отладочные версии библиотек DLL Visual C++ вместе с отладочной версии приложения.  
  
-   Использование центра развертывания для установки отладочной версии конкретной библиотеки DLL Visual C++ в каталог %windir%\system32\ с помощью проекта установки, который включает в себя модули слияния для подходящую библиотеку версии и архитектуры приложения. Модули слияния можно найти на Program Files или каталог Program Files (x86) в \Common Files\Merge модулей\\. Отладочная версия модуля слияния имеет отладки в примере namefor Microsoft_VC110_DebugCRT_x86.msm. Пример этого развертывания, можно найти в [Пошаговое руководство: развертывание Visual C++ приложения с помощью проекта установки](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).  
  
-   Использование локального развертывания для установки отладочной версии конкретной библиотеки DLL Visual C++ в каталог установки приложения, используя файлы, включенные в каталог Program Files (x86) в \Microsoft Visual Studio или Program Files \<версии > \VC\redist\Debug_NonRedist\\.  
  
    > [!NOTE]
    >  Для удаленной отладки приложения, написанного на Visual C++ 2005 или Visual C++ 2008 на другом компьютере, необходимо развернуть отладочные версии библиотек Visual C++ DLL в качестве общего side-by-side сборок. Чтобы установить соответствующие модули слияния можно использовать проект установки или установщика Windows.  
  
-   Используйте the_**развернуть** в диалоговом окне **Configuration Manager** диалоговое окно в Visual Studio, чтобы скопировать выходные файлы проекта и другие файлы к удаленному компьютеру. 
  
 После установлены библиотеки DLL Visual C++, можно запустить удаленный отладчик на общем сетевом ресурсе. Дополнительные сведения об удаленной отладке см. в разделе [удаленной отладки](/visualstudio/debugger/remote-debugging.md).  
  
## <a name="see-also"></a>См. также  
 
 [Развертывание в Visual C++](../ide/deployment-in-visual-cpp.md)   
 [Windows Параметры командной строки установщика](http://msdn.microsoft.com/library/windows/desktop/aa367988.aspx)   
 [Примеры развертывания](../ide/deployment-examples.md) [удаленной отладки](/visualstudio/debugger/remote-debugging.md)